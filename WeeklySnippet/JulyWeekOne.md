





# First Week: Operating Systems


- [First Week: Operating Systems](#First-Week-Operating-Systems)
  - [Threading: July 3rd (Wednesday)](#Threading-July-3rd-Wednesday)
    - [Implement a Thread Pool (D.E. Shaw)](#Implement-a-Thread-Pool-DE-Shaw)
      - [The ThreadPool class](#The-ThreadPool-class)
      - [The WorkerThread class](#The-WorkerThread-class)
  - [Operating System: July 4th (Thursday)](#Operating-System-July-4th-Thursday)

## Threading: July 3rd (Wednesday)

### Implement a Thread Pool (D.E. Shaw)
- Each `Task` implements `Runnable`
- A `ThreadPool` composes of a `TaskQueue` and a list of `WorkerThread`
- `WorkerThread` extends `Thread`, and they loop forever, blocking when queue is empty
- `main` loop instantiate `ThreadPool` with number of threads and throws tasks to it
- Sources: [Source 1](https://caffinc.github.io/2016/03/simple-threadpool), [Source 2](https://howtodoinjava.com/java/multi-threading/control-concurrent-access-to-multiple-copies-of-a-resource-using-semaphore).

#### The ThreadPool class
```java
public class ThreadPool {

    WorkerThread[] threads;
    Queue<Task> taskQueue;

    public ThreadPool(int numberOfThreads) {
        threads = new WorkerThread[numberOfThreads];
        taskQueue = new Queue();
    }

    public addTask(Task task) {
        synchronized(taskQueue) {
            taskQueue.add(task);
            taskQueue.notify();
        }
    }

    public start() {
        for (WorkerThread thread: threads) {
            thread.start();
        }
    }
}
```

#### The WorkerThread class
```java

```

## Operating System: July 4th (Thursday)

```java

```