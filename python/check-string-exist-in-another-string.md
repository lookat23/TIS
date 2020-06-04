# 判断字符串是否是另一个字符串的子串

[stackoverflow连接1](https://stackoverflow.com/questions/3389574/check-if-multiple-strings-exist-in-another-string)

[stackoverflow连接2](https://stackoverflow.com/questions/3437059/does-python-have-a-string-contains-substring-method)

最简单的判断方法如下：

```python
if "blah" in 'somestring': 
```

如果要判断一个子串是否存在多个字符串的某个中，下面的方法**是错的**：

```python
>>> "foo" in ["bar", "foo", "foobar"]
True
# 上面并不是判断字符串是否是多个字符串中的某个的子串的正确方法，因为它是精准匹配的，看看下面的改动就会明白
>>> "foo" in ["bar", "afooa", "foobar"]
False
```

上面的写法只有在精准匹配时才能为True，正确的方法应该如下：

```python
>>> any("foo" in x for x in ["bar", "afooa", "foobar"])
True
# 如果需要都匹配，用all 
>>> all("foo" in x for x in ["bfoo", "afooa", "fooba"])
True
```

如果需要多个子串去匹配一个字符串时，方法如下：

```python
>>> any(x in "abccd" for x in ["aa", "bb", "cc"])
True
# 同样的，要都匹配就换用all
>>> all(x in "aabbccd" for x in ["aa", "bb", "cc"])
True
```

那多个子串匹配多个字符串要怎么玩呢，如下玩法：

```python
>>> any(any(y in x for x in ["bar", "afooa", "foobbar"]) for y in ["aasdf", "bb", "ccsdfs"])
True
>>> any(any(y in x for x in ["bar", "afooa", "foobbar"]) for y in ["aasdf", "bbc", "ccsdfs"])
False
```

其实如果遇到这种需求，还是弄个函数写个嵌套循环解决吧，语法糖一时爽，但直观更重要，毕竟以后改代码的可能是自己：）。