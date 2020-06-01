---
layout: post
title: FeignClient原理
date: 2020-06-01 00:00:00 +0800
description:  # Add post description (optional)
img: # Add image post (optional)
tags: [微服务,原理,架构] # add tag
---

# Feign远程调用的基本流程

`https://github.com/OpenFeign/feign/tree/master/core/src/main/java/feign`

在微服务启动时，Feign会进行包扫描，对加@FeignClient注解的接口，按照注解的规则，创建远程接口的本地JDK Proxy代理实例。然后，将这些本地Proxy代理实例，注入到Spring IOC容器中。当远程接口的方法被调用，由Proxy代理实例去完成真正的远程访问，并且返回结果。

`
@FeignClient 远程调用接口 → JDK Proxy 动态实例代理 → InvokeHandler → MethodHandler 
→ 构造RequestTemplate → Encoder → Interceptors,Logger 
→ feign.Client → Decoder → MethodHandler → InvokeHandler → JDK Proxy 动态实例代理
→ Response Bean
`

## JDK Proxy 动态实例代理
Feign在启动时，会为其创建一个本地JDK Proxy代理实例，并注册到Spring IOC容器。

## InvokeHandler

通过 JDK Proxy 生成动态代理类，核心步骤就是需要定制一个调用处理器，具体来说，就是实现JDK中位于java.lang.reflect 包中的 InvocationHandler 调用处理器接口，并且实现该接口的 invoke（…） 抽象方法。

两个实现：

- Feign.InvocationHandler 默认的(FeignInvocationHandler)
    
    默认的调用处理器 FeignInvocationHandle，在处理远程方法调用的时候，
    会根据Java反射的方法实例，在dispatch 映射对象中，找到对应的MethodHandler 方法处理器，然后交给MethodHandler 完成实际的HTTP请求和结果的处理。
    - 成员 Map<Method, MethodHandler> dispatch : 每个远程的方法对应一个MethodHandler
    - 不建议使用：
        - 没有远程调用过程中的熔断监测和恢复机制；
        - 也没有用到高性能的HTTP连接池技术。
        
- Feign.hystrix(HystrixInvocationHandler)

## MethodHandler

MethodHandler 的invoke(…)方法，主要职责是完成实际远程URL请求，然后返回解码后的远程URL的响应结果。

实现：

- 默认的：SynchronousMethodHandler
    SynchronousMethodHandler的invoke(…)方法，调用了自己的executeAndDecode(…) 请求执行和结果解码方法。该方法的工作步骤：
    
    - 首先通 RequestTemplate 请求模板实例，生成远程URL请求实例 request；
    - 然后用自己的 feign 客户端client成员，execute(…) 执行请求，并且获取 response 响应；
    - 对response 响应进行结果解码。
    - SynchronousMethodHandler实例的client成员，不是feign.Client.Default类型，而是 LoadBalancerFeignClient 客户端负载均衡类型。
- DefaultMethodHandler

##  feign.Client

客户端组件是Feign中一个非常重要的组件，负责端到端的执行URL请求。其核心的逻辑：发送request请求到服务器，并接收response响应后进行解码。

feign.Client 类，是代表客户端的顶层接口，只有一个抽象方法

实现：

- 默认 Client.Default
    - feign.Client 客户端实现类，内部使用 HttpURLConnection 完成URL请求处理；
    - 在JKD1.8中，虽然在HttpURLConnnection 底层，使用了非常简单的HTTP连接池技术，但是，其HTTP连接的复用能力，实际是非常弱的，性能当然也很低。
    
- ApacheHttpClient 
    - 内部使用 Apache httpclient 开源组件完成URL请求处理的feign.Client 客户端实现类；
    - 从代码开发的角度而言，Apache HttpClient相比传统JDK自带的URLConnection，增加了易用性和灵活性，它不仅使客户端发送Http请求变得容易，而且也方便开发人员测试接口。既提高了开发的效率，也方便提高代码的健壮性。
    - 从性能的角度而言，Apache HttpClient带有连接池的功能，具备优秀的HTTP连接的复用能力。关于带有连接池Apache HttpClient的性能提升倍数，具体可以参见后面的对比试验。
    - 

- OkHttpClient
    - 内部使用 OkHttp3 开源组件完成URL请求处理的feign.Client 客户端实现类。
    - OkHttp3 开源组件由Square公司开发，用于替代HttpUrlConnection和Apache HttpClient。由于OkHttp3较好的支持 SPDY协议（SPDY是Google开发的基于TCP的传输层协议，用以最小化网络延迟，提升网络速度，优化用户的网络使用体验。）
    - 从Android4.4开始，google已经开始将Android源码中的 HttpURLConnection 请求类使用OkHttp进行了替换。也就是说，对于Android 移动端APP开发来说，OkHttp3 组件，是基础的开发组件之一。
    

- LoadBalancerFeignClient 
    - 内部使用 Ribbon 负载均衡技术完成URL请求处理的feign.Client 客户端实现类。
    - 简单的使用了delegate包装代理模式：Ribben负载均衡组件计算出合适的服务端server之后，由内部包装 delegate 代理客户端完成到服务端server的HTTP请求；
    - 所封装的 delegate 客户端代理实例的类型，可以是 Client.Default 默认客户端，也可以是 ApacheHttpClient 客户端类或OkHttpClient 高性能客户端类，还可以其他的定制的feign.Client 客户端实现类型。
    
    
