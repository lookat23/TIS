# 在bash中双引号和单引号的区别

[stackoverflow连接](<https://stackoverflow.com/questions/6697753/difference-between-single-and-double-quotes-in-bash>)

单引号不会进行字符串转换；双引号会进行字符串转换，如变量、反引号(`` ` ``)、某些\转移符等等

example：

```bash
$echo "$(echo "upg")"
upg

$echo '$(echo "upg")'
$(echo "upg")
```

bash手册中对单双引号的说明：

> [3.1.2.2 Single Quotes](http://www.gnu.org/software/bash/manual/html_node/Single-Quotes.html)
>
> 包围字符串在单引号(`'`)中，可以确保在单引号中的字符都按原值。一个单引号不可以出现在一对单引号的里面，除非在前面加上反斜杠`\`。...
>
> [3.1.2.3 Double Quotes](http://www.gnu.org/software/bash/manual/html_node/Double-Quotes.html)
>
> 包围字符串在双引号(`"`)中，可以确保在双引号中的字符都按原值，除了`$`、`` ` `` 、`\`和开启了历史扩展模式。...

