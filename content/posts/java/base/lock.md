---
title: "Java 同步锁"
date: 2020-01-30T10:11:14+08:00
draft: false
authorEmoji: 🤖 # emoji for subtitle, summary meta data
authorImage: "/img/whoami/avatar1.jpg" # image path in the static folder
authorDesc: "hello"# author description
tags: ["tutorial","Java","Lock","同步锁"]
categories: ["Java"]
series: ["Tutorial"]
description: "Java 同步锁（Lock、ReadWriteLock）"
---
# Java同步锁
> 从Java5开始，Java提供功能更强大的线程同步机制——Lock
> - Lock提供比synchronized更广泛的锁定操作
> - Lock允许实现更灵活的结构，支持多个相关的Condition对象
> - Java提供两个根类——Lock、ReadWriteLock
> - 使用Lock与使用同步方法相似，只是使用Lock是显式使用Lock对象作为同步锁，而同步方法为隐式使用当前对象作为同步监视器

## Lock
控制多个线程对共享资源的访问
- lock()
- lockInterruptibly()
- tryLock()
- tryLock(long var1, TimeUnit var3)
- unlock()
- newCondition()

### 实现类——ReentrantLock
```java
class RentrantLockDemo {
    private final ReentrantLock lock = new ReentrantLock();

    public void lockOpt(){
        // 加锁
        lock.lock()

        try{
            // operation
        }catch(Exception e){

        }finaly{
            // 解锁
            lock.unlock()
        }
    }
}
```


## ReadWriteLock
对共享资源的并发访问
- readLock()
- writeLock()

### 实现类——ReentrantReadWriteLock
为读写操作提供了三种操作模式
- Writing
- ReadingOptimistic
- Reading

## Java8新增的StampedLock
在大多数情况下可以替代传统的ReentrantReadWriteLock




