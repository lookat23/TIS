# 字符串如果通过空格分割转换为数组

[stackoverflow连接](https://stackoverflow.com/questions/13737745/split-a-string-on-whitespace-in-go)

原本我是想用`strings.Split`这个方法的，但这个方法明显有问题，当空格个数不是1个时，它会把两个空格中间的空串也作为一个值，所以用`strings.Split`来分割`"aa&nbsp;&nbsp;&nbsp;bb"`这种情况是不正确的。

正确的方法是使用`strings.Fields`方法，代码如下：

```go
someString := "one    two   three four "

words := strings.Fields(someString)

fmt.Println(words, len(words)) // [one two three four] 4
```

[官方文档连接](https://golang.org/pkg/strings/#Fields)

> `func Fields(s string) []string`
>
> Fields 方法通过判断字符串 s 中 一个或多个连续空格字符作为依据进行拆分，返回一个字符串数组，或当字符串只包含空格时返回一个空数组。

