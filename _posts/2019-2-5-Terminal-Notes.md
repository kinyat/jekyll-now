---
layout: post
title: Terminal Notes
---

### Replace string in multiple files:

```sh
find . -type f -name "*.txt" -print0 | xargs -0 sed -i "s/foo/bar/g"
```

### Read .env file and run command:

```sh
env $(cat .env | tr "\\n" " ") yarn start
```
