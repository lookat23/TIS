# 使用print输出时如何不换行

[stackoverflow连接](https://stackoverflow.com/questions/493386/how-to-print-without-newline-or-space)

## 在Python3中

可以使用`end=`参数来使`print`函数输出时不换行：

```python
print('hello', end='')
```

如果有缓冲问题，可以加上`flush`参数来强制刷新：

```python
print('hello', flush=True)
```

## 在Python 2.6 或 2.7中

可以使用`sys.stdout.write()`来直接向标准输出中写数据来实现：

```python
import sys
sys.stdout.write('hello')
```

为了确保输出，可能要调用刷新命令：

```python
sys.stdout.flush()
```

## 补充

开头我以为`sys.stdout.write()`的方法应该同样适用于Python3，但我发现并不是这样的。Python3中不单止换行，还会显示字符串长度，如下：

```python
>>> import sys
>>> sys.stdout.write('hello')
hello5
>>> 
```

