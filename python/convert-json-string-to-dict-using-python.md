# 如何把JSON字符串转为字典

[stackoverflow连接](https://stackoverflow.com/questions/4528099/convert-json-string-to-dict-using-python)

可以使用`json`模块的`loads`方法： 

```python
import json

d = json.loads(j)
print d['glossary']['title']
```

