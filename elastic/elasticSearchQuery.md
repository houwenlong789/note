# 查询具体用户信息

```
/user_detail_information/userbehaviorinformation/18229153348

```

# 统计记录数

```
/user_detail_information/_count
```

# 根据条件搜索


```
/user_detail_information/_search
```

```
{
    "from": 0,
    "size": 1000,
    "explain": true,
    "query": {
        "range": {
            "creationTime": {
                "gte": "now-8h"
            }
        }
    }
}
```

# 按照标签搜索


```
{
    "query" : {
    
                "terms" : { 
                    "addresses.tags" : [1]
                }
         
    }
}
```





