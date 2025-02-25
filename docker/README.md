# Docker

此目录包含与Docker相关的配置文件和说明文档。Docker用于创建、部署和运行应用程序的容器化环境。

## 目录结构
- `Dockerfile`: 用于构建Docker镜像的配置文件
- `scripts/`: Docker相关的辅助脚本

## 使用说明
1. 确保已安装Docker和Docker Compose
2. shell 脚本需要增加执行权限

## 相关脚本介绍
- [docker安装脚本](./scripts/install_docker.sh)
    ```bash
    install_docker.sh -s docker --mirror Aliyun 
    ```
- [构建支持量子算法的openssl容器](./dockerfile/Dockerfile_openssl3-oqs)
    ```bash
    docker build -t openssl3-oqs:latest -f ./dockerfile/Dockerfile_openssl3-oqs .
    ```
- [配置http代理](./scripts/http-proxy.conf)
    ```bash
    sudo mkdir -p /etc/systemd/system/docker.service.d
    sudo cp ./scripts/http-proxy.conf /etc/systemd/system/docker.service.d/http-proxy.conf
    sudo systemctl daemon-reload
    sudo systemctl restart docker
    ```
