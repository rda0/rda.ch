---
layout: post
title: 'Install Python from source'
tags: [linux,python]
---

Sometimes you need a Python version not available by your distribution.
This guide shows how to build a complete Python environment from source.

Distribution: Ubuntu 20.04

<!--more-->

## Install dependencies

Install the required packages to build Python (requires root):

```bash
apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev wget
```

## Build Python

The rest of the build process can be done as a regular user.

```bash
wget https://www.python.org/ftp/python/3.7.9/Python-3.7.9.tgz
tar -xzf Python-3.7.9.tgz
cd Python-3.7.9
./configure --prefix=/path/to/install --enable-optimizations
make
make install
```

## Set up a venv and use it

```bash
cd /path/to/install
bin/python3 --version
bin/python3 -m pip --version
bin/python3 -m venv env
env/bin/pip install <module>
env/bin/python3
>>> import <module>
```

## Alternatively install Python using pyenv

Install dependencies:

```bash
apt install --no-install-recommends make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
```

Install Python using [pyenv](https://github.com/pyenv/pyenv):

```bash
git clone https://github.com/pyenv/pyenv.git pyenv
cd pyenv
src/configure && make -C src
export PYENV_ROOT="/path/to/pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
pyenv install 3.7.9
versions/3.7.9/bin/python3 --version
```
