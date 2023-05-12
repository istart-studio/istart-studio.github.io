# 常见问题

<details>
  <summary>Java 中线程有哪些状态？线程状态之间的转换是如何发生的？</summary>
  <p>

- NEW：新建状态，线程被创建后还未开始执行。
- RUNNABLE：可运行状态，线程正在Java虚拟机中执行，但可能正在等待操作系统资源（如CPU资源）。
- BLOCKED：阻塞状态，线程被阻塞并等待锁的释放以获取对共享资源的访问权限。
- WAITING：等待状态，线程等待其他线程执行特定操作，如线程进入wait状态时等待其他线程调用notify或notifyAll方法唤醒它。
- TIMED_WAITING：限时等待状态，线程在等待另一个线程执行特定操作时，在指定的时间内等待。
- TERMINATED：终止状态，线程已经执行完毕。
- 线程状态之间的转换通常由Java虚拟机的线程调度器控制，但也受到其他因素（例如线程优先级和等待时间）的影响。

例如，当线程调用sleep方法、join方法或者等待IO操作完成时，线程状态会从RUNNABLE转变为TIMED_WAITING状态或WAITING状态。当线程等待获取锁资源时，线程状态会从RUNNABLE转变为BLOCKED状态。
线程状态的变化是由Java虚拟机的线程调度器来控制的，线程调度器会根据各个线程的优先级以及其他一些因素来决定线程的调度顺序。在一些情况下，我们也可以手动控制线程状态的转换，例如使用wait、notify、notifyAll等方法来控制线程的等待和唤醒。
</p>
</details>
<details>
  <summary>Java 中的锁有哪几种？它们之间有何区别？</summary>
  <p>

- synchronized关键字：是Java内置的一种锁机制，只能在方法或代码块中使用。它采用的是悲观锁思想，即假定并发访问是频繁的，因此在执行代码块前，先获取锁，执行完代码块后，再释放锁。synchronized锁的粒度比较大，如果锁的范围太大，会影响系统的并发性能。

- ReentrantLock：是JDK提供的可重入锁机制，可以在代码块中随意获取锁，锁的范围比synchronized更加灵活。相比synchronized，ReentrantLock还提供了更多高级功能，如可响应中断、超时机制、公平锁等。

- ReadWriteLock：是JDK提供的读写锁机制，适用于读多写少的场景。它允许多个线程同时获取读锁，但只允许一个线程获取写锁。

- StampedLock：是JDK 8新增的一种锁机制，是ReadWriteLock的升级版，允许在不同的访问模式之间进行转换，比如从写锁转换为读锁。它的性能比ReadWriteLock更好，但使用起来相对复杂。

- volatile关键字：是Java提供的一种轻量级的锁机制，主要用于保证变量的可见性。它可以确保一个变量在多个线程之间的可见性，但并不能保证原子性，因此不能用于对变量的原子操作。

这些锁之间的区别主要体现在锁的粒度、锁的性能、锁的可重入性、锁的公平性、锁的支持多少个线程同时获取等方面。在具体的场景中，需要根据实际情况选择合适的锁机制。
</p>
</details>
<details>
  <summary>什么是 synchronized 关键字？如何使用 synchronized 实现同步？</summary>
  <p>
synchronized 是 Java 中的一个关键字，可用于修饰方法或代码块，用于实现同步。使用 synchronized 关键字可以保证多个线程访问共享资源时的安全性，避免出现竞态条件。
使用 synchronized 实现同步有以下几种方式：

**同步方法**：使用 synchronized 修饰方法，使得在执行该方法时，当前对象被锁定，其他线程无法访问该方法。

```java
public synchronized void method() {
// ...
}
```

**同步代码块**：使用 synchronized 关键字修饰一个代码块，使得在执行该代码块时，当前对象被锁定，其他线程无法访问该代码块。

```java
synchronized (this) {
// ...
}
```

需要注意的是，使用 synchronized 实现同步时，要避免死锁等问题，同时尽量减小同步范围，提高并发效率。
</p>
</details>
<details>
  <summary>Java 中的 Lock 接口和 synchronized 关键字有何区别？你会选择哪一种实现同步？为什么？</summary>
  <p>

