# 通过IP查找网口名

[stackoverflow连接1](https://stackoverflow.com/questions/49781217/how-to-find-network-interface-name-from-ip-address)

[stackoverflow连接2](https://stackoverflow.com/questions/49781217/how-to-find-network-interface-name-from-ip-address)

感觉这个是冷门问题，所以stackoverflow上虽然有人回答了，但感觉都有些问题。主要是他们没考虑相似IP的问题，例如网口IP为`172.16.1.100`，如果用IP`72.16.1.10`也是能匹配上的，为此我在其它答案之上，对这种情况做了过滤。

```bash
ifconfig | grep -PB1 "[: ]72.16.1.10[^\d]" | grep -o "^\w*"
or
ifconfig | grep -PB1 "[: ]72.16.1.10[^\d]" | awk -F'[: ]' 'NR==1{print $1}'
```

