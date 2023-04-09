
## grep

grep 是代表“全局正则表达式打印”的首字母缩写词。grep 是一个程序，它逐行扫描一个或多个指定文件，返回包含模式的行。模式是一种表达式，它通过将字符解释为元字符来指定一组字符串。例如，星号元字符 (*) 被解释为“零个或多个前面的元素”。这使用户能够在 grep 命令中键入一小段字符和元字符，让计算机向我们显示文件匹配的行。

标准的 grep 命令如下所示：

```
grep <flags> '<regular expression>' <filename>
```

grep 将搜索结果打印到屏幕 (stdout) 并返回以下退出值：

```
0    A match was found.
1    No match was found.
>1   A syntax error was found or a file was inaccessible 
     (even if matches were found).
```

一些常见的标志是：`-c`用于计算成功匹配的数量而不打印实际匹配，`-i`使搜索不区分大小写，`-n`在每个匹配打印输出之前打印行号，`-v`取正则表达式的补码（即返回行不匹配），并`-l`打印包含与表达式匹配的行的文件的文件名。

## egrep

egrep 是代表“扩展全局正则表达式打印”的首字母缩写词。

egrep 中的“E”表示将模式视为正则表达式。在 egrep 中启用了缩写为“ERE”的“扩展正则表达式”。egrep（与 相同`grep -E`）将`+`, `?`, `|`, `(`, 和`)`视为元字符。

在基本正则表达式（使用 grep）中，元字符`?`, `+`, `{`, `|`, `(`, 和`)`失去了它们的特殊含义。如果您希望 grep 将这些字符视为元字符，请将它们转义 `\?`, `\+`, `\{`, `\|`, `\(`, 和`\)`。

例如，这里 grep 使用基本的正则表达式，其中加号按字面意思处理，返回任何带有加号的行。

```
grep "+" myfile.txt
```

另一方面，egrep 将“+”视为元字符并返回每一行，因为加号被解释为“一次或多次”。

```
egrep "+" myfile.txt
```

这里返回每一行，因为`+`egrep 将其视为元字符。正常的 grep 只会搜索带有文字的行`+`。

## fgrep

fgrep 是代表“固定字符串全局正则表达式打印”的首字母缩写词。

fgrep（与 grep -F 相同）是固定的或快速的 grep，其行为与 grep 相同，但不将任何正则表达式元字符识别为特殊字符。搜索将更快地完成，因为它只处理简单的字符串而不是复杂的模式。

例如，如果我想在 .bash_profile 中搜索文字点 (.)，那么使用 grep 会很困难，因为我必须转义点，因为点是一个元字符，表示“通配符，任何单个字符”：

```bash
grep "." myfile.txt
```

上面的命令返回 myfile.txt 的每一行。改为这样做：

```bash
fgrep "." myfile.txt
```

然后只有具有文字“。”的行 在他们返回。fgrep 帮助我们不用费心转义我们的元字符。

## pgrep

pgrep 是一个首字母缩写词，代表“Process-ID Global Regular Expressions Print”。

pgrep 查看当前正在运行的进程并将与选择条件匹配的进程 ID 列出到标准输出。当您只想知道进程的进程 ID 整数时，pgrep 很方便。`pgrep mysql`例如，如果我只想知道我的 mysql 进程的进程 ID，我会使用返回进程 ID 的 命令，如 7312

```bash

pgrep -f "lcltc"

```


```shell
#!/bin/sh  
#!/bin/bash  
  
# 上一个进程名关键字（可能不同的版本），当前进程的jar名  
JAR_NAME='app-mt-lcltc-provider'  
# source /etc/profile  
# ps -ef | grep "$JAR_NAME" |grep -v grep |awk '{print $2}' |xargs kill -9  
LAST_PID=$(pgrep -f "${JAR_NAME}")  
  
if [ -z "${LAST_PID}" ];then  
    echo "无正在运行的进程"  
else  
    echo "正在运行的进程(PID):${LAST_PID}"  
    kill -9 "${LAST_PID}"  
    echo "kill -9 (PID):${LAST_PID}"  
fi  
  
# 获取所在目录  
install_dir="$( cd "$( dirname "${BASH_SOURCE[0]}" )" >/dev/null 2>&1 && pwd )"  
echo "JAR所在目录：${install_dir}"  
  
# 找到所在目录中JAR的全名  
jar_file_name="$(ls ${install_dir} |grep ${JAR_NAME})"  
echo "JAR包：${install_dir}/${jar_file_name}"  
  
  
java -Xms512m -Xmx2048m -jar -Dfile.encoding=utf-8 -XX:+HeapDumpOnOutOfMemoryError -XX:HeapDumpPath="${install_dir}" "${install_dir}/${jar_file_name}" --spring.main.allow-bean-definition-overriding=true --sms.platform.key:ALI_CLOUD > /dev/null &  
echo '已启动'
```


```Shell

journalctl -f -u logstash

```

# TCPDUMP

yum -y install tcpdump

```bash
### 可用的网卡
tcpdump -D

### 监听特定主机
# 例子：监听本机跟主机`182.254.38.55`之间往来的通信包。
# 备注：出、入的包都会被监听。
tcpdump host 182.254.38.55

### 特定来源、目标地址的通信
# 特定来源
tcpdump src host hostname
# 特定目标地址
tcpdump host hostname

### Show the HTTPs Traffic

tcpdump -nnSX port 443



```


```bash
tcpdump -ni eth0 -ttt
```

-ttt 输出所包含的DELTA时间，测量了包和包之间的时间。

# SYS-STATE

yum -y install sysstate


## netstat

