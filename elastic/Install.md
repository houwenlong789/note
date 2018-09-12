# 安装 centos 版
 参见文档 https://www.elastic.co/guide/en/elasticsearch/reference/current/zip-targz.html
 
 # 安装 5.5.1 遇到问题集锦
 1 . 默认情况下在外部是无法访问 Elastic search 的，仅仅映射到内部，没有映射到外部，因此需要添加
 
 
```
# 配置到外部映射
 network.bind_host: 10.9.35.11
```
2 一些配置信息
http://www.jianshu.com/p/4c6f9361565b

