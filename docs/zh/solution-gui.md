# 可视化管理

我们推荐使用官方提供免费可视化管理工具 RedisInsight（[下载](https://redislabs.com/redisinsight/) | [Licence](https://redislabs.com/redis-insight-license-terms)） 。它是一个基于浏览器运行的GUI工具，支持 Windows，Linux和Mac OS系统运行。

## 前置条件

查看[远程访问控制](/zh/solution-remote.md)文档，确保符合其中描述的条件。

## 使用

RedisInsight 实现了多平台统一性，只要打开 RedisInsight 界面，使用方式是一模一样的：  

1. 打开 RedisInsight 界面
  
   * 本地浏览器访问：*http://服务器公网IP:8002* ，即可打开服务器上安装的 RedisInsight
   * 启动桌面的RedisInsight图标（[下载安装](https://redislabs.com/redisinsight/) ），打开本地安装的 RedisInsight

   ![打开RedisInsight](https://libs.websoft9.com/Websoft9/DocsPicture/zh/redis/redisinsight-login-websoft9.png)

2. 选择【Connect to a Redis Server】
   ![选择RedisInsight连接方式](https://libs.websoft9.com/Websoft9/DocsPicture/zh/redis/redisinsight-connect001-websoft9.png)

3. 输入连接信息（[不知道密码](/zh/stack-accounts.md#redis)）
   ![登录RedisInsight](https://libs.websoft9.com/Websoft9/DocsPicture/zh/redis/redisinsight-connect002-websoft9.png)
   
   * HOST：localhost （推荐） 或 服务器公网IP
   * Port：66379
   * Name：redis

4. 成功建立一个连接
   ![RedisInsight连接](https://libs.websoft9.com/Websoft9/DocsPicture/zh/redis/redisinsight-connectss-websoft9.png)

5. RedisInsight 的功能十分强大，集管理、监控、配置和分析于一体，甚至还可以运行CLI命令。
   ![登录RedisInsight](https://libs.websoft9.com/Websoft9/DocsPicture/zh/redis/redisinsight-consolegui-websoft9.png)