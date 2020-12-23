# 远程访问控制

虽然不建议将 Redis 公开到 Internet 直接访问，但是有些特殊场景下，比如：使用 RedisInsight 客户端，就需要设置 Redis 的远程访问。  

数据库是高安全应用，设置远程访问，最少需三个独立的步骤：

## 设置安全组

一般来说，Redis使用的是6379端口。  

首先，我们要登录到云控制台，打开云服务器所在的安全组中，保证 **TCP:6379** 端口是开启的。

## 设置绑定（非必要）

默认情况下，Redis 允许服务器所有网卡的连接。

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

* 如果需要限制所有外部访问，去掉"#"，重启服务。
* 如果要指定某个网卡，自行添加一行绑定项，例如： `bind 192.168.1.100 10.0.0.1`

> 此处的 bind 不是白名单的概念，而是服务器网卡绑定关系。

## 开启身份验证

Redis 提供了身份访问控制 [ACL](https://redis.io/topics/acl) 功能，特别是从 Redis 6.0 之后，这些功能进一步增强。  

身份认证最简单的方式就是开启密码（对于外网访问是必须的）:

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
   > 本地访问方式，如果关闭密码认证，任然可以连接访问；远程方式必须设置密码才能访问

3. 重启 Redis 服务后生效



