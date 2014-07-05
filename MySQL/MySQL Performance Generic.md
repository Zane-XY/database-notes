Performance
=========

## query log
- set `long_query_time=1` and `slow_query_log=1`
- --log-queries-not-using-indexes
- --log-slow-admin-statements
- mysqldumpslow

## Normalisation
reduce redundant data

- 1NF:  all attributes are single-valued.
- 2NF:  it is in 1NF and all non-key attributes are functionally dependent on the table’s entire primary key.
- 3NF:  it is in 2NF and no transitive dependencies exist.

## Table Optimization
- NULLABLE column, MyISAM use extra bit to store NULL, In InnoDB, NULLS take no space.  [ref](http://stackoverflow.com/a/1106577)
- INT instead of BIGINT
- VARCHAR(10) instead of VARCHAR(255)

## Monitor process list
- mysql> show full processlist;

## global tuning options
- table_cache (default 64)
- max_connections (default 100)
