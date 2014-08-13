Serial Types
======
The data types smallserial, serial and bigserial are not true types, but merely a notational
convenience for creating unique identifier columns (similar to the AUTO_INCREMENT property supported
by some other databases). In the current implementation, specifying:

```sql
CREATE TABLE tablename (
colname SERIAL
);
```
is equivalent to specifying:

```sql
CREATE SEQUENCE tablename_colname_seq;
CREATE TABLE tablename (
colname integer NOT NULL DEFAULT nextval(’tablename_colname_seq’)
);
ALTER SEQUENCE tablename_colname_seq OWNED BY tablename.colname;
```
