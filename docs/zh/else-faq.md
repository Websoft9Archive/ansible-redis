# FAQ

#### 什么是Redis客户端？

Redis 客户端是用于与Redis-Server进行通信的程序，例如：redis-cli 就是典型的客户端工具

#### Redis 数据库默认的用户名是？

没有用户名的概念

#### Redis 支持多数据库吗？

一台机器上可以运行多个 Redis 实例，每个实例有16个数据库，默认数据库为db0。

![Redis DataBases](https://libs.websoft9.com/Websoft9/DocsPicture/zh/redis/redis-database-websoft9.png)

```
# Interactive mode (no password verification), immediately entering the standby state of the CLI
[root@iZj6calfqlbdkbj5cxjnf9Z ~]# redis-cli
127.0.0.1:6379>

# Change default database 0 to 1
redis 127.0.0.1:6379> SELECT 1

```


#### Redis社区版 vs Redis企业版

* Redis社区版：兼容开源Redis的高性能数据缓存服务，适用于标准的、无特殊业务需求的Redis使用场景。
* Redis企业版：在Redis社区版的基础上开发的强化版Redis服务，从访问延时、持久化需求、整体成本这三个核心维度考量，基于DRAM、NVM和ESSD云盘等存储介质，推出了多种不同形态的产品，为您提供更强的性能、更多的数据结构和更灵活的存储方式，满足不同场景下的业务需求。

#### Redis Labs 与 Redis 有什么关系？

[Redis Labs](https://redislabs.com/) 是 Redis 的母公司，即 Redis 是 Redis Labs 公司旗下的产品。

#### Redis需要密码才能登录吗？

可以无需设置密码验证

#### Redis 支持哪些数据结构？

Redis不是简单的键值存储，它实际上是一个数据结构服务器，支持不同类型的值。包括：二进制字符串、列表、集合、哈希、位图、HyperLogLogs、流等

#### 是否有可视化的数据库管理工具？

部分Redis镜像已经安装 RedisInsight 这个可视化管理工具，如果没有安装，可以自行安装。

#### 是否可以修改Redis的源码路径？

不可以修改

#### 部署和安装有什么区别？

部署是将一序列软件按照不同顺序，先后安装并配置到服务器的过程，是一个复杂的系统工程。  
安装是将单一的软件拷贝到服务器之后，启动安装向导完成初始化配置的过程。  
安装相对于部署来说更简单一些。 

#### 云平台是什么意思？

云平台指提供云计算服务的平台厂家，例如：Azure,AWS,阿里云,华为云,腾讯云等

#### 实例，云服务器，虚拟机，ECS，EC2，CVM，VM有什么区别？

没有区别，只是不同厂家所采用的专业术语，实际上都是云服务器
