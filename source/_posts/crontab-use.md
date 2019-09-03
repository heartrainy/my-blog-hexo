---
title: crontab使用
date: 2019-08-02 11:00:26
tags:
---

## 命令
```dos
crontab -l   // 查看当前的定时任务
crontab –e   // 修改 crontab 文件.如果文件不存在会自动创建
crontab -r   // 删除 crontab 文件
crontab -ir  // 删除 crontab 文件前提醒用户
systemctl start  crond.service      // 启动服务
systemctl stop  crond.service       // 关闭服务
systemctl reload  crond.service     // 重新载入配置
systemctl restart  crond.service    // 重启服务
systemctl status  crond.service     // 查看服务状态
```

## 说明
```
分  小时  日  月  星期  命令
30  7  8  *  *  ls      // 指定每月8号的7:30分执行ls命令
*/15  *  *  *  *  ls    // 每15分钟执行一次命令[即每个小时的第0、15、30、45、60分钟执行ls命令]
0  */2  *  *  *  ls     // 每隔两小时执行一次ls

*    *    *    *    *    *
-    -    -    -    -    -
|    |    |    |    |    |
|    |    |    |    |    + year [optional]
|    |    |    |    +----- day of week (0 - 7) (Sunday=0 or 7)
|    |    |    +---------- month (1 - 12)
|    |    +--------------- day of month (1 - 31)
|    +-------------------- hour (0 - 23)
+------------------------- min (0 - 59)
```
注意点：
1.星期中0表示周日
2.每隔两小时的时候前面不能为*，为*表示分钟都会执行