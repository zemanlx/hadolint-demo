# bringing light\\into **Docker**files
# base **image**
```Dockerfile
FROM alpine
```
```Dockerfile
FROM alpine:latest
```
```Dockerfile
FROM alpine:3.7
```
```Dockerfile
FROM alpine@sha256:7b848083...
```
```Dockerfile
docker inspect \
  --format='{{.RepoDigests}}' \
  alpine:3.7
```
# apt-get
```Dockerfile
RUN apt-get update
RUN apt-get upgrade
```
```Dockerfile
RUN apt-get update \
 && apt-get upgrade
```
```Dockerfile
RUN apt-get update \
 && apt-get install -y curl git
```
```Dockerfile
RUN apt-get update \
 && apt-get install --no-install-recommends -y \
    curl \
    git
```
```Dockerfile
RUN apt-get update \
 && apt-get install --no-install-recommends -y \
    curl \
    git \
 && rm -rf /var/lib/apt/lists/*
```
```Bash
RUN apt-get update \
 && apt-get install --no-install-recommends -y \
    curl=7.52.1-5+deb9u4 \
    git=1:2.11.0-3+deb9u2 \
 && rm -rf /var/lib/apt/lists/*
```
```Dockerfile
RUN apt-get update \
 && apt-get install --no-install-recommends -y \
    curl=7.52.* \
    git=1:2.11.* \
 && rm -rf /var/lib/apt/lists/*
```
# ADD
```Dockerfile
ADD http://vlasto.com/big.tar.xz /cool/
```
```Dockerfile
ADD big.tar.xz /cool/
```
```Dockerfile
ADD http://vlasto.com/big.tar.xz /cool/
RUN tar -xJf /cool/big.tar.xz -C /cool
RUN rm -rf /cool/big.tar.xz
```
```Dockerfile
RUN mkdir -p /cool \
 && curl -SL http://vlasto.com/big.tar.xz \
 |  tar -xJC /cool
```
# enough
# ha**do**lint
# **shell**check
```Dockerfile
FROM debian

RUN apt-get update \
 && apt-get upgrade
```
```Bash
Dockerfile:1 DL3006 Always tag the version of an image explicitly
Dockerfile:3 DL3005 Do not use apt-get upgrade or dist-upgrade
Dockerfile:3 DL3009 Delete the apt-get lists after installing something
```
- TTY
```JSON
[
  {
    "line": 1,
    "code": "DL3006",
    "message": "Always tag the version of an image explicitly",
    "column": 1,
    "file": "Dockerfile",
    "level": "warning"
  },
  {
    "line": 3,
    "code": "DL3005",
    "message": "Do not use apt-get upgrade or dist-upgrade",
    "column": 1,
    "file": "Dockerfile",
    "level": "error"
  },
  {
    "line": 3,
    "code": "DL3009",
    "message": "Delete the apt-get lists after installing something",
    "column": 1,
    "file": "Dockerfile",
    "level": "info"
  }
]
```
- JSON
```XML
&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;checkstyle version="4.3"&gt;
  &lt;file name="Dockerfile"&gt;
    &lt;error line="1" column="1" severity="warning" message="Always tag the version of an image explicitly" source="DL3006"/&gt;
    &lt;error line="3" column="1" severity="error" message="Do not use apt-get upgrade or dist-upgrade" source="DL3005"/&gt;
    &lt;error line="3" column="1" severity="info" message="Delete the apt-get lists after installing something" source="DL3009"/&gt;
  &lt;/file&gt;
&lt;/checkstyle&gt;
```
- XML - checkstyle
# CI
# static binary*
# linux\\darwin(osx)\\windows
# docker image
# Atom\\Sublime Text 3\\(Neo)Vim
# ![](https://user-images.githubusercontent.com/18702153/33764234-7abc1f24-dc0b-11e7-96b6-4f08207b6950.png)
# github**.**com**/**hadolint**/**hadolint
