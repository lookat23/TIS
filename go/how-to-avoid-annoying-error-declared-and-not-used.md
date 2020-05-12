# 如何避免Go中模块或变量没使用而报错的问题

[stackoverflow连接](https://stackoverflow.com/questions/21743841/how-to-avoid-annoying-error-declared-and-not-used)

首先这个报错是为了你能写出更好的代码，和确保你声明和引用的都使用上。它使阅读其它人的代码更容易，因为你总是能确保代码中所有的的声明和引用都已经使用，和避免无用的死代码。

但如果一定要跳过这个错误可以使用[blank identifier](http://golang.org/doc/effective_go.html#blank)（`_`）:

```go
package main

import (
    _ "fmt" // no more error
)

func main() {
    i := 1 // no more error
    _ = i
}
```

可以在[这里](http://golang.org/doc/faq#unused_variables_and_imports)找到官网对这事情的回答

> 出现还没使用的变量可能说明代码有问题，而没使用的引用会减慢编译速度。引用大量没使用的包将会使编译变得非常慢。由于这些原因，所以Go不允许存在没使用的变量和引用。