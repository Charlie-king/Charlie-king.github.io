# kindle联网异常的解决方法


<!--more-->
使用kindle时，有时突然遇到不能联网的问题，提示以下信息。

> 您的kindle已连接WiFi网络，但无法连接互联网。请联系您的互联网服务供应商，寻求支持。

## 解决方法
- **法1：** 数据线连接电脑在Kindle U盘根目录建立一个空白文件夹（不是文件），名为`WIFI_NO_NET_PROBE`（不含引号），重启。原理阻止wifi进行网络连接测试。

- **法2：** 路由器给kindle设备分配静态ip（末段不要超100），或DHCP得到的内网IP 192.168.1.*，（*分配的动态ip不要超过100），dns改为谷歌的8.8.8.8或8.8.4.4。

建议直接用法2。

---

> 作者: Kingpo  
> URL: https://hugo.111520.xyz/posts/2022-09-06-kindle-networking-exception/  

