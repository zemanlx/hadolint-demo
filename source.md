# bringing light\\into **Docker**files
# base **image**
```Dockerfile
FROM debian
```
```Dockerfile
FROM debian:latest
```
```Dockerfile
FROM debian:9
```
```Dockerfile
FROM debian@sha256:f7ca2200...
```
```Bash
docker pull debian:9
  9: Pulling from library/debian
  Digest: sha256:f7ca2200...
  Status: Image is up to date for debian:9
```
```Dockerfile
docker inspect \
  --format='{{.RepoDigests}}' \
  debian:9
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
```Dockerfile
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
# github**.**com**/**hadolint**/**hadolint
