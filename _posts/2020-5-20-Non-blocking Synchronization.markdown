---
layout: post
title: Non-blocking Synchronization
date: 2020-05-20 00:00:00 +0300
description:  # Add post description (optional)
img: # Add image post (optional)
tags: [性能] # add tag
---

# Non-blocking Synchronization

1. Wait-free 

Wait-free 是指任意线程的任何操作都可以在有限步之内结束，而不用关心其它线程的执行速度。 Wait-free 是基于 per-thread 的，可以认为是 starvation-free 的。非常遗憾的是实际情况并非如此，采用 Wait-free 的程序并不能保证 starvation-free，同时内存消耗也随线程数量而线性增长。目前只有极少数的非阻塞算法实现了这一点。 

2. Lock-free 

Lock-Free 是指能够确保执行它的所有线程中至少有一个能够继续往下执行。由于每个线程不是 starvation-free 的，即有些线程可能会被任意地延迟，然而在每一步都至少有一个线程能够往下执行，因此系统作为一个整体是在持续执行的，可以认为是 system-wide 的。所有 Wait-free 的算法都是 Lock-Free 的。 

3. Obstruction-free 

Obstruction-free 是指在任何时间点，一个孤立运行线程的每一个操作可以在有限步之内结束。只要没有竞争，线程就可以持续运行。一旦共享数据被修改，Obstruction-free 要求中止已经完成的部分操作，并进行回滚。所有 Lock-Free 的算法都是 Obstruction-free 的。 

综上所述，不难得出 Obstruction-free 是 Non-blocking synchronization 中性能最差的，而 Wait-free 性能是最好的，但实现难度也是最大的，因此 Lock-free 算法开始被重视，并广泛运用于当今正在运行的程序中，比如linux内核。 

一般采用原子级的 read-modify-write 原语来实现 Lock-Free 算法，其中 LL 和 SC 是 Lock-Free 理论研究领域的理想原语，但实现这些原语需要 CPU 指令的支持，非常遗憾的是目前没有任何 CPU 直接实现了 SC 原语。根据此理论，业界在原子操作的基础上提出了著名的 CAS（Compare - And - Swap）操作来实现 Lock-Free 算法，Intel 实现了一条类似该操作的指令：cmpxchg8。
