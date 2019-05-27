---
title: "Day Two - Java Daemon Thread"
date: 2019-05-26T17:51:31+07:00
draft: true
tags: ["30-day", "java", "threading", "concurrency"]
---


A daemon thread is a thread that is considered doing some tasks in the background like handling requests or various chronjobs that can exits in an application.

### Properties
* It can not prevent JVM from exiting when all user threads finish their executions.
* It is an utmost low priority thread.

### Methods
* **public final void setDaemon(boolean on)**: This method is used to mark the current thread as daemon thread or normal thread.
* **public final void isDaemon()**: Test if a thread is daemon thread.

### Example

{{< highlight java >}}
public class DaemonThreadDemo {
  public static void main(String[] args) {
    MyDaemonThread myThread = new MyDaemonThread();

    myThread.setDaemon(true);

    myThread.start();

    try {
      Thread.sleep(2000);
    } catch (InterruptedException e) {}
  }
}

class MyDaemonThread extends Thread {
  @Override public void run() {
    int counter = 1;
    while (true) {
      System.out.println("Hello from daemon thread. Current counter is " + counter);

      try {
        Thread.sleep(500);
      } catch (InterruptedException e) {}

      counter ++;
    }
  }
}

{{< / highlight >}}

#### Output.

{{< highlight bash >}}
6:46:45 PM: Executing task 'DaemonThreadDemo.main()'...

> Task :compileJava
> Task :processResources NO-SOURCE
> Task :classes

> Task :DaemonThreadDemo.main()
Hello from daemon thread. Current counter is 1
Hello from daemon thread. Current counter is 2
Hello from daemon thread. Current counter is 3
Hello from daemon thread. Current counter is 4

BUILD SUCCESSFUL in 2s
2 actionable tasks: 2 executed
6:46:48 PM: Task execution finished 'DaemonThreadDemo.main()'.
{{< / highlight >}}