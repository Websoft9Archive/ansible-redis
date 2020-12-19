# FAQ

#### What is the Redis client?

Redis client is a program used to communicate with Redis-Server, for example: redis-cli is client tool

#### What's relationship between Redis Labs and Redis?

[Redis Labs](https://redislabs.com/) is the parent company of Redis, that is, Redis is a product of Redis Labs.

#### Does Redis need a password to log in?

No password authentication required

#### What is Redis default user？

Redis have not users

#### Redis supports multiple databases？

Multiple redis instances can be run on a server. Each instance has 16 databases, the default is db0.

![Redis DataBases](https://libs.websoft9.com/Websoft9/DocsPicture/en/redis/redis-database-websoft9.png)

> redis-cli how to change database

```
# Interactive mode (no password verification), immediately entering the standby state of the CLI
[root@iZj6calfqlbdkbj5cxjnf9Z ~]# redis-cli
127.0.0.1:6379>

# Change default database 0 to 1
redis 127.0.0.1:6379> SELECT 1

```

#### Redis Communication Version vs Redis Enterprise Version

* Redis Communication Version: High performance data caching service compatible with open source redis, suitable for standard redis usage scenarios without special business requirements.
* Redis Enterprise Version: The Enterprise version of redis service developed on the basis of redis Community Edition has launched a variety of different forms of products based on DRAM, NVM, ESSD cloud disk and other storage media from the three core dimensions of access delay, persistence requirements and overall cost, so as to provide you with stronger performance, more data structures and more flexible storage methods to meet the business requirements in different scenarios.

#### What data structures does Redis support?

Redis is not a plain key-value store, it's data structures server, supporting different [kinds of values](https://redis.io/topics/data-types-intro)

#### Is there a web-GUI tool for Redis?

Yes, installed RedisInsight

#### Is there a web-base GUI database management tools?

No

#### Is it possible to modify the source path of Redis?

No

#### What's the difference between Deployment and Installation?

- Deployment is a process of installing and configuring a sequence of software in sequence in a different order, which is a complex system engineering.  
- Installation is the process of starting the initial wizard after the application is prepared.  
- Installation is simpler than deployment. 

#### What's Cloud Platform?

Cloud platform refers to platform manufacturers that provide cloud computing services, such as: **Azure, AWS, Alibaba Cloud, HUAWEI CLOUD, Tencent Cloud**, etc.

#### What is the difference between Instance, Cloud Server, Virtual Machine, ECS, EC2, CVM, and VM?

No difference, just the terminology used by different manufacturers, actually cloud servers
