# More

Each of the following solutions has been proven to be effective and We hope to be helpful to you.

## Persistence

Redis supports RDB and AOF persistence way:

* RDB：through snapshot technology, a copy of the data in memory is generated and saved to the specified directory on the disk
* AOF：In other words, all commands (and their parameters) that have been written to the database are recorded to the AOF file by means of protocol text, so as to achieve the purpose of recording database status, which is very similar to the binary log of MySQL

## Multiple instances

Redis is a dictionary hash structure storage server, one Redis has 16 dictionary hash(form 0 to 15, default 0), The client can specify which dictionary to store the data in. It is very similar to building a database in a relational database.

Usually, we will start multiple redis instances on one server:

1. Prepare the ports required for the second instance, example for port: 6378

2. Copy redis.conf file, named redis_6378.conf

3. Fill in the configuration item correctly
    | Configuration item    | Configuration description                                   |
    | --------- | ------------------------------------------ |
    | port      | server port                    |
    | logfile   | log files                                   |
    | dir       | Redis work directory |
    | daemonize | Whether it has been started in daemons mode Redis(yes or no)  |

4. Start service
    ```
    redis-server /etc/redis/redis_6378.conf
    ```

## Edit RedisInsight access port

Edit[Nginx Vhost](/stack-components.md#nginx) parameter `listen` of value, can reset the password

```
server {
    listen 8002;
    server_name example.yourdomain.com;
```
 
## Reset password

Edit [Redis Config](/zh/stack-components.md#redis) parameter `requirepass` of value, can reset the password
```
# Warning: since Redis is pretty fast an outside user can try up to
# 150k passwords per second against a good box. This means that you should
# use a very strong password otherwise it will be very easy to break.
#
# requirepass foobared
```
