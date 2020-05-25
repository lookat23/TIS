# 如何在Bash中判断字符串是否存在某个子串

[stackoverflow连接](https://stackoverflow.com/questions/229551/how-to-check-if-a-string-contains-a-substring-in-bash)

使用双括号的方法：

```bash
string='My long string'
if [[ $string == *"My long"* ]]; then
  echo "It's there!"
fi
```

注意：子串中的空格必须在双引号之间，和`*`号通配符应该在双引号外面。

注意：简单的匹配使用`==`，不要使用正则操作符`=~`

使用`case`的方法：

```bash
case "$string" in 
  *foo*)
    # Do stuff
    ;;
esac
```

