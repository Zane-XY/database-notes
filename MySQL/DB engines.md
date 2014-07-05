Engine
=========

## InnoDB Performance Tuning Tips [ref](http://dev.mysql.com/doc/refman/5.0/en/innodb-tuning.html)
- InnoDB stores PK as (clustered index](http://dev.mysql.com/doc/refman/5.0/en/innodb-index-types.html), make PK shorter can save disk space.
- InnoDB must flush the log to disk at each transaction commit, so keep your transactions tight and short.


## MyISAM VS InnoDB [ref](http://www.rackspace.com/knowledge_center/article/mysql-engines-myisam-vs-innodb)

<table><tbody><tr><th>MyISAM</th>
<th>Innodb</th>
</tr><tr><td>Not *ACID compliant and non-transactional</td>
<td>*ACID compliant and hence fully transactional with ROLLBACK and COMMIT and support for Foreign Keys</td>
</tr><tr><td>MySQL 5.0 Default Engine</td>
<td>MySQL 5.5+ default engine</td>
</tr><tr><td>Requires full repair/rebuild of indexes/tables</td>
<td>Auto recovery from crash via replay of logs</td>
</tr><tr><td>Changed Db pages written to disk instantly</td>
<td>Dirty pages converted from random to sequential before commit and flush to disk</td>
</tr><tr><td>No ordering in storage of data</td>
<td>Row data stored in pages in PK order</td>
</tr><tr><td>Table level locking</td>
<td>Row level locking</td>
</tr>
<tr><td>no foreign key support (planned to implement)</td>
<td>has foreign key</td>
</tr>
</tbody></table>


## Which one to use?

- MyISAM: primary reading, full text support for versions below 5.5
- choose InnoDB in most of the cases


