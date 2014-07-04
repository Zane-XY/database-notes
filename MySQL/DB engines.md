Engine
=========

#InnoDB
- InnoDB uses clustered indexes
  The length of the PRIMARY KEY is extremely important
- The rows are always dynamic
  Using VARCHAR instead of CHAR is almost always better
- Maintenance operations needed after 
 Many UPDATE/DELETE operations 
 The pages can become underfilled

## MyISAM VS InnoDB
InnoDB offers:

- ACID transactions
- row-level locking
- foreign key constraints
- automatic crash recovery
- table compression (read/write)
- spatial data types (no spatial indexes)

MyISAM offers:

- fast COUNT(*)s (when WHERE, GROUP BY, or JOIN is not used)
- full text indexing
- smaller disk footprint
- very high table compression (read only)
- spatial data types and indexes (R-tree)    

To summarize:

Frequent reading, almost no writing   => MyISAM
Full text search in MySQL <= 5.5      => MyISAM

In all other circumstances, InnoDB is usually the best way to go.

## InnoDB Performance Tuning Tips [ref](http://dev.mysql.com/doc/refman/5.0/en/innodb-tuning.html)
- InnoDB stores PK as (clustered index](http://dev.mysql.com/doc/refman/5.0/en/innodb-index-types.html), make PK shorter can save disk space.
- InnoDB must flush the log to disk at each transaction commit, so keep your transactions tight and short.