- 粒度：synchronized锁是在代码块或方法上的，而Lock接口允许对更细粒度的控制，可以在任意时刻获取和释放锁。
- 可中断性：使用synchronized时，一旦获取了锁，就必须等到代码块执行完成才会释放锁。而Lock接口提供了可中断的获取锁机制，如果获取锁的线程被中断，则可以响应中断，并释放锁。
- 公平性：synchronized锁是非公平的，也就是说，当有多个线程等待同一把锁时，没有任何机制来保证哪个线程会获得锁。而Lock接口提供了公平性选择，可以按照线程请求的顺序获取锁。
- 条件变量：Lock接口提供了条件变量的机制，可以让线程在特定条件下等待或唤醒。
- 性能：在高并发情况下，Lock接口比synchronized锁更具性能优势。

针对不同的需求和场景，选择使用Lock接口还是synchronized关键字需要根据具体情况而定。如果需要对代码块进行同步控制，而且不需要更细粒度的控制和条件变量的机制，可以使用synchronized。如果需要更高的灵活性和性能，以及可中断性和公平性选择，可以使用Lock接口。

综上所述，Lock接口提供了更高级别的同步控制机制，适用于更复杂的并发场景，而synchronized关键字则更简单易用，适用于简单的同步控制。
</p>
</details>
<details>
  <summary>什么是 ReentrantLock？相比于 synchronized 有哪些优势和不同之处？</summary>
  <p>
ReentrantLock是Java中的一个可重入锁，与synchronized一样可以实现线程之间的同步。相比于synchronized，ReentrantLock具有以下优势和不同之处：

- 可重入性：ReentrantLock允许同一个线程多次获得该锁，而synchronized不允许。
- 公平性：ReentrantLock可以设置为公平锁或非公平锁，而synchronized只能是非公平锁。
- 可中断性：ReentrantLock可以响应中断，即可以在等待锁的过程中被中断，而synchronized不能响应中断。
- Condition支持：ReentrantLock中提供了Condition类，可以实现更加灵活的线程间通信，而synchronized则只能使用Object类的wait()和notify()方法。

性能：在高并发情况下，ReentrantLock的性能通常优于synchronized。
在实际使用中，如果需要更多的高级功能（如公平锁、可中断性、Condition支持等），可以使用ReentrantLock。如果只需要简单的同步，可以使用synchronized。
```java
ReentrantLock lock = new ReentrantLock();
lock.lock();
try {
    // 这里写需要同步的代码块
} finally {
    lock.unlock();
}
```
</p>
</details>
<details>
  <summary>什么是公平锁，非公平锁，各自的适用场景是什么？</summary>
  <p>
公平锁和非公平锁的适用场景主要取决于应用程序对锁的公平性和吞吐量的需求。

- 公平锁：公平锁能够确保所有线程获取锁的顺序与它们发出请求的顺序一致，即线程在等待队列中排队等待获取锁。因此，公平锁能够保证所有线程的公平竞争，避免线程饥饿现象。但是，由于公平锁需要维护一个等待队列，因此在高并发场景下，可能会导致性能下降，因为所有的线程都需要在队列中等待。因此，公平锁适用于对锁的公平性要求比较高的场景。
- 非公平锁：非公平锁是一种不考虑线程启动顺序的锁，它不会在获取锁时考虑等待时间或者其他线程的状态，而是直接尝试获取锁，如果锁没有被占用就获取成功，否则就进入等待队列。因此，非公平锁的获取顺序是不可预测的，先到先得的原则不能保证。与公平锁相比，非公平锁的吞吐量通常更高，因为它减少了线程之间的竞争，但是在高并发的情况下，会有部分线程长时间等待，可能会导致线程饥饿问题。非公平锁适合于读多写少的场景，可以提高整体的吞吐量
- 非公平锁也会进入等待队列，但是线程在尝试获取锁的时候，不会去优先考虑先前等待的线程是否可以获得锁，而是直接尝试获取锁，如果获取失败，再进入等待队列。这样会导致一些线程在等待锁的时候，可能会一直获取不到锁，而其他线程一直在不停的尝试获取锁，导致了线程的饥饿问题。但是相比公平锁，非公平锁的吞吐量会更高，因为它允许线程直接尝试获取锁，减少了唤醒线程的开销，适用于对吞吐量要求较高的场景。
- 当线程尝试获取非公平锁时，如果锁被占用，则该线程会进入等待队列，并处于 WAITING 状态，直到获取到锁。在等待队列中，线程不会去竞争锁，而是等待其他线程释放锁并通知等待队列中的线程。

