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
│ nothing │
└─────────┘

D select count(*) from nothing;
┌──────────────┐
│ count_star() │
│    int64     │
├──────────────┤
│            0 │
└──────────────┘
```
