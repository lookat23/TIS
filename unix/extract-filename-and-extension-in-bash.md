# bash怎样在文件路径中提取文件名和扩展名

[stackoverflow连接](https://stackoverflow.com/questions/965053/extract-filename-and-extension-in-bash)

```bash
filename=$(basename -- "$fullfile")
extension="${filename##*.}"
filename_exclude_extension="${filename%.*}"
```

作为替代，获取文件名可以使用下面的方法来替代`basename`

```bash
filename="${fullfile##*/}"
```

命令细节可以查看文档：

- 在线文档：[3.5.3 Shell Parameter Expansion](http://www.gnu.org/software/bash/manual/html_node/Shell-Parameter-Expansion.html)；
- bash的man文档“Parameter Expansion”这一节。