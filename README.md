# **`Java Concurrency Notes`**

# Table of contents

- [**Introduction**](#introduction)
    - [**Fundamentals**](#fundamentals)
        - [Multithreading benefits](#multithreading-benefits)
        - [Concurrency vs. Parallelism](#concurrency-vs-parallelism)
        - [What is concurrency](#what-is-concurrency)
        - [Thread safety](#thread-safety)
        - [Sharing objects](#sharing-objects)
        - [Composing objects](#composing-objects)
        - [Building blocks](#building-blocks)
    - [**Concurrency Introduction**](#concurrency-introduction)
        - [Concurrency in a breeze](#concurrency-in-a-breeze)
        - [The message passing model](#the-message-passing-model)
        - [The shared memory and shared state model](#the-shared-memory-and-shared-state-model)
        - [Of patterns and paradigms](#of-patterns-and-paradigms)
- [**Strategies, patterns and models**](#strategies-patterns-and-models)
    - [**Strategies for concurrency**](#strategies-for-concurrency)
        - [Division of Labor](#division-of-labor)
        - [Design Approaches](#design-approaches)
        - [Concurrency Models](#concurrency-models)
        - [Same-Threading](#same-threading)
        - [Single-threaded concurrency](#single-threaded-concurrency)
    - [**Structuring concurrent applications**](#structuring-concurrent-applications)
        - [Creating and starting Java threads](#creating-and-starting-java-threads)
        - [A thread and its context](#a-thread-and-its-context)
        - [Race Conditions & Critical Sections](#race-conditions--critical-sections)
        - [Thread Safety & Shared Resources](#thread-safety--shared-resources)
        - [Thread Safety & Immutability](#thread-safety--immutability)
        - [Task Execution](#task-execution)
        - [Cancellation and Shutdown](#cancellation-and-shutdown)
        - [Applying Thread Pools](#applying-thread-pools)
    - [**Threading Patterns**](#threading-patterns)
        - [A bounded buffer](#a-bounded-buffer)
        - [Reader or writer locks](#reader-or-writer-locks)
        - [Counting semaphores](#counting-semaphores)
        - [Our own reentrant lock](#our-own-reentrant-lock)
        - [Countdown latch](#countdown-latch)
        - [A cyclic barrier](#a-cyclic-barrier)
        - [A future task](#a-future-task)
    - [**Thread Pools**](#thread-pools)
        - [Thread pools](#thread-pools)
        - [The fork-join pool](#the-fork-join-pool)
        - [Work stealing](#work-stealing)
        - [Active objects](#active-objects)
- [**Liveness, Performance, and Testing**](#liveness-performance-and-testing)
    - [**Avoiding Liveness Hazards**](#avoiding-liveness-hazards)
    - [**Performance and Scalability**](#performance-and-scalability)
    - [**Testing Concurrent Programs**](#testing-concurrent-programs)
    - [**Increasing the Concurrency**](#increasing-the-concurrency)
        - [A lock-free stack](#a-lock-free-stack)
        - [A lock-free FIFO queue](#a-lock-free-fifo-queue)
        - [Concurrent hashing](#concurrent-hashing)
        - [The big lock approach](#the-big-lock-approach)
        - [The lock striping design pattern](#the-lock-striping-design-pattern)
- [**Modern Java/JDK Concurrency**](#modern-javajdk-concurrency)
    - [**Scalability and Thread Safety**](#scalability-and-thread-safety)
    - [**Taming Shared Mutability**](#taming-shared-mutability)
- [**Software Transactional Memory**](#software-transactional-memory)
    - [**Introduction**](#introduction)
    - [**STM in Clojure, Groovy, Java, JRuby, and Scala**](#stm-in-clojure-groovy-java-jruby-and-scala)
- [**Functional Concurrency Patterns**](#functional-concurrency-patterns)
    - [**Immutability**](#immutability)
    - [**Futures**](#futures)
- [**Actor-Based Concurrency**](#actor-based-concurrency)
    - [**Favoring Isolated Mutability**](#favoring-isolated-mutability)
    - [**Actors in Groovy, Java, JRuby, and Scala**](#actors-in-groovy-java-jruby-and-scala)
    - [**Actors patterns**](#actors-patterns)
        - [Message driven concurrency](#message-driven-concurrency)
- [**Advanced Topics**](#advanced-topics)
    - [**Explicit Locks**](#explicit-locks)
    - [**Building Custom Synchronizers**](#building-custom-synchronizers)
    - [**Atomic Variables and Nonblocking Synchronization**](#atomic-variables-and-nonblocking-synchronization)
    - [**The Java Memory Model**](#the-java-memory-model)
- [**Appendixes**](#appendixes)
    - [**Annotations for Concurrency**](#annotations-for-concurrency)
    - [**Programmer's guide**](#programmers-guide)
    - [**Architect's guide**](#architects-guide)
    - [**Clojure Agents**](#clojure-agents)
    - [**Amdahl's Law**](#amdahls-law)
- [**Bibliography/References:**](#bibliographyreferences)

# **Introduction**

## **Fundamentals**

### Multithreading benefits
### Concurrency vs. Parallelism
### What is concurrency
### Thread safety
### Sharing objects
### Composing objects
### Building blocks

## **Concurrency Introduction**

### Concurrency in a breeze
### The message passing model
### The shared memory and shared state model
### Of patterns and paradigms

# **Strategies, patterns and models**

## **Strategies for concurrency**

### Division of Labor
### Design Approaches
### Concurrency Models
### Same-Threading
### Single-threaded concurrency

## **Structuring concurrent applications**

### Creating and starting Java threads
### A thread and its context
### Race Conditions & Critical Sections
### Thread Safety & Shared Resources
### Thread Safety & Immutability
### Task Execution
### Cancellation and Shutdown
### Applying Thread Pools

## **Threading Patterns**

### A bounded buffer
### Reader or writer locks
### Counting semaphores 
### Our own reentrant lock
### Countdown latch
### A cyclic barrier
### A future task

## **Thread Pools**

### Thread pools
### The fork-join pool
### Work stealing
### Active objects

# **Liveness, Performance, and Testing**

## **Avoiding Liveness Hazards**
## **Performance and Scalability**
## **Testing Concurrent Programs**
## **Increasing the Concurrency**

### A lock-free stack
### A lock-free FIFO queue
### Concurrent hashing
### The big lock approach
### The lock striping design pattern

# **Modern Java/JDK Concurrency**

## **Scalability and Thread Safety**
## **Taming Shared Mutability**

# **Software Transactional Memory**

## **Introduction**
## **STM in Clojure, Groovy, Java, JRuby, and Scala**

# **Functional Concurrency Patterns**

## **Immutability**
## **Futures**

# **Actor-Based Concurrency**

## **Favoring Isolated Mutability**
## **Actors in Groovy, Java, JRuby, and Scala**
## **Actors patterns**

### Message driven concurrency

# **Advanced Topics**

## **Explicit Locks**
## **Building Custom Synchronizers**
## **Atomic Variables and Nonblocking Synchronization**
## **The Java Memory Model**

# **Appendixes**

## **Annotations for Concurrency**
## **Programmer's guide**
## **Architect's guide**
## **Clojure Agents**
## **Amdahl's Law**

# **Bibliography/References:**

> [1]
> B. Goetz, Java concurrency in practice. Upper Saddle River, NJ: Addison-Wesley, 2006.
> 
> [2]
> V. Subramaniam, Programming concurrency on the JVM: mastering synchronization, STM, and actors.
> Dallas, Tex: Pragmatic Bookshelf, 2011.
> 
> [3]
> J. Jenkov, «Java Concurrency and Multithreading Tutorial». [Online]. 
> Disponible en: http://tutorials.jenkov.com/java-concurrency/index.html. [Accedido: 26-sep-2021]
> 
> [4]
> A. S. Khot, Concurrent Patterns and Best Practices. 2018 [Online]. Disponible en: http://sbiproxy.uqac.ca/login?url=https://international.scholarvox.com/book/88863236. [Accedido: 26-sep-2021]