因此，在选择公平锁和非公平锁时，需要根据应用程序的需求进行选择。如果对锁的公平性要求比较高，可以选择公平锁，否则可以选择非公平锁。
```java
ReentrantLock lock = new ReentrantLock();
lock.lock();
try {
    // 这里写需要同步的代码块
} finally {
    lock.unlock();
}
```
</p>
</details>
<details>
  <summary>什么是 volatile 关键字？为什么要使用 volatile？</summary>
  <p>
`volatile` 是 Java 中用来修饰变量的关键字，用于保证变量的可见性和禁止指令重排序优化。使用 `volatile` 修饰的变量可以保证在多线程环境下的正确性。

- 当一个变量被 `volatile` 修饰后，线程在读取该变量的值时，总是从主内存中读取，而不是从线程的本地内存中读取。
- 同时，`volatile` 修饰的变量在赋值时也会立即写入到主内存，而不是先写入到本地内存，然后再由一个写屏障（Write Barrier）将本地内存中的值刷新到主内存。
- 使用 `volatile` 的主要作用是保证变量的可见性和禁止指令重排序优化，可以确保在多线程环境下变量的正确性。但是，`volatile` 并不能保证操作的原子性，如果需要保证多个操作的原子性，需要使用锁或者使用原子类。
总之，如果需要在多线程环境下访问某个变量，而这个变量可能会被多个线程同时修改，那么就需要使用 `volatile` 来保证变量的可见性和禁止指令重排序优化。
</p>
</details>
<details>
  <summary>什么是 CAS（Compare And Swap）？它和 synchronized、Lock 之间的区别和优劣势是什么？</summary>
  <p>

CAS（Compare And Swap）是一种乐观锁机制，用于实现多线程同步和并发控制。它的原理是比较并交换，当需要修改某个共享变量时，
CAS 操作先比较这个变量的值是否和预期值相同，如果相同就执行修改操作，否则不做任何操作。整个过程是原子的。
相比于 synchronized 和 Lock，CAS 操作具有以下优点：

1. 性能更高：由于 CAS 操作是基于硬件实现的原子操作，因此比 synchronized 和 Lock 更加高效。
2. 不会阻塞线程：CAS 操作不会像 synchronized 和 Lock 一样，使线程进入阻塞状态，从而提高了程序的并发性。
3. 没有死锁问题：由于 CAS 操作没有锁的概念，因此不存在死锁问题。

然而，CAS 操作也存在一些缺点：

1. ABA 问题：在多线程环境下，由于 CAS 操作只关注变量的值，因此可能会出现 ABA 问题，即一个值先被修改为另一个值，然后又被修改回原来的值，而 CAS 操作无法识别这种情况。
2. 循环时间长：由于 CAS 操作需要不断地进行重试，因此当冲突比较多时，会导致循环时间长，影响性能。
3. 只能保证一个共享变量的原子操作：如果要保证多个共享变量的原子操作，需要使用锁等其他机制。

因此，CAS 操作适用于需要高效并发控制的场景，比如在高并发的计数器场景中，可以使用 CAS 操作来实现线程安全的自增操作。但是在需要保证复杂操作原子性的场景中，还是需要使用锁等其他机制。
</p>
</details>

<details>
  <summary>Java 中如何实现线程间通信？可以使用哪些方法？</summary>
  <p>
Java 中有多种方法可以实现线程间通信，其中常见的包括：

