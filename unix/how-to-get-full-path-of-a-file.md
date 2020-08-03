# 如何获取文件全路径

[stackoverflow连接](https://stackoverflow.com/questions/5265702/how-to-get-full-path-of-a-file)

使用[readlink](http://man7.org/linux/man-pages/man1/readlink.1.html) 或者 `realpath`：

```bash
readlink -f file.txt
realpath file.txt
```

