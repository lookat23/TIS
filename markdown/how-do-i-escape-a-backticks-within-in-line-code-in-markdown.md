# 怎样在行间代码块中显示反引号`

[stackexchange连接](https://meta.stackexchange.com/questions/82718/how-do-i-escape-a-backticks-within-in-line-code-in-markdown)

使用双倍的反引号：```` `` `List`1` `` ````将会显示为`` `List`1` ``。

[这里](http://daringfireball.net/projects/markdown/syntax) 有对格式的说明。

注意：如果要在行间代码块的开头或结尾添加反引号，则需要在两边添加额外的空格。例如`` foo` ``、`` `foo ``、`` ` ``。如果需要显示2个反引号的话，那可以前后添加数量更多的反引号来作为行间代码块标识。

## 补充

经过测试，多小个反引号都可以作为行间代码块的标识，只要不和代码里面的反引号数量一样即可。例如为了显示3个反引号，就可以用单个反引号作为标识，当然前后的空格还是要有，不然容易出问题。