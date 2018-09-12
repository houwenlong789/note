# 安装配置

## 遇到的坑
1 创建topic 失败 
 需要设置： bin/zookeeper-server-start.sh config/zookeeper.properties 后台运行，在后面加 & 参数
 
## 服务器上开启客户端访问

```
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
```

注意：localhost 要换成ip ，否则报

```
WARN Connection to node -1 could not be established. Broker may not be available. (org.apache.kafka.clients.NetworkClient)

```
