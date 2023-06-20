# Ubuntu输入su认证失败的解决方法


<!--more-->
## linux的权限和目录简述

linux系统是用户权限管理非常明确，目录结构是一个根目录的目录树。每个文件有所有者u，所在组g，其他组o，不同组对文件处理权限有读r写w执行x。

```
/
├── bin -> usr/bin
├── boot
├── cdrom
├── dev
├── etc
├── home  #【用户在此目录下】
├── lib -> usr/lib
├── lib32 -> usr/lib32
├── lib64 -> usr/lib64
├── libx32 -> usr/libx32
├── lost+found
├── media
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin -> usr/sbin
├── snap
├── srv
├── sys
├── tmp
├── usr
└── var


```

## su认证失败

Ubuntu安装时默认创建的是普通账户，所有账户位于home目录下，每个账户只对自己及以下的文件夹有所有权限，超级管理员root默认是锁定的。

因此在终端中如果直接操作home外的其他目录会提示权限不够，输入su切换，输入密码会提示认证失败，此时需要先开启超级管理员。

1. 终端输入`sudo passwd`
2. 输入系统安装时设置的密码
3. 输入超管root的密码，重复两次
4. 完成，此时已经开启root账号

---

> 作者: Kingpo  
> URL: https://hugo.111520.xyz/posts/2023-05-10-ubuntu-su/  

