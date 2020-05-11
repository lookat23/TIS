# 如何在命令行中生成字符串的md5

[stackoverflow连接](<https://stackoverflow.com/questions/41721792/bash-generate-md5-hash-of-string-with-special-characters>)

[askubuntu连接](https://askubuntu.com/questions/53846/how-to-get-the-md5-hash-of-a-string-directly-in-the-terminal)

有好几种方法，命令如下：

```bash
printf '%s' hello | md5sum | awk '{print $1}'
echo -n hello | md5sum | awk '{print $1}'
```

要注意使用`<<<`(here-string)的方法不能获得正确结果，因为here-string会为字符串加上换行符，所以**下面命令结果是错误的**：

```bash
md5sum <<< hello | awk '{print $1}'	# 错误的
echo -n hello | md5sum | awk '{print $1}'  # 同样echo不加-n时也会加换行符，也是错误的
```

