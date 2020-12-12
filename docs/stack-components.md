# Parameters

The Redis deployment package contains a sequence software (referred to as "components") required for Redis to run. The important information such as the component name, installation directory path, configuration file path, port, version, etc. are listed below.

## Path

### Redis

Redis configuration file: */etc/redis.conf*  
Redis data directory: */var/lib/redis*  
Redis logs: */var/log/redis/redis.log*  
Redis default database: *redis*  	


### RedisInsight

RedisInsight directory: */data/redisinsight*  
RedisInsight logs: */data/logs/redisinsight*  
RedisInsight configuration file: */data/redisinsight/redisinsight.config*  

You can access it by URL: *http://Server's Internet IP:8002*

### Nginx

Nginx vhost configuration file: */etc/nginx/conf.d/default.conf*    
Nginx main configuration file: */etc/nginx/nginx.conf*   
Nginx logs file: */var/log/nginx*  
Nginx rewrite rules directory: */etc/nginx/conf.d/rewrite* 

## Ports

Open or close ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/tech-instance.html)** of your Cloud Server to decide whether the port can be accessed from Internet.  

You can run the cmd `netstat -tunlp` to check all related ports.  

The following are the ports you may use:

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| Redis | 6379 | Remote connect Redis | Optional |
| RedisInsight | 8002 | Nginx proxy for access to RedisInsight | Optional |

## Version

You can see the version from product page of Marketplace. However, after being deployed to your server, the components will be automatically updated, resulting in a certain change in the version number. Therefore, the exact version number should be viewed by running the command on the server:

```shell
# Linux Version
lsb_release -a

# Redis version
redis-server -v

# Nginx version
nginx -v
```