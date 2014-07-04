Index
=========

## considerations before creating index
base on the data (prefix index) and query(multi column index)

## supported syntax 
```sql
CREATE [UNIQUE|FULLTEXT|SPATIAL] INDEX index_name
    [index_type]
    ON tbl_name (index_col_name,...)
    [index_type]

index_col_name:
    col_name [(length)] [ASC | DESC]

index_type:
    USING {BTREE | HASH}
```
## prefix index
Index on the whole column is not always necessary.
- Indexes can be created that use only the leading part of column values, using col_name(length) syntax to specify an index prefix length

## multi-column index
- An index may consist of up to 16 columns.
- Index values are formed by concatenating the values of the given columns.
- column oder in query should match column index order
- works for partial column query
- works even in order by [ref](http://stackoverflow.com/q/12728832)
