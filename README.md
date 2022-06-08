# Apache ZooKeeper 源码注释

主要的注释存在 server 包下面

包含：

1. 启动流程的 leader 选举
2. ZAB 协议的具体实现


阅读中间件源码的核心关注点：

* 并发编程
* 网络IO编程
* 分布式一致性协议的实现


阅读的源码的方法：

- 抓住主线，一开始不要关心 if 逻辑，一般 if 之外一定会执行的，以及 finally 里面的代码都是非常关键的。还有什么start 开头的代码。
- 阅读的时候一定要记住自己进来这里面是要找什么，就找有对应含义的方法调用，否则就会迷路
- 阅读一定要画思维导图，否则过段时间就完全换回去了， 有图的话就可以快速回忆起来，并且在图上标记一些自己觉得重要的东西。


奥利给！！！

---


![alt text](https://zookeeper.apache.org/images/zookeeper_small.gif "ZooKeeper")

For the latest information about Apache ZooKeeper, please visit our website at:

http://zookeeper.apache.org/

and our wiki, at:

https://cwiki.apache.org/confluence/display/ZOOKEEPER

## Packaging/release artifacts

Either downloaded from https://zookeeper.apache.org/releases.html or
found in zookeeper-assembly/target directory after building the project with maven.

apache-zookeeper-[version].tar.gz

    Contains all the source files which can be built by running:
    mvn clean install

    To generate an aggregated apidocs for zookeeper-server and zookeeper-jute:
    mvn javadoc:aggregate
    (generated files will be at target/site/apidocs)

apache-zookeeper-[version]-bin.tar.gz

    Contains all the jar files required to run ZooKeeper
    Full documentation can also be found in the docs folder
As of version 3.5.5, the parent, zookeeper and zookeeper-jute artifacts
are deployed to the central repository after the release
is voted on and approved by the Apache ZooKeeper PMC:

https://repo1.maven.org/maven2/org/apache/zookeeper/zookeeper/

## Java 8

If you are going to compile with Java 1.8, you should use a
recent release at u211 or above.

## Contributing

We always welcome new contributors to the project! See [How to Contribute](https://cwiki.apache.org/confluence/display/ZOOKEEPER/HowToContribute) for details on how to submit patch through pull request and our contribution workflow.
