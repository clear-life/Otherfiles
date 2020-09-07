### Anaconda环境配置



#### Anaconda

- condas是一个**开源、跨平台、语言无关**的**包管理**和**环境管理系统**
- Anaconda包含了**conda**、**虚拟环境管理**和**大量的库**
- Miniconda是最小化安装的Anaconda

1. 从官网下载好安装包之后，按照教程直接安装
2. 从 开始 菜单栏打开Anaconda Prompt 就可以启动终端



#### 管理conda

1. ##### 显示conda版本

   ```
   conda --version
   ```

2. ##### 更新conda

   ```
   conda update conda
   ```

3. ##### 查看conda帮助信息

   ```
   conda --help 或者 conda -h
   ```



#### 管理环境

1. ##### 创建新环境

   ```
   conda create --name <env_name> <package_names>
   例：
   conda create -n python3 python=3.5 numpy pandas	
   //-n是--name的缩写	python3是环境名称	python=3.5指定包的版本号 
   //numpy和pandas也是一个包		conda把所有东西都看成一个包，包括python和自身conda
   //环境默认保存在 /Users/<user_name>/anaconda3/env 目录下
   ```

2. ##### 切换环境

   ```
   activate <env_name>
   //创建环境时默认为Anaconda的python版本
   //切换环境后，行首以(env_name)/[env_name]开头
   ```

3. ##### 退出环境

   ```
   deactivate
   ```

4. ##### 显示环境信息

   ```
   conda info --envs
   或
   conda info -e
   或
   conda env list
   //"*"所在行即为当前所在环境
   ```

5. ##### 复制环境

   ```
   conda create --name <new_env_name> --clone <copied_env_name>
   //copied_env_name是被复制的环境
   conda create --name py3 --clone python3 
   //复制python3，新环境名为py3
   ```

6. ##### 删除环境

   ```
   conda remove --name <env_name> --all
   ```

#### 管理包

1. ##### 查找可以安装的包版本

   1. 精确查找

      ```
      conda search --full-name <package_full_name>
      conda search --full-name python
      //查找全名为python的包有哪些可以安装的版本
      ```

   2. 模糊查找

      ```
      conda search <text>
      conda search py 
      //查找含有py字段的包
      ```

2. ##### 列出已安装的包

   ```
   conda list
   ```

3. ##### 安装包

   ```
   conda install --name <env_name> <package_name>
   //在指定环境中安装包，没有指定环境的话就在当前环境安装
   
   conda install 无法安装时，可以用pip安装
   pip install <package_name>
   //1、pip不能管理环境，需要先切换到目标环境中，再用pip命令安装
   //2、pip不能更新python
   //3、pip和conda都能安装一些对方不能安装的包
   
   //从Anaconda.org安装包
   //从http://anaconda.org中拿到目标包的路径开始下载
   //复制“To install this package with conda run:”下方的命令，粘贴在终端中执行
   ```

4. ##### 卸载包

   ```
   conda remove --name <env_name> <package_name>
   conda remove --name python3 pandas
   //卸载环境名为python3中的pandas包，默认情况下为当前所在环境
   ```

5. ##### 更新包

   ```
   //更新所有包
   conda update --all
   或
   conda upgrade --all
   
   //更新指定包
   conda update <package_name>
   或
   conda upgrade <package_name>
   conda update pandas numpy matplotlib
   //更新多个指定包
   ```



#### 参考资料链接

```
https://zhuanlan.zhihu.com/p/32925500
```

