---
layout: post
title: SQL Notes
---

## PostgreSQL

### Check all running queries

```
SELECT query FROM pg_stat_activity WHERE state IN ('idle in transaction', 'active');
```
