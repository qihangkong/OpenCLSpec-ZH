# 第二章 词汇表
**Application**  
应用程序，在主机和OpenCL设备上运行的程序的组合。

**Acquire semantics**  
获取语义，为同步操作定义的内存顺序语义之一。获取语​​义适用于从内存加载的原子操作。给定两个执行单元A和B，它们作用于共享的原子对象M，如果A使用具有获取语义原子load M与B使用释放语义的原子 store M同步，则A的原子load M将发生在A进行任何后续操作之前。请注意，内存顺序的release、sequentially consistent和acquire_release 都包含release semantics ，有效的与使用获取语义的load协同。

**Acquire release semantics**  
获取释放语义，同步操作（例如原子操作）的存储顺序语义，具有获取和释放存储顺序的属性。它与读-修改-写操作一起使用。

**Atomic operations**  
原子操作，从任何角度和任何视角来看，一个操作要么已经完全或根本没有发生。与原子操作关联的内存顺序可能会限制相对于原子加载和原子存储操作的可见性（请参阅宽松语义，获取语义，释放语义或获取释放语义）。

**Blocking and Non-Blocking Enqueue API calls**  
阻塞和非阻塞的入队API调用，无阻塞队列API调用将命令放在命令队列上，并立即返回到主机。在命令完成之前，阻塞模式队列API调用不会返回到主机。

**Barrier**
栏栅，有三种类型的Barrier：command-queue barrier, a work-group barrier and a sub-group barrier。
