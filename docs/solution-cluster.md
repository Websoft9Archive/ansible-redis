# Redis deployment architecture

A picture to see the typical Redis deployment architecture:

![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/redis-cluster-architecture.png)

## Single database

单机是最简单的一种模式

## HA database

对Redis来说，主从也就是我们所说的主从复制，主服务器数据更新后根据配置和策略，自动同步到备份服务的一种机制。通常也被称之为：Master-Slave，其中Master以写为主，Slave以读为主。  

这样做的好处显而易见：

* 读写分离
* 容灾恢复

详细部署方案请参考官方文档：https://redis.io/topics/replication

## Clustered database

Redis所以很适合用来充当整个互联网架构中各级之间的Cache，为了在大流量访问下提供稳定的业务，Redis集群化是存储的必然形态。
Redis Cluster 是官方提供的一种集群方案，通常具有 高可用、可扩展性、分布式、容错等特性。

详细部署方案请参考官方文档：https://redis.io/topics/sentinel

## HA Clustered database

高可用性集群即分布式集群，即多个集群组合。