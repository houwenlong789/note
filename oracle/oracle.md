### 统计oracle 字段，表信息

```
select  cc.TABLE_NAME,cm.COMMENTS, 
ccm.COLUMN_NAME,
 c.DATA_TYPE, c.DATA_LENGTH, c.NULLABLE,ccm.COMMENTS from all_col_comments cc
join all_tab_cols c on cc.TABLE_NAME = c.TABLE_NAME and cc.COLUMN_NAME = c.COLUMN_NAME
 left join all_tab_comments cm on cc.TABLE_NAME = cm.TABLE_NAME
 left join all_col_comments ccm on ccm.TABLE_NAME = cc.TABLE_NAME and ccm.COLUMN_NAME = cc.COLUMN_NAME
 where  cc.OWNER = 'ZTZC' 
 and cc.TABLE_NAME like 'ARBITRATION_APPLY%'
```
