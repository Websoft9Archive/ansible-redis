# Redis CLI

## About it

[redis-cli](https://redis.io/topics/rediscli)  is the Redis command line interface, a simple program that allows to send commands to Redis, and read the replies sent by the server, directly from the terminal.

Redis CLI supports two usage modes: interactive mode and standard command line:

```
# Interactive mode (no password verification), immediately entering the standby state of the CLI
redis-cli
127.0.0.1:6379>

# Interactive mode (password verification), immediately entering the standby state of the CLI
redis-cli -h 127.0.0.1 -p 6379 -a 123456
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