# 1.Linux基础

## 1.1Linux目录

### 1.1.1Linux目录结构

Linux没有盘符的概念，只有一个根目录`/`，所有的文件都在它下面

### 1.1.2Linux路径的描述方式

`/usr/local/hellow.txt`

第一个`/`为根目录，其他`/`表示层次关系

## 1.2Linux命令

### 1.2.1Linux命令基础

**命令行：**Linux终端（Terminal），是一种命令提示符页面，以纯字符的形式操作系统。可以使用各种字符化命令对系统发出操作指令

**命令：**即Linux程序，一个命令就是一个Linux的程序。命令没有图形化页面，可以在命令行（终端）中提供字符化的反馈

### 1.2.2Linux命令基础格式

**`command [-options] [parameter]`**

- `command`：命令本身
- `-options`：[可选，非必填]命令的一些**`选项`**，可以通过选项控制命令的行为细节
- `parameter`：[可选，非必填]命令的**`参数`**，多数用于命令的指向目标等

**eg：**

- ls -l /home/hellow.txt

  - ls是命令本身
  - -l是选项
  - /home/hello.txt参数

  含义为：以列表的形式，显示/home/hello.txt

- cp -r text1 text2

  - cp是命令本身
  - -r是选项
  - test1和test2是参数

  含义为：复制文件夹test1成为test2

## 1.3常见命令

### 1.3.1ls命令

**语法：**

**`ls [-a -l -h] [Linux路径]`**

- command：
  - `ls`：列出目录下的内容
- -options
  - `-a`：表示列出全部文件（包含隐藏的文件/文件夹）
  - `-l`：以列表（纵向排列）的形式显示内容，并展示更多信息
  - `-h`：以易于阅读的方式，列出文件的大小（必须和`-l`共同使用`-lh`)
- parameter
  - 为空时，列出当前工作目录下的内容呢
  - 可选为指定目标

当不使用选项和参数，直接使用`ls`命令本体，表示以平铺的形式，列出`当前工作目录`下的内容

### 1.3.2目录切换命令（cd-pwd）

Linux终端（命令行）打开默认以用户的home目录作为当前的工作目录

`cd`命令可更改当前所在的工作目录

`cd`命令来自英文：Change Directory

**语法：**

**`cd [Linux路径]`**

- command：
  - `cd`：切换当前所在的工作目录
- -options
  - 无
- parameter
  - 为空时，回到用户的home目录
  - 可选为指定路径

`pwd`命令可以查看当前所在的工作目录

`pwd`命令来自：Print Work Directory

**语法：**

**`pwd`**

- command：
  - `pwd`：查看当前工作目录
- -options
  - 无
- parameter
  - 无

### 1.3.3相对路径、绝对路径、特殊路径符

**绝对路径：**以**`根目录`**为起点，描述路径的一种写法，路径描述以`/`开头

**相对路径：**以**`当前工作目录`**为起点，描述路径的一种写法，路径描述无需以`/`开头

**特殊路径符号：**

- `.`表示当前目录
- `..`表示上一级目录
- `~`表示home目录

### 1.3.4创建目录命令mkdir

通过mkdir命令可以创建新的目录（文件夹）

mkdir来自英文：Mkae Directory

**语法：**

**`mkdir [-p] linux路径`**

- command：
  - `mkdir`：创建新的目录（文件夹）
- -options
  - `[-p]`：可选，表示自动创建不存在的`父目录`，适用于创建连续多层级的目录
- parameter
  - Linux路径（相对或者绝对）

**注意：**
创建文件夹需要修改权限，确保操作均在HOME目录内，不要在HOME外操作
在HOME外操作，会涉及到权限问题

### 1.3.5touch-cat-more命令

**touch命令 创建文件**

通过touch命令创建文件

**语法：**

**`touch Linux路径`**

- command：
  - `touch`：创建文件
- -options
  - 无选项
- parameter
  - Linux路径（相对或者绝对）

**catch命令 查看文件内容**

通过catch查看文件内容

全部显示出来

**语法：**

**`cat Linux路径`**

- command：
  - `catch`：查看内容
- -options
  - 无选项
- parameter
  - Linux路径（相对或者绝对）

**more命令 查看文件内容**

通过more命令查看内容

支持翻页，如果文件内容过多，可以一页一页的展示

通过空格或者回车翻页

通过q退出翻页

**语法：**

**`more Linux路径`**

- command：
  - `catch`：查看文件内容
- -options
  - 无选项
- parameter
  - Linux路径（相对或者绝对）

### 1.3.6cp-mv-rm命令

**cp命令复制文件文件夹**

cp命令可以用于复制文件\文件夹

cp命令来自英文单词：copy

**语法：**

**`cp [-r] 参数1 参数2`**

- command：
  - `cp`：复制文件文件夹
- -options
  - `-r`，可选，用于复制文件夹使用（复制文件夹时必须添加-r）
- parameter
  - `参数1`，Linux路径表示被复制的文件、文件夹
  - `参数2`，Linux路径表示要复制去的地方

**mv命令复制文件文件夹**

mv命令可以用于移动文件\文件夹

mv命令来自英文单词：move

**语法：**

**`mv 参数1 参数2`**

- command：

  - `mv`：移动文件文件夹

- -options

  - 无选项

- parameter

  - `参数1`，Linux路径表示被移动的文件文件夹
  - `参数2`，Linux路径表示要移动去的地方，如果目标不存在，**则进行改名，确保目标存在**

  

**rm命令删除文件文件夹**

mv命令可以用于删除文件\文件夹

mv命令来自英文单词：remove

**语法：**

**`rm [-r -f] 参数1 参数2......参数N`**

- command：
  - `rm`：删除文件文件夹
- -options
  - `-r`，用于删除文件夹
  - `-f`，表示force，强制删除（不会弹出提示确认信息）
    - 普通用户删除内容不会弹出提示，只有root管理员用户删除内容会有提示
    - 一般普通用户用不到-f选项
- parameter
  - `参数N`，Linux路径表示被删除的文件文件夹，按照空格隔开

rm命令支持通配符*，用来做模糊匹配

符号*表示通配符，即匹配任意内容（包含空）

- `test*`，表示匹配任何以test开头的内容
- `*test`，表示匹配任何以test结尾的内容
- `*test*`，表示匹配任何包含test的内容

**关于-f选项**

效果：强制删除

- 可以通过su -root 并输入密码，临时切换到root用户体验
- 通过exit命令，退回普通用户

### 1.3.6which-find命令

**which命令：**

在前面学习的Linux命令，本体是二进制可执行的程序

和Windows系统中的.exe是一个意思

可以通过which命令，查看所使用的一系列命令的程序文件存放在哪里

**语法：**

**`which 需要查找的命令名`**

- command：
  - `which`：查找命令的位置
- -options
  - 无
- parameter
  - `命令名`

**find命令：**

