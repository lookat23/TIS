# 如何解决Nginx反向代理时出现504（网关超时）

[stackoverflow连接](https://stackoverflow.com/questions/24453388/nginx-reverse-proxy-causing-504-gateway-timeout)

 最根本的方法是找出反向代理的目标服务器为何一直不返回，也可以先在 `nginx.conf`把超时时间通过以下配置来延长看能不能解决问题：

```nginx
proxy_connect_timeout       300;
proxy_send_timeout          300;
proxy_read_timeout          300;
send_timeout                300;
```

