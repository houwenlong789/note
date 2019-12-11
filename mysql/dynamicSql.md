
### 动态sql书写格式
```sql
set @SQL_FOR_SELECT := 'select *From customer_user_tag_0000';   -- 拼接查询sql语句

set @sql := @SQL_FOR_SELECT;

PREPARE stmt FROM @sql;         -- 预处理动态sql语句

EXECUTE stmt ;                        -- 执行sql语句

deallocate prepare stmt;      -- 释放prepare
```