# 如何在无需注销再重新登录系统的前提下，重新加载.bashrc文件

[stackoverflow](https://stackoverflow.com/questions/2518127/how-do-i-reload-bashrc-without-logging-out-and-back-in)

只需通过下面的命令：

```bash
source ~/.bashrc
```

或者使用更短的命令`.`代替`source`：

```bash
. ~/.bashrc
```

除了上面的方法，还有另外一个可行的方法，但需要注意，这个方法和上面的方法原理不一样，命令是：

```bash
exec bash
```

exec命令通过运行指定的命令行来完全替换当前的shell进程。上面的命令使用新的`bash`（使用新的配置文件）替换当前shell进程。

