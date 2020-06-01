# 运行shell命令并获取输出

[stackoverflow连接](https://stackoverflow.com/questions/4760215/running-shell-command-and-capturing-the-output)

一种简单的方法是使用`commands`模块，但只能在Unix（包含 Cygwin）系统使用，而且还要使用Python 2.7版本：

```python
import commands
print commands.getstatusoutput('wc -l file')
```

它将返回一个tuple，包含（退出码，输出）。

一种通用于 Python2 和 Python3 的解决方法是使用`subprocess`模块：

```python
from subprocess import Popen, PIPE
output = Popen(["date"],stdout=PIPE)
response = output.communicate()
print response
```



