---
layout: post
title: Python Notes
---

### Virtual Environment:

#### To setup virtual environment:

```
virtualenv --no-site-packages env --python=python3
. env/bin/activate
```

#### To disable virtual environment

```
deactivate
```

#### To set python project root

```
export PYTHONPATH=$(pwd)
```

#### To install requirements

```
env/bin/pip install -r requirements.txt
```

#### To freeze requirements

```
env/bin/pip freeze freeze > requirements.txt
```

### Linter:

```
flake8 ./src/py
autopep8 --in-place --aggressive --recursive --max-line-length 120 ./src/py
```
