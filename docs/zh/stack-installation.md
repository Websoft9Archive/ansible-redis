# 初始化验证

在云服务器上部署 Redis 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:6379** 和 **TCP:8002**端口是否开启
3. 若想用域名访问 Redis，请先到 **域名控制台** 完成一个域名解析

## Redis 检验

1. 通过 SSH 工具连接 Redis服务器

2. 运行 Redis Service 命令
   ```
   ubuntu@redis:~$ sudo systemctl status redis 
   redis.service - redis
   Loaded: loaded (/lib/systemd/system/redis.service; enabled; vendor preset: en
   Active: active (running) since Mon 2020-02-03 10:03:09 UTC; 2h 27min ago
   Process: 31972 ExecStart=/usr/local/bin/redis-server /etc/redis/redis.conf (co
   Main PID: 31973 (redis-server)
   ```
3. 运行版本查询命令
   ```
   ubuntu@redis:~$ sudo redis-server -v
   Redis server v=2.8.24 sha=00000000:0 malloc=jemalloc-3.6.0 bits=64 build=ba7fac81f854c786
   ```
4. 运行 Redis CLI 命令
   ```
   ubuntu@redis:~$ redis-cli
   127.0.0.1:6379>

   //密码登录
   redis-cli -h 127.0.0.1 -p 6379 -a <password>
   127.0.0.1:6379>
   ```
   
5. PHP 连接 redis 读写操作

   ```
   <?php
   
   $redis = new Redis();
   $redis->connect('127.0.0.1', 6379);
   $redis->auth('password');
   $redis->set('Websoft9', 9);
   echo $redis->get('Websoft9'); 

   ?>
   
   ```


> 需要了解更多Redis的使用，请参考：[Redis Documentation](https://redis.io/documentation)

## 常见问题

#### 远程无法连接 Redis？

请检查服务器对应的安全组6379端口是否开启（入规则），且Redis配置文件中是否允许外部访问

#### 本部署是否提供 Web 版的可视化管理工具？

已安装官方可视化管理工具：[RedisInsight](/zh/solution-gui.md)
