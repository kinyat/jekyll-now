---
layout: post
title: Docker Notes
---

### Stop all containers

```
docker stop $(docker ps -a -q)
```

### Remove all containers

```
docker rm $(docker ps -a -q)
```

### Restart Docker

```
sudo systemctl restart docker 
```
