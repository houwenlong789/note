### 导出elastic数据到文件中

config.config 文件设置
```
input{
   elasticsearch{
    hosts =>"192.168.4.76"
	index=>"user_detail_information"
	size=>100
    scroll=>"5m"
    docinfo => true
    }
}
output{
 file{
   path => "./a.txt"
   codec => line{ format =>"%{[@metadata][_id]}"
        }
    }
}
```


### 输出到标准流


```
 stdout{
    codec=>json
    }
```
### 输出到Kafka


```
output {
    kafka {
      codec =>json
      bootstrap_servers=>"10.9.35.11:9092"
      topic_id => "ZTO_SV_Migration_es"
    }
}
```



### 步骤

1. 下载logstash
2. 解压缩
3. 创建config.config 文件在 bin下
4. 执行如下命令

```
bin/logstash -f bin/config.config 
```