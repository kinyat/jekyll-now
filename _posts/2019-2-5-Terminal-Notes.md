---
layout: post
title: Terminal Notes
---

### Replace string in multiple files:

```shell
find . -type f -name "*.txt" -print0 | xargs -0 sed -i "s/foo/bar/g"
```
