# 如何获取结构中的Tag字符串

[stackoverflow连接](https://stackoverflow.com/questions/23507033/golang-reflection-get-tag-from-struct-field)

使用`reflect`这个包可以读取，例子如下：

```go
package main

import (
	"fmt"
	"reflect"
)

type User struct {
	Name string `json:"name_field"`
	Age  int
}

func main() {
	user := &User{"John Doe The Fourth", 20}

	field, ok := reflect.TypeOf(user).Elem().FieldByName("Name")
	if !ok {
		panic("Field not found")
	}
	fmt.Println(getStructTag(field))
}

func getStructTag(f reflect.StructField) string {
	return string(f.Tag)
}

```

[在线连接](https://play.golang.org/p/0SJT8I6gGR5)

