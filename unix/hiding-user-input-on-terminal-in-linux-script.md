# Shell脚本中输入密码时如何隐藏输入内容

[stackoverflow连接](https://stackoverflow.com/questions/4316730/hiding-user-input-on-terminal-in-linux-script)

编写脚本时输入密码如何已隐藏的方式输入呢，可以通过在read命令中加上 `-s` 参数： 

```bash
$ read -s PASSWORD
$ echo $PASSWORD
```

需要注意的是原链接有评论说不是所有的Shell都支持`-s`参数，不过起码bash是支持的。