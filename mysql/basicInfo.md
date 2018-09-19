### 1. 显示基础表定义
```sql
desc arb_settlement_001

```


### 2. 显示详细表定义

``` sql
SELECT
	c.table_schema,
	c.table_name,
	c.column_name,
	c.column_default,
	c.is_nullable,
	c.data_type,
	c.column_type,
	c.column_comment
FROM
	information_schema.`COLUMNS` c
WHERE
	c.table_name = 'arb_settlement_001'

```


