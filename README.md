# NoDB
A high-performance, in-memory, git-backed OLAP database (of nothing).

Because the best database infrastructure is no database infrastructure.


# Using NoDB with [DuckDB](https://duckdb.org/)

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


D from nothing;
┌────────┐
│ niets  │
│ int64  │
├────────┤
│ 0 rows │
└────────┘


D from nichts select count(*) as notmuch;
┌─────────┐
│ notmuch │
│  int64  │
├─────────┤
│       0 │
└─────────┘


D from nichts;
┌────────┐
│ niets  │
│ int64  │
├────────┤
│ 0 rows │
└────────┘
```


# Cross-Engine Support with [DataFusion](https://datafusion.apache.org/)


```
-DataFusion CLI v44.0.0

> create external table rien stored as parquet location 'https://github.com/jakthom/nodb/raw/refs/heads/main/nada.parquet';
0 row(s) fetched.
Elapsed 0.638 seconds.

> show tables;
+---------------+--------------------+-------------+------------+
| table_catalog | table_schema       | table_name  | table_type |
+---------------+--------------------+-------------+------------+
| datafusion    | public             | rien        | BASE TABLE |
| datafusion    | information_schema | tables      | VIEW       |
| datafusion    | information_schema | views       | VIEW       |
| datafusion    | information_schema | columns     | VIEW       |
| datafusion    | information_schema | df_settings | VIEW       |
| datafusion    | information_schema | schemata    | VIEW       |
| datafusion    | information_schema | routines    | VIEW       |
| datafusion    | information_schema | parameters  | VIEW       |
+---------------+--------------------+-------------+------------+

> select count(*) as nil from rien;
+-----+
| nil |
+-----+
| 0   |
+-----+
1 row(s) fetched.
Elapsed 0.135 seconds.
```


# NoDB Roadmap

* NoDB will have full support of [Vortex](https://github.com/spiraldb/vortex) as a file format, for high-performance random-access reads and scans of nothing.

* NoDB will experimentally support NoLLM, NoML, NoAI in the very near future.

* NoDB is current NoGovernance, but plans to support NoSecurity as well.

* No DR is on the roadmap (though proprietary and only provided by our NoBYOC offering).


# License

NoDB IP is protected via use of a permissive copy-left license.

However, if you plan to make it commercially available as no-IaaS please give us no credit.
