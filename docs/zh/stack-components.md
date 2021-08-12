# 参数

Redis 预装包包含 Redis 运行所需一序列支撑软件（简称为“组件”），下面列出主要组件名称、安装路径、配置文件地址、端口、版本等重要的信息。

## 路径

### Redis

Redis 配置文件： */etc/redis.conf*  
Redis 数据目录： */var/lib/redis*  
Redis 日志文件： */var/log/redis/redis.log*  
Redis 默认数据库： *redis*  

### RedisInsight

RedisInsight 安装目录： */data/redisinsight*  
RedisInsight 日志文件： */data/logs/redisinsight*  
RedisInsight 配置文件： */data/redisinsight/redisinsight.config*  

访问方式：*http://服务器公网IP:8002*  


## 端口号

在云服务器中，通过 **[安全组设置](https://support.websoft9.com/docs/faq/zh/tech-instance.html)** 来控制（开启或关闭）端口是否可以被外部访问。 

通过命令`netstat -tunlp` 看查看相关端口，下面列出可能要用到的端口：

| 名称 | 端口号 | 用途 |  必要性 |
| --- | --- | --- | --- |
| Redis | 6379 | 远程访问Redis | 可选 |
| RedisInsight | 8002 | HTTP 访问 RedisInsight  | 可选 |

## 版本号

组件版本号可以通过云市场商品页面查看。但部署到您的服务器之后，组件会自动进行更新导致版本号有一定的变化，故精准的版本号请通过在服务器上运行命令查看：

```shell
# Linux Version
lsb_release -a

# Redis version
redis-server -v
```