# 重置修改过的文件

[stackoverflow连接](https://stackoverflow.com/questions/7147270/hard-reset-of-a-single-file)

重置所有修改的文件可以用下面的命令：

```bash
git reset --hard
```

重置单个文件可以用下面的命令：

```bash
git checkout HEAD -- my-file.txt
```

命令中`--` 代表后面的参数都作为文件名，[这里](https://stackoverflow.com/questions/6561142/different-between-git-checkout-filename-and-git-checkout-filename/6561160#6561160)有stackoverflow中的回答。

