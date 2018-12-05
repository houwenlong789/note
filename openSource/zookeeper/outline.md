### 1. 启动
#### 启动类

```java
ZooKeeperServerMain
```


## 注意事项

1. 使用curator 类库访问 zookeeper 的时候要使用特定的版本，否则连接不上去。

> Curator 2.x.x - compatible with both ZooKeeper 3.4.x and ZooKeeper 3.5.x

> Curator 3.x.x - compatible only with ZooKeeper 3.5.x and includes support for new features such as dynamic reconfiguration, etc.
