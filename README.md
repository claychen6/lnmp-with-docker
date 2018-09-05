# lnmp-with-docker
docker lnmp PHP开发环境


# docker 小工具
1. portainer
```
# 拉取镜像
docker pull portainer/portainer
# 启动容器（我的9000端口已经被使用了。这里用1900做映射容器9000）
docker run -d -p 1900:9000 -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer
```