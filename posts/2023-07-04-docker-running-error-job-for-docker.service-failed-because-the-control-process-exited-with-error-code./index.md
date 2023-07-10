# docker运行报错Job for docker.service failed because the control process exited with error code的一种原因


<!--more-->
## docker 运行报错

报错提示为：
```
Job for docker.service failed because the control process exited with error code. See "systemctl status docker.service" and "journalctl -xeu docker.service" for details.
```

## 一种原因

添加下载源时候，符号出错。

最后一个地址后不能加逗号，所有逗号均为英文符号。

`/etc/docker/deamon.json`
```
{
"registry-mirrors": [
"https://dockerproxy.com",
"https://docker.nju.edu.cn",
"https://mirror.baidubce.com",
"https://mirror.gcr.io"
]
}
```

---

> 作者: Kingpo  
> URL: https://hugo.111520.xyz/posts/2023-07-04-docker-running-error-job-for-docker.service-failed-because-the-control-process-exited-with-error-code./  

