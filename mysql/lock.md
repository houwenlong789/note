
# 常用
## 共享锁和排它锁

> 共享锁

```sql

START TRANSACTION ;
select *From arb_auto_missing_result 
where bill_code = '1234'  lock in share mode;
commit;

```

> 排它锁

## 意向共享锁 意向排它锁
>意向共享锁 IS

>意向排它锁 IX

## 记录锁 Record Locks

## 间隙锁 Gap Locks

## 事务信息

>通过连接方式
```sql
SELECT
  r.trx_id waiting_trx_id,
  r.trx_mysql_thread_id waiting_thread,
  r.trx_query waiting_query,
  b.trx_id blocking_trx_id,
  b.trx_mysql_thread_id blocking_thread,
  b.trx_query blocking_query
FROM       information_schema.innodb_lock_waits w
INNER JOIN information_schema.innodb_trx b
  ON b.trx_id = w.blocking_trx_id
INNER JOIN information_schema.innodb_trx r
  ON r.trx_id = w.requesting_trx_id;
```
> 通过视图方式
```sql
SELECT
  waiting_trx_id,
  waiting_pid,
  waiting_query,
  blocking_trx_id,
  blocking_pid,
  blocking_query
FROM sys.innodb_lock_waits;

```
# 不常用



## 参考文献
[地址](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html)
