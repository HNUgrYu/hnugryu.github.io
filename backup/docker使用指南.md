[pytorch Docker Hub](https://hub.docker.com/r/pytorch/pytorch)
[使用文档](https://docs.docker.com/desktop/setup/sign-in/#whats-next)
# 常用指令
更改后重新启动
```
sudo systemctl start docker
sudo systemctl enable docker
docker --version
```
拉取文件
`docker pull <image-name>:<tag>`
根据镜像创建容器
`docker run -it --name pytorch-container pytorch/pytorch`
查看容器
`docker ps -a`
退出容器
`exit`
[docker守护进程开启](https://cloud.tencent.com/developer/ask/sof/106366605)
[docker无法拉取](https://www.cnblogs.com/liujunjun/p/18546650)
# pycharm专业版的docker配置
1. 不要使用容器，直接从镜像生成docker配置
