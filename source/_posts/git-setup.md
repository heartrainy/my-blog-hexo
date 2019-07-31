---
title: centos7安装git
date: 2019-07-31 14:11:56
tags:
---

1.查询是否安装了git

```dos
rpm -qa|grep git
```

2.如果安装了则卸载

```dos
rpm -e --nodeps git  或者  rpm -e git
```

3.yum安装git

```dos
yum install git
```
