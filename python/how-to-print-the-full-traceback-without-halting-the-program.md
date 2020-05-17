# 打印异常堆栈

[stackoverflow连接1](https://stackoverflow.com/questions/3702675/how-to-print-the-full-traceback-without-halting-the-program)

[stackoverflow连接2](https://stackoverflow.com/questions/4564559/get-exception-description-and-stack-trace-which-caused-an-exception-all-as-a-st)

最简单的方法就是用`traceback`模块，例子：

```python
import traceback

try:
    raise Exception('this is exception')
except Exception as e:
    traceback.print_exc()
    #or
    print(traceback.format_exc())
```

此方法在Python2和Python3都适用，在stackoverflow的原链接中还有很多说到其它方法的答案。