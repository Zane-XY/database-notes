Performance
=========

## query log
- long_query_time
- --log-queries-not-using-indexes
- --log-slow-admin-statements
- mysqldumpslow

## Normalization
reduce redundant data

# Table Optimization
- NULLABLE column, MyISAM use extra bit to store NULL, In InnoDB, NULLS take no space.  [ref](http://stackoverflow.com/a/1106577)
- INT instead of BIGINT
- VARCHAR(10) instead of VARCHAR(255)

## Monitor process list
- mysql> show full processlist;

## global tuning options
- table_cache (default 64)
- max_connections (default 100)
