---
layout: post
title: SQL Notes
---

## PostgreSQL

### Check all running queries

```
SELECT query FROM pg_stat_activity WHERE state IN ('idle in transaction', 'active');
```

### Upgrade Version

Make sure you run `ANALYSE` after upgrade the version to update `pg_statistic` which the query planner used.
