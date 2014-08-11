Pagination
======

#####the old ways
```sql
select * from T where ... order by ... limit m,n
```

##### Why `limit m,n` is bad?
- performs really bad when table is large
- user probably doesn't care about which page he's viewing

##### pagination without offset
- we want out queries to hit our indexes as much as possible
- using where and limit n
- store view range in client side

