# PHP中各种空和对应判断方法

[stackoverflow连接](https://stackoverflow.com/questions/8236354/php-is-null-or-empty)

在PHP7中，`if`对比`isset`对比`is_null`对比`empty`判断各种空的区别如下：

|         | '' OR "" | NULL  | []    | 0 OR "0" | false | Object |
| ------- | -------- | ----- | ----- | -------- | ----- | ------ |
| if()    | false    | false | false | false    | false | true   |
| isset   | true     | false | true  | true     | true  | true   |
| is_null | false    | true  | false | false    | false | false  |
| empty   | true     | true  | true  | true     | true  | false  |

 从表中可以看出，用`if`来判断各种空不靠谱。`isset`和`is_null`可以很好地判断`NULL`的情况。`empty`很符合空的概念，上面的空都会判定为`true`