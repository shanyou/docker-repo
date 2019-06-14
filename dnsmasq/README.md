dnsmasq
===

[dnsmasq 漏洞](https://www.anquanke.com/post/id/86976)

为了保障线上服务起安全，需要用最新的dnsmasq版本。目前官方版本2.80. 在此基础上制作docker镜像来替代线上对应的服务。

调用方法:
```bash
docker run -p 53:53/tcp -p 53:53/udp shanyou/dnsmasq
```

添加自定义的解析
```bash
docker run -p 53:53/tcp -p 53:53/udp -v dnsmasq.hosts:/etc/dnsmasq.hosts shanyou/dnsmasq 
```