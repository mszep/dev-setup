---
title: Development Environment
author: Mark Szepieniec
---

This document captures all the components comprising my preferred development environment.
Its source form is a literal program that builds up a Dockerfile representing that environment in a deterministically reproducible way.
The intention is for this to be portable across Linux distros (maybe incorporating MacOS at a later time) and form a compact docker layer for other images to layer on to.

``` {.dockerfile #dockerfile file=src/Dockerfile}
FROM alpine:latest
RUN apk add neovim tmux
```
