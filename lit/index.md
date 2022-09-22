---
title: Development Environment
author: Mark Szepieniec
---

This document captures all the components comprising my preferred development environment.
Its source form is a literal program that builds up a Dockerfile representing that environment in a deterministically reproducible way.
The intention is for this to be portable across Linux distros (maybe incorporating MacOS at a later time) and form a compact docker layer for other images to layer on to.

## Dockerfile

We start the Dockerfile by using the latest `alpine` image as a base image.
Alpine is a minimalistic distribution, which leads to small container images, and its libc implementation is strictly POSIX compliant so installed executables should be highly portable (meaning we can just copy the binary files over to other containers and expect things to work).
``` {.dockerfile #dockerfile file=src/Dockerfile}
FROM alpine:latest
```

Next, we use Alpine's package manager `apk` to install the packages that comprise our development environment.
``` {.dockerfile #dockerfile file=src/Dockerfile}
RUN apk add neovim tmux
```
