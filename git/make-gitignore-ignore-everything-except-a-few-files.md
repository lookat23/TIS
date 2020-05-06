# .gitignore如何默认忽略所有，只例外部分文件

[stackoverflow连接](<https://stackoverflow.com/questions/987142/make-gitignore-ignore-everything-except-a-few-files>)

> 可选前置参数`!`可以把已经被忽略的文件设置为不忽略。

```bash
# 忽略所有
*

# 但除了这些文件
!.gitignore
!script.pl
!template.latex
# 其它...

# 即使上面例外的文件在子目录中也不忽略
!*/

# 指定例外的具体子目录路径
!*/a/b/file1.txt
!*/a/b/c/*
```

上面的例子解答了标题的问题，先使用`*`来忽略所有文件，然后再配置需要例外的文件。

