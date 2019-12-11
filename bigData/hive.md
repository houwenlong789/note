#常用hivesql汇总
### 建表

```sql
create table tmp.tag_result_all_aggregate
(
phone STRING  comment '手机号',
tag_info STRING comment 'json字符串，格式为[{"tag_code":"","probability":""}]'
)comment '聚合所有的标签'
partitioned by (ds string comment '统计日期')
ROW FORMAT DELIMITED FIELDS
TERMINATED BY '\001'
LINES TERMINATED BY '\n'
stored as orc;
```

### 插入语句
> 插入分区数据
```sql
insert into table tmp.tag_result_all partition (ds='20190719')(phone, tag)  select *From tmp.tag_temp
```