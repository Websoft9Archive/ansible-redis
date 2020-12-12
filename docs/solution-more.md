# More

Each of the following solutions has been proven to be effective and We hope to be helpful to you.

## 持久化

Redis 支持 RDB 和 AOF 两种持久化方式：

* RDB：即通过快照技术，将内存中的数据生成一份副本并保存到磁盘指定的目录中；
* AOF：即通过协议文本的方式，将所有对数据库进行过写入的命令（及其参数）记录到 AOF 文件，以此达到记录数据库状态的目的，非常类似 MySQL 的二进制日志

## 多实例

Redis是一个字典结构的存储服务器，一个 Redis 实例对应多个字典（默认支持16个字典，从0开始编号），客户端可以指定将数据存储在哪个字典中。非常类似在关系数据库中建库。

虽然 Redis 没有多数据库，但通常我们会在一台服务器上启动多个 Redis 实例：

1. 准备好第二个实例所需的端口，假如为：6378

2. 复制现有的 redis.conf 文件，命名为 redis_6378.conf

3. 正确填写配置项
    | 配置名    | 配置说明                                   |
    | --------- | ------------------------------------------ |
    | port      | 端口                                       |
    | logfile   | 日志文件                                   |
    | dir       | Redis 工作目录（存放持久化文件和日志文件） |
    | daemonize | 是否已守护进程方式启动 Redis（yes 或 no）  |

4. 启动服务
    ```
    redis-server /etc/redis/redis_6378.conf
    ```

## 修改 RedisInsight 访问端口

编辑 [Nginx 虚拟主机配置文件](/zh/stack-components.md#nginx) 中的参数 `listen` 的值即重置密码。

```
server {
    listen 8002;
    server_name example.yourdomain.com;
```
 
## 重置密码

编辑 [Redis 配置文件](/zh/stack-components.md#redis) 中的参数 `requirepass` 的值即重置密码。
```
# Warning: since Redis is pretty fast an outside user can try up to
# 150k passwords per second against a good box. This means that you should
# use a very strong password otherwise it will be very easy to break.
#
# requirepass foobared
```
