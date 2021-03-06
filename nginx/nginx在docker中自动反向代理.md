## nginx在docker中自动反向代理

> http://jasonwilder.com/blog/2014/03/25/automated-nginx-reverse-proxy-for-docker/

一个反向代理服务器通常在其它服务器的前面，用以提供额外web服务器自身不能提供的功能。比如说，一个反向代理服务器可以提供SSL终端、负载均衡、路由请求、缓存、压缩或A/B测试。当我们运行web服务在docker容器中时，nginx可以运行在容器的前面，这对于简单部署来说很有用。

## 为什么对docker使用反向代理

docker容器随机分配IP和ports，其生成很多来自于客户端的复杂地址。默认的，ips和ports是本地私有的且不能被外部访问，除非它们绑定了host。

绑定容器的本地端口能防止多容器运行在同一个主机。例如，现在只有一个容器能绑定80端口，当不停机的推出新的容器版本这是很复杂的，因为旧的容器必须在新的容器启动之前停止。反向代理能够帮组我们解决这个问题并且改善0停机部署。

