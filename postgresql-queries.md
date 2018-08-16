# Postgres

## databases by size

dump database names and sizes:

```sql
SELECT datname, pg_size_pretty(size) FROM (
  SELECT datname, pg_database_size(datname) AS size
  FROM pg_database
  ORDER BY size DESC
) AS sizes;
```


list database sizes, with owner name and access:

```sql
SELECT
    d.datname AS Name,
    pg_catalog.pg_get_userbyid(d.datdba) AS Owner,
    CASE WHEN pg_catalog.has_database_privilege(d.datname, 'CONNECT')
        THEN pg_catalog.pg_size_pretty(pg_catalog.pg_database_size(d.datname))
        ELSE 'No Access'
    END AS Size
FROM pg_catalog.pg_database d
    ORDER BY
    CASE WHEN pg_catalog.has_database_privilege(d.datname, 'CONNECT')
        THEN pg_catalog.pg_database_size(d.datname)
        ELSE NULL
    END DESC;
```


## tables by size

Lists tables and table-size, ordered by size, in the current database.

```sql
SELECT nspname || '.' || relname AS "relation",
    pg_size_pretty(pg_relation_size(C.oid)) AS "size"
  FROM pg_class C
  LEFT JOIN pg_namespace N ON (N.oid = C.relnamespace)
  WHERE nspname NOT IN ('pg_catalog', 'information_schema')
  ORDER BY pg_relation_size(C.oid) DESC
  LIMIT 20;
```


## connections

```sql
SELECT * FROM pg_stat_activity;
SELECT pid, datname, usename, client_addr, query_start, state FROM pg_stat_activity;
```


## locks

```sql
SELECT relation::regclass, * FROM pg_locks WHERE NOT GRANTED;
```


## cache hit rate

```sql
SELECT
  sum(heap_blks_read) as heap_read,
  sum(heap_blks_hit)  as heap_hit,
  sum(heap_blks_hit) / (sum(heap_blks_hit) + sum(heap_blks_read)) as ratio
FROM
  pg_statio_user_tables;
```


## index usage

```sql
SELECT 
  relname, 
  100 * idx_scan / (seq_scan + idx_scan) percent_of_times_index_used, 
  n_live_tup rows_in_table
FROM 
  pg_stat_user_tables
WHERE 
    seq_scan + idx_scan > 0 
ORDER BY 
  n_live_tup DESC;
```
