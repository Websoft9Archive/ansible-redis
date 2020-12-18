# Redis CLI

## About it

[redis-cli](https://redis.io/topics/rediscli)  is the Redis command line interface, a simple program that allows to send commands to Redis, and read the replies sent by the server, directly from the terminal.

It has two main modes: 
* an interactive mode where there is a REPL (Read Eval Print Loop) where the user types commands and get replies; 
* and another mode where the command is sent as arguments of redis-cli, executed, and printed on the standard output.

```
# Interactive mode (no password verification), immediately entering the standby state of the CLI
[root@iZj6calfqlbdkbj5cxjnf9Z ~]# redis-cli
127.0.0.1:6379>

# Interactive mode (password verification), immediately entering the standby state of the CLI
[root@iZj6calfqlbdkbj5cxjnf9Z ~]# redis-cli -h 127.0.0.1 -p 6379 -a 123456
127.0.0.1:6379>

# Standard command line mode, that is to run a command with a clear goal and exit automatically after execution
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