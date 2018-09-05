# lnmp-with-docker
docker lnmp PHP开发环境，该环境再Mac使用并调试，linux上稍微修改，很容易启动。

## 安装步骤

###步骤1：安装docker
```
brew cash install docker
```

### 步骤2：安装docker-compose工具
```
brew install docker-compose
```

### 步骤3：进入lnmp-with-docker目录，启动服务组
```
docker-compose up -d

# 学习更多docker-compose
docker-compose --help
```

### 注意事项：
1. 关于volumes:/private/var/db/timezone/tz/2018e.1.0/zoneinfo/Asia/Shanghai，这是我时区存放地址。你需要根据实际情况，修改。
2. 关于volumes:~/Work，这是我项目的目录，你需要改成你自己的
3. 关于IP设置、Mysql密码、PORT映射管理，你都可以安装自己习惯配置
4. ！！！开发环境使用，不要用再生产环境

## 推荐一个 docker 工具
1. portainer
```
# 拉取镜像
docker pull portainer/portainer
# 启动容器（我的9000端口已经被使用了。这里用1900做映射容器9000）
docker run -d -p 1900:9000 -v --name PORTAINER /var/run/docker.sock:/var/run/docker.sock portainer/portainer
```