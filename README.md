
# Redis 自动化安装与部署

本项目是由 [Websoft9](http://www.websoft9.com) 研发的 [Redis](https://redis.io/) 自动化安装程序，开发语言是 Ansible。使用本项目，只需要用户在 Linux 上运行一条命令，即可自动化安装 Redis，让原本复杂的安装过程变得没有任何技术门槛。  

本项目是开源项目，采用 LGPL3.0 开源协议。

## 配置要求

操作系统：目支持 CentOS7.x, Ubuntu, Debian 以上部署此脚本，确保是干净的操作系统  
硬件配置：最低1核1G

## 组件

包含的核心组件为：可选 Redis2.8.24/3.0.7/3.2.13/4.0.14/5.0.7 多个版本

更多请见[参数表](/docs/zh/stack-components.md)

## 本项目安装的是 Redis 最新版吗？

本项目是下载[Redis源码](http://download.redis.io/releases/)，再编译安装。  

查看 [redis.yml](/redis.yml) 文件中版本选择的内容，来查看和维护具体的详细版本号

```
  vars_prompt:
    - name: 'redis_version_number'
      prompt: "\nPlease choose the number for Redis version [ 1/2/3/4/5/6] \n\n
      1: Redis2.8\n
      2: Redis3.0\n
      3: Redis3.2\n
      4: Redis4.0\n
      5: Redis5.0\n
      5: Redis-Latest\n"
      private: no
      default: 3
  vars:
    temp_ver:
      '1': '2.8.24'
      '2': '3.0.7'
      '3': '3.2.13'
      '4': '4.0.14'
      '5': '5.0.7'
      '6': 'stable'
```

Redis-Latest 是官方发布的最新Stable版本，但还没有形成正式的发行版  

我们会定期检查版本准确性，并增加官方最新的stable版本，以保证用户可以顺利安装所需的Redis版本。

## 安装指南

登录 Linux，运行下面的**命令脚本**即可启动自动化部署，然后耐心等待，直至安装成功。

```
#非 root 用户登录后，需先提升成为 root 权限
sudo su -

#自动化安装命令
wget -N https://raw.githubusercontent.com/Websoft9/linux/master/ansible_script/install.py ; python install.py playb=redis url=https://github.com/Websoft9/ansible-redis.git init=0 ansible=y

```

注意：  

1. 自动化脚本需服务器上已经安装 Python 2.7 或以上版本方可运行，一般操作系统会自带 Python。如果无法运行，系统会提示用户先安装 Python，再运行自动化安装命令。
2. 由于自动化安装过程中有大量下载任务，若网络不通（或速度太慢）会引起下载失败，从而导致安装程序终止运行。此时，请重置服务器后再次尝试安装，若仍然无法完成，请使用我们在公有云上发布的 [Redis 镜像](https://apps.websoft9.com/redis) 的部署方式


## 文档

文档链接：https://support.websoft9.com/docs/redis/zh

## FAQ

- 命令脚本部署与镜像部署有什么区别？请参考[镜像部署-vs-脚本部署](https://support.websoft9.com/docs/faq/zh/bz-product.html#镜像部署-vs-脚本部署)
- 本项目支持在 Ansible Tower 上运行吗？支持
