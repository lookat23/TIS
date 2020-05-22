# 如何判断map中是否存在某个key

[stackoverflow连接](https://stackoverflow.com/questions/2050391/how-to-check-if-a-map-contains-a-key-in-go)

```go
if val, ok := dict["foo"]; of {
	//...   
}
```

或者

```go
_, ok := dict["foo"]
if ok {
    //...
}
```

