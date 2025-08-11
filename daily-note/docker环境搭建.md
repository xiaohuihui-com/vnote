# docker 环境搭建

[toc]

```shell
sudo apt-get update
# 安装一些必要的软件包，以便 apt 可以通过 HTTPS 使用仓库
sudo apt-get install -y apt-transport-https ca-certificates curl software-properties-common
```

```shell
# 添加 Docker 的官方 GPG 密钥
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

# 添加 Docker APT 仓库
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

# 再次更新软件包索引
sudo apt-get update

# 安装 Docker CE
sudo apt-get install -y docker-ce

# 验证 Docker 是否正确安装
sudo docker --version

# 安装docker compose
# 下载最新版本的 Docker Compose（请检查是否有更新版本）
sudo curl -L "https://github.com/docker/compose/releases/download/$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep -Po '"tag_name": "\K.*\d')" /usr/local/bin/docker-compose

# 应用可执行权限给二进制文件
sudo chmod +x /usr/local/bin/docker-compose

# 验证安装是否成功
docker-compose --version
- sudo apt-get update
- sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
- sudo apt-get update
- curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
- sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
- sudo apt-get update
- sudo apt-get install docker-ce
- sudo docker --version

sudo vim /etc/docker/daemon.json
{
    "registry-mirrors": [
		"https://docker.1ms.run",
        "https://docker.xuanyuan.me",
    ]
}

sudo usermod -aG docker $USER
newgrp docker
sudo systemctl daemon-reexec
sudo systemctl restart docker
sudo docker info

- sudo apt-get update
- sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
- curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
- sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
- sudo apt-get update
- sudo apt-get install docker-ce
- sudo docker --version

sudo vim /etc/docker/daemon.json
{
    "registry-mirrors": [
        "https://docker.xuanyuan.me",
        "https://docker.xuanyuan.me",
        "https://docker.1ms.run",
        "https://docker.xuanyuan.me"
    ]
}
sudo systemctl restart docker
sudo docker info
docker pull mysql:5.7
docker run --name mysql57 -v /my/own/datadir:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=1234 -d -p 3306:3306 mysql:5.7



# 安装mysql
docker pull mysql:5.7
docker run --name mysql57 -v /my/own/datadir:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -d -p 3306:3306 mysql:5.7
# 安装redis
docker pull redis
docker run --name redis -p 6379:6379 -d redis
docker run --name redis -p 6379:6379 -d redis redis-server --requirepass "123456"
# 安装elasticsearch
docker pull docker.elastic.co/elasticsearch/elasticsearch:8.11.3
docker run -d --name elasticsearch -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" -e "ES_JAVA_OPTS=-Xms512m -Xmx512m" docker.elastic.co/elasticsearch/elasticsearch:8.11.3
# 安装nginx
docker pull nginx
docker run --name nginx -p 8080:80 -d nginx

# 安装jdk17
docker pull openjdk:17

```
