# Redis GUI

We suggest you use the GUI tool **RedisInsight**([download](https://redislabs.com/redisinsight/) | [Licence](https://redislabs.com/redis-insight-license-terms)) powered by **Redis Labs** to manage your Redis. It's a web-base GUI which can be installed on Windows, Linux, Mac OS.

RedisInsight is very powerful. It integrates management, monitoring, configuration and analysis, and can even run CLI commands.


## Preconditions

View[Remote Document](/solution-remote.md),confirm matching the basic condition.

## Use

RedisInsight realize the unity of multiple platforms, if start the RedisInsight, how to user it is same: 

1. Start RedisInsight, access init page
  
   * 本地浏览器访问：*http://服务器公网IP:8002* ，即可打开服务器上安装的 RedisInsight
   * 启动桌面的RedisInsight图标（[下载安装](https://redislabs.com/redisinsight/) ），打开本地安装的 RedisInsight

   ![打开RedisInsight](https://libs.websoft9.com/Websoft9/DocsPicture/en/redis/redisinsight-login-websoft9.png)

2. 选择【Connect to a Redis Server】
   ![选择RedisInsight连接方式](https://libs.websoft9.com/Websoft9/DocsPicture/en/redis/redisinsight-connect001-websoft9.png)

3. 输入连接信息（[不知道密码](/zh/stack-accounts.md#redis)）
   ![登录RedisInsight](https://libs.websoft9.com/Websoft9/DocsPicture/en/redis/redisinsight-connect002-websoft9.png)
   
   * HOST：localhost （推荐） 或 服务器公网IP
   * Port：6379
   * Name：redis

4. 成功建立一个连接
   ![RedisInsight连接](https://libs.websoft9.com/Websoft9/DocsPicture/en/redis/redisinsight-connectss-websoft9.png)

5. RedisInsight 的功能十分强大，集管理、监控、配置和分析于一体，甚至还可以运行CLI命令。
   ![登录RedisInsight](https://libs.websoft9.com/Websoft9/DocsPicture/en/redis/redisinsight-consolegui-websoft9.png)