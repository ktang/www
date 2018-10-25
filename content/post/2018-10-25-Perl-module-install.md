---
title: "Perl Module Install"
author: "Kai Tang"
date: 2018-10-25T15:30
categories: ["Perl"]
tags: ["R Markdown", "Perl", "Module"]
---

```{perl eval=FALSE}
perl -MCPAN -e shell
>o conf mbuildpl_arg "--install_base ~/opt"
>o conf makepl_arg "PREFIX=~/opt"
```

OR

download tar.gz to
local directory and then

```{perl eval=FALSE}
perl Makefile.PL PREFIX=~/opt
make 
make test
make install
```

```{perl eval=FALSE}
perl Build.PL --install_base ~/opt
perl Build
perl Build test
perl Build install
```
