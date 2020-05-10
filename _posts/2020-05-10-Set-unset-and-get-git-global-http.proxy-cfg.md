---
title:  "Set, unset and get git global http.proxy configuration"
date:   2020-05-10 16:56:00
summary: cli
---

## Set

```bash
git config --global http.proxy http://proxyusr:proxypwd@proxy.server.com:80
```

## Unset

```bash
git config --global --unset http.proxy
```

## Get

```bash
git config --global --get http.proxy
```

---
> Good, better, best. Never let it rest. 'Til your good is better and your better is best.
> <small>- [St. Jerome](https://www.brainyquote.com/quotes/st_jerome_389605)</small>