1. wait() 和 notify()/notifyAll() 方法：通过调用对象的 wait() 方法使线程进入等待状态，当条件满足时，通过调用对象的 notify() 或 notifyAll() 方法唤醒等待的线程。
2. Lock 和 Condition 接口：使用 Lock 和 Condition 接口的 await() 方法使线程进入等待状态，当条件满足时，通过调用 signal() 或 signalAll() 方法唤醒等待的线程。
3. 管道（PipedInputStream 和 PipedOutputStream）：通过管道实现线程间通信，一个线程将数据写入管道，另一个线程从管道中读取数据。
4. CountDownLatch：通过调用 CountDownLatch 的 await() 方法使线程进入等待状态，当计数器减为 0 时，等待的线程被唤醒。
5. CyclicBarrier：通过调用 CyclicBarrier 的 await() 方法使线程进入等待状态，当所有线程都到达屏障点时，线程被唤醒。
6. Semaphore：通过调用 Semaphore 的 acquire() 方法获取许可证，如果没有可用的许可证，则线程进入等待状态。

以上是 Java 中常用的线程间通信方法，不同的方法适用于不同的场景，需要根据具体情况选择合适的方法。
</p>
</details>

<details>
  <summary>什么是线程安全？如何保证线程安全？请列举几个常用的线程安全的集合类。</summary>
  <p>
死锁是指两个或多个线程相互等待对方持有的资源，导致所有线程都被阻塞，无法继续执行的一种情况。

避免死锁的方法包括：

1. 避免多个线程同时持有多个锁。
2. 避免持有一个锁的同时去请求另一个锁。
3. 尽量减少持有锁的时间，避免一个线程在持有一个锁的同时等待另一个锁。
4. 使用 tryLock() 方法来获取锁，避免长时间等待。

如果遇到死锁问题，可以进行如下排查和解决：

1. 分析死锁现象，确定是哪些线程、哪些资源出现了死锁。
2. 使用 jstack 命令来生成线程 dump 信息，查看线程的状态和堆栈信息，确定是否出现了死锁。
3. 使用 jconsole 或 jvisualvm 等工具来进行线程监控和分析。
4. 尝试使用 jstack 命令或者 kill -3 命令来打印线程信息，查看线程状态和堆栈信息。
5. 在代码中使用 LockSupport.parkNanos() 来打印线程堆栈信息，定位出哪个线程出现了问题。
6. 使用 jmap 命令或者 VisualVM 等工具来查看内存信息，分析是否出现了内存泄漏等问题。
7. 对代码进行调试，查找出问题所在，并进行修改。

需要注意的是，死锁问题一般比较难排查和解决，需要有一定的经验和技巧。在编写代码时，应该尽量避免出现死锁的情况。
</p>
</details>

<details>
  <summary>Java 中的 synchronized 关键字有哪些缺点？如何优化 synchronized 的性能？</summary>
  <p>

Java 中 synchronized 关键字的缺点包括：

1. 阻塞：synchronized 在获取锁失败时会导致线程阻塞，影响程序性能。
2. 只能实现互斥锁：synchronized 只能实现互斥锁，无法实现读写锁等其他锁类型。
3. 只能实现单个条件变量：synchronized 只能实现单个条件变量，如果需要实现多个条件变量，则需要通过 wait 和 notifyAll 来实现。

为了优化 synchronized 的性能，可以使用以下方法：

1. 减小同步块的范围：将同步块的范围尽量缩小，只锁定必要的共享资源。
2. 使用 synchronized 代码块替代 synchronized 方法：synchronized 方法会将整个方法锁定，如果方法比较大，会导致效率下降。可以将同步块封装在 synchronized 方法之外，这样可以缩小锁的范围，提高程序的并发能力。
3. 使用 ConcurrentHashMap 和 CopyOnWriteArrayList 等并发容器代替同步容器：这些并发容器内部实现了一些高效的同步策略，比使用同步容器更加高效。
4. 使用 Lock 和 Condition 接口：Lock 接口比 synchronized 更加灵活，可以实现公平锁和非公平锁，可以中断等待锁的线程。Condition 接口可以实现更灵活的等待和唤醒机制。
5. 使用原子类：Java 中提供了一些原子类，如 AtomicInteger、AtomicLong 等，它们内部使用了 CAS 机制，可以避免使用 synchronized 的情况下实现一些原子操作。

</p>
</details>

<details>
  <summary>什么是 AQS（AbstractQueuedSynchronizer）？它在 Java 中的实现有哪些？</summary>
  <p>

AQS（AbstractQueuedSynchronizer）是一个用于实现同步器的抽象类，是 Java 并发包中实现锁和其他同步器的基础。它采用了一种“先进先出”的等待队列，提供了可重入锁和条件等待的基本框架，是实现同步器的基础框架。

