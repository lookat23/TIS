# Shell脚本中如何找到端口对应的进程并杀掉

[stackoverflow连接](https://askubuntu.com/questions/346394/how-to-write-a-shscript-to-kill-9-a-pid-which-is-found-via-lsof-i)

以前我是用`netstat`再配合各种筛选命令来实现这个需求，这做法太复杂，还是stackoverflow找到的用`lsof`的方法好。

通过命令`lsof`加上`-t`（terse）参数可以只显示端口，再通过`-i`参数设置端口即可完成需求：

```bash
$ kill -9 $(lsof -ti tcp:80)
```

