* `ctrl + alt + t` 打开终端

### 帮助命令



#### 查看命令的简要说明

* `whatis command` 简要说明命令的作用(显示命令所处的man分类页面)

* `whatis -w "loca*"`   显示loca开头的命令说明(正则匹配)

* `info command` 更加详细的说明文档



#### 查看命令的说明文档

* `man command`  查看说明文档

* 使用 `page up` 和  `page down` 来翻页

* `man` 的说明文档分为 9 个类别

  ```
  (1)用户可以操作的命令或者是可执行文件
  (2)系统核心可调用的函数与工具等
  (3)一些常用的函数与数据库
  (4)设备文件的说明
  (5)设置文件或者某些文件的格式
  (6)游戏
  (7)惯例与协议等	例如Linux标准文件系统、网络协议、ASCⅡ，码等说明内容
  (8)系统管理员可用的管理条令
  (9)与内核有关的文件
  ```

* 查看某个分类下的说明文档

  ```
  man 3 printf
  ```

* 根据部分关键字查询命令

  ```
  man -k GNOME config| grep 1 	查找GNOME的config配置工具命令
  ```



#### 查看路径

* `which command` 查看程序的二进制文件路径

* `whereis command` 查看程序的搜索路径



### 文件及目录管理



#### 创建/删除/移动/复制

* `mkdir` 创建文件夹
* `rm` 删除文件  
* `rm -rf dir` 删除文件夹
* `rm *log` 删除日志
* `mv` 移动
* `cp` 复制
* `find ./ | wc -l` 查看当前目录下的文件个数
* `cp -r source_dir dest_dir` 复制目录 



#### 目录切换

* `cd` 进入目录
* `cd ..` 进入父目录
* `cd 或 cd ~` 进入home目录
* `pwd` 显示当前路径



#### 列出目录项

* `ls` 列出目录项
* `ls -lrt` 按时间排序,用列表显示目录项
* `ls | cat -n` 添加一个编号



#### 查找目录/文件

* `find ./ -name "core*" | xrags file` 查找文件/目录
* `find ./ -name '*.obj'`查找是否有 `obj` 文件
* `find ./ -name "*.o" -exec rm {} \;` 递归删除 `.obj`文件
* `locate string` 寻找包含有`string`的路径,但`locate`并不是实时查找,需要更新数据库
* `updatedb`更新`locate`数据库



#### 查看文件内容

* `cat -n file`显示内容+行号

* `ls -al | more`按页显示列表内容

* `head -10`只看前十行 

* `tail -10`只看最后十行

* `diff file1 file2`查看文件的差别

* `tail -f crawler.log`动态显示最新信息



#### 查找文件内容

* `egrep 'string' filename`



#### 权限修改

* `chown`改变拥有者
* `chmod`改变读,写,执行等属性



#### 增加别名

* `ln cc ccAgain` 硬链接,删除一个后,仍能找到
* `ln -s cc ccAgain` 软链接,删除源后,另一个不能使用



#### 管道和重定向

* `|`批处理命令
* `;`串联
* `&&`命令必须都执行成功
* `||`前面失败后,后面的命令也能执行
* `>  >>`重定向



#### 设置环境变量

`.profile`文件设置环境变量



#### Bash快捷输入或删除

```
Ctl-U   删除光标到行首的所有字符,在某些设置下,删除全行
Ctl-W   删除当前光标到前边的最近一个空格之间的字符
Ctl-H   backspace,删除光标前边的字符
Ctl-R   匹配最相近的一个文件，然后输出
```

