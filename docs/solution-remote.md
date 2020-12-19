# Redis remote connection

Although we don't suggest you access Redis from Internet, but sometime you may need to do this.  

e.g. Using **RedisInsight**.

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

Redis provided Access Control List [ACL](https://redis.io/topics/acl), after Redis 6.0, These features have been enhanced.

Enable password is need for Internet access, the easiest way to authenticate is to set a password:

1. Edit [Redis config file](/stack-components.md#redis),find the item below

```
# Warning: since Redis is pretty fast an outside user can try up to
# 150k passwords per second against a good box. This means that you should
# use a very strong password otherwise it will be very easy to break.
#
# requirepass foobared
```

2. Set password from `# requirepass foobared` to `requirepass yourpassword`
   > Be sure to set the password whic is a very complex  password
   > For local access mode, if password authentication is turned off, you can still connect to access; for remote access, you must set a password to access

3. After [restart Redis service](/admin-service.md#redis), it will take effect

