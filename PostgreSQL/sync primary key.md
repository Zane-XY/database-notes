####ERROR: duplicate key violates unique constraint
__cause__: That likely means that the primary key sequence in the table you're working with has somehow become out of sync, likely because of a mass import process (or something along those lines). [ref](http://hcmc.uvic.ca/blogs/index.php?blog=22&p=8105&more=1&c=1&tb=1&pb=1)

__fix__:
```sql
SELECT setval('your_table_id_seq', (SELECT MAX(id) FROM your_table));
```
replace your_table with whatever the table name you are using. And the code above assumes your primary key column name is id.
