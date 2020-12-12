# Redis remote connection

Although we don't suggest you access Redis from Internet, but sometime you may need to do this. e.g. Using **RedisInsight**.

Then, you need to configure your redis remote by the following steps:

## Set port

Check your **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the **TCP:6379** is allowed

## Bind IP 

You should check your [Redis configuration file](/stack-components.md#redis) the following segment

```
# By default Redis listens for connections from all the network interfaces
# available on the server. It is possible to listen to just one or multiple
# interfaces using the "bind" configuration directive, followed by one or
# more IP addresses.
#
# Examples:
#
# bind 192.168.1.100 10.0.0.1
# bind 127.0.0.1
```

## Enable password

Redis 提供了身份访问控制 [ACL](https://redis.io/topics/acl) 功能，特别是从 Redis 6.0 之后，这些功能进一步增强。  

身份认证最简单的方式就是开启密码：

1. 编辑 Redis 配置文件，找到如下的配置项

```
# Warning: since Redis is pretty fast an outside user can try up to
# 150k passwords per second against a good box. This means that you should
# use a very strong password otherwise it will be very easy to break.
#
# requirepass foobared
```

2. 将 `# requirepass foobared` 修改为 `requirepass yourpassword`
   > 务必将密码设置成非常复杂的加强密码

3. 重启 Redis 服务后生效

