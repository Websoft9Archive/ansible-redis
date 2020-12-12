# Redis CLI

## About it

[redis-cli](https://redis.io/topics/rediscli)  is the Redis command line interface, a simple program that allows to send commands to Redis, and read the replies sent by the server, directly from the terminal.

It has two main modes: 
* an interactive mode where there is a REPL (Read Eval Print Loop) where the user types commands and get replies; 
* and another mode where the command is sent as arguments of redis-cli, executed, and printed on the standard output.

```
# 交互式模式（无密码验证），即进入 CLI 的随时待命状态
[root@iZj6calfqlbdkbj5cxjnf9Z ~]# redis-cli
127.0.0.1:6379>

# 交互式模式（密码验证），即进入 CLI 的随时待命状态
[root@iZj6calfqlbdkbj5cxjnf9Z ~]# redis-cli -h 127.0.0.1 -p 6379 -a 123456
127.0.0.1:6379>

# 标准命令行模式，即运行一条有明确目标的命令，执行完成后自动退出
redis-cli help
redis-cli incr mycounter
redis-cli --stat
redis-cli --bigkeys
```

## Command line usage

| **Command** | **Description** |
| --- | --- |
| redis-benchmark | Performance test |
| SAVE | Backup Data |
| CONFIG GET dir | Restore Data |
| INFO | Manage Redis services |