# 4.7 统一环境

为了使所有同事有共同的开发测试规范, 并确保任何开发同事都能用最快的速度在不需要别人帮助的情况下运行和测试某一项目, 我们使用 **Docker** 进行环境管理, 暂不应用于生产环境.

Docker 作为开发工程师必备工具, 会列入试用期转正的考评之一, 如果不能熟练使用, 不予录用.

## 安装 Docker

* Mac 平台, 下载 安装dmg即可, 地址 [https://download.docker.com/mac/stable/Docker.dmg](https://download.docker.com/mac/stable/Docker.dmg)
* 其他平台 可以参考 [https://docs.docker.com/engine/installation/](https://docs.docker.com/engine/installation/)

## TODO: 优化

* TODO: 使用国内docker镜像

## 项目配置

* 项目中必须包含让项目能成功运行的 docker 或 docker-compose 配置文件
* 在 README.md 文件中, 详细描述如何让项目 运行\测试\部署等