AQS 的实现采用了模板方法设计模式，它将同步器的关键逻辑封装在了几个 protected 方法中，同时提供了公开的 API 接口供子类实现。AQS 提供了两种锁的实现方式：独占锁和共享锁。

Java 并发包中的 ReentrantLock、ReentrantReadWriteLock、CountDownLatch、Semaphore 等同步器都是基于 AQS 实现的。AQS 可以让我们很方便地实现各种锁和同步器，而且可以基于 AQS 实现自己的同步器。

AQS 通过一个 volatile 类型的 int 变量 state 来表示同步状态，同时采用了一种非公平的、先进先出的等待队列来管理等待线程。在实现独占锁和共享锁时，需要分别实现 tryAcquire() 和 tryRelease() 方法，这些方法需要被子类实现以提供特定的锁语义。

AQS 还提供了一些辅助方法，比如 acquire()、release()、tryAcquireNanos()、tryReleaseShared() 等，它们是对 tryAcquire() 和 tryRelease() 方法的封装，可以更方便地使用同步器。

总之，AQS 是 Java 并发包中实现同步器的基础框架，提供了可重入锁和条件等待的基本框架，同时支持自定义同步器的实现，是实现高性能、高可靠性并发程序的重要基础。
</p>
</details>

<details>
  <summary>什么是线程局部变量？为什么要使用线程局部变量？</summary>
  <p>

线程局部变量（Thread Local Variable）是一种特殊类型的变量，在 Java 中，每个线程都可以拥有自己的线程局部变量，这些变量对于其他线程是不可见的。线程局部变量可以存储与线程相关的数据，例如用户认证信息、语言环境、用户偏好设置等。

使用线程局部变量的主要目的是为了避免线程安全问题。在多线程环境下，如果多个线程共享同一个变量，可能会出现竞争条件，导致数据错误、内存泄漏等问题。通过将共享变量转换为线程局部变量，每个线程都可以独立访问自己的变量，从而避免了线程安全问题。

在 Java 中，可以使用 ThreadLocal 类来实现线程局部变量。每个 ThreadLocal 对象实例都会关联一个线程局部变量，多个线程可以通过相同的 ThreadLocal 对象来访问不同的线程局部变量。ThreadLocal 类提供了 set()、get() 和 remove() 等方法，可以方便地设置和获取线程局部变量的值，也可以随时清除线程局部变量，从而释放相关的内存空间。
</p>
</details>


<details>
  <summary>Java 中如何进行多线程调试？请介绍一下常用的调试工具。</summary>
  <p>

AQS（AbstractQueuedSynchronizer）是一个用于实现同步器的抽象类，是 Java 并发包中实现锁和其他同步器的基础。它采用了一种“先进先出”的等待队列，提供了可重入锁和条件等待的基本框架，是实现同步器的基础框架。

AQS 的实现采用了模板方法设计模式，它将同步器的关键逻辑封装在了几个 protected 方法中，同时提供了公开的 API 接口供子类实现。AQS 提供了两种锁的实现方式：独占锁和共享锁。

Java 并发包中的 ReentrantLock、ReentrantReadWriteLock、CountDownLatch、Semaphore 等同步器都是基于 AQS 实现的。AQS 可以让我们很方便地实现各种锁和同步器，而且可以基于 AQS 实现自己的同步器。

AQS 通过一个 volatile 类型的 int 变量 state 来表示同步状态，同时采用了一种非公平的、先进先出的等待队列来管理等待线程。在实现独占锁和共享锁时，需要分别实现 tryAcquire() 和 tryRelease() 方法，这些方法需要被子类实现以提供特定的锁语义。

AQS 还提供了一些辅助方法，比如 acquire()、release()、tryAcquireNanos()、tryReleaseShared() 等，它们是对 tryAcquire() 和 tryRelease() 方法的封装，可以更方便地使用同步器。

总之，AQS 是 Java 并发包中实现同步器的基础框架，提供了可重入锁和条件等待的基本框架，同时支持自定义同步器的实现，是实现高性能、高可靠性并发程序的重要基础。
</p>
</details>


