[pytorch Docker Hub](https://hub.docker.com/r/pytorch/pytorch)
[使用文档](https://docs.docker.com/desktop/setup/sign-in/#whats-next)
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