# shell中，2>&1是什么意思

[stackoverflow连接](https://stackoverflow.com/questions/818255/in-the-shell-what-does-21-mean)

文件描述符 1 代表标准输出（stdout）。

文件描述符 2 代码标准错误输出（stderr）。

这是一种记忆方法，尽管不是完全准确。首先，2>1可以看做是`stderr`重定向到`stdout`。然而，事实上它会解释为把`stderr`重定向到文件名为1的文件中。为了解决这个问题，使用`&`显式说明后面跟着的是一个文件描述符，而不是文件名。所以就会写成`2>&1`

## 补充

所以，如果要把程序的标准输出和标准错误输出都抛弃，可以这样写

```bash
command > /dev/null 2>&1
```

