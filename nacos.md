## Nacos安装

服务（Service）是Nacos 世界的一等公民。Nacos支持几乎所有主流类型的“服务”的发现、配置和管理。

#### 1.Docker安装Nacos

**拉取镜像**

```bash
docker pull nacos/nacos-server
```

**启动容器并且添加映射**

```bash
docker run -d -p 8848:8848 --env MODE=standalone --name nacos --restart=always nacos/nacos-server
```

**查看容器是否启动**

```bash
docker ps
```

**检查nacos服务是否正常**

```bash
浏览器打开 http://localhost:8848/nacos 用户名密码默认为nacos
```



