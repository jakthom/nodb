# NoDB
A high-performance, in-memory, git-backed OLAP database (of nothing).

Because the best database infrastructure is no database infrastructure.


# Connecting to NoDB with [DuckDB](https://duckdb.org/)

```
D attach 'https://github.com/jakthom/nodb/raw/refs/heads/main/catalog' as nodb;
100% ▕████████████████████████████████████████████████████████████▏


D use nodb;


D show tables;
┌─────────┐
│  name   │
│ varchar │
├─────────┤
│ nichts  │
│ nothing │
└─────────┘


D from duckdb_views() select database_name, schema_name, view_name where not internal;
┌───────────────┬─────────────┬───────────┐
│ database_name │ schema_name │ view_name │
│    varchar    │   varchar   │  varchar  │
├───────────────┼─────────────┼───────────┤
│ nodb          │ main        │ nichts    │
└───────────────┴─────────────┴───────────┘


D select * from nothing;
┌────────┐
│ niets  │
│ int64  │
├────────┤
│ 0 rows │
└────────┘


D select count(*) from nichts;
┌──────────────┐
│ count_star() │
│    int64     │
├──────────────┤
│            0 │
└──────────────┘


D select * from nichts;
┌────────┐
│ niets  │
│ int64  │
├────────┤
│ 0 rows │
└────────┘
```


# Cross-Engine Support with [DataFusion](https://datafusion.apache.org/)


```
DataFusion CLI v44.0.0
> select * from 'https://github.com/jakthom/nodb/raw/refs/heads/main/nada.parquet';
+-------+
| niets |
+-------+
+-------+
0 row(s) fetched.
Elapsed 1.091 seconds.
```


# License

NoDB IP is protected via use of a permissive copy-left license.

If you make it commercially available as no-IaaS please give us no credit.
