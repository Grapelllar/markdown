# Git 笔记

## Git 简介

* 版本控制系统
* 作者是 Linux 之父 Linus，打破 SVN 速度慢、需联网的痛点，以及 BitKeeper 收回使用权，花了两周自己写的

* SVN 是集中式版本控制系统，所有的版本库存放于中央服务器。局域网带宽大可能速度够快，但在互联网上慢。

* Git 是分布式版本控制系统，没有中央服务器，每个电脑上都有完整的版本库，工作时无需联网。分布式每台电脑都有副本，更安全。分布式版本控制系统一般也有服务器，只不过用于“方便”交换而已。Git的分支管理是其强大于SVN 之处

  ```待深入学习感受SVN集中式的不便```

## Git 安装

Linux、Mac、Windows上的不同安装方法见：

https://www.liaoxuefeng.com/wiki/896043488029600/896067074338496

### 在 Windows 上 安装 Git

* 在官网下载安装程序：https://git-scm.com/downloads

* 开始菜单中输入 Git，打开 Git Bash

* 安装完成后，设置名字和 Email （分布式系统需要自报家门）：

  * git config 中的 --global 参数代表这太机器上 git 仓库都使用该配置

  ```
  $ git config --global user.name "Your Name"
  $ git config --global user.email "email@example.com"
  ```

### 创建版本库

* repository，在某个目录下创建版本库，目录中的所有文件都被 Git 管理。

#### 创建步骤：

* 选择版本库目录（目录路径不要有中文）

  ```
  $ mkdir learngit
  $ cd learngit
  $ pwd
  /Users/michael/learngit
  ```

* 把目录变成 Git 仓库

  ```
  $ git init
  Initialized empty Git repository in /Users/michael/learngit/.git/
  ```

#### 文件提交：

* 使用 ```git add <file> ``` 把文件**添加**到仓库

  ```
  $ git add readme.txt
  ```

* 使用 ```git commit -m <message>``` 将文件**提交**到仓库 ```-m``` 后附带提交备注，尽量输入，方便从历史记录中查询。一次 commit 能把所有的 add 提交。

  ```
  $ git commit -m "wrote a readme file"
  [master (root-commit) eaadf4e] wrote a readme file
   1 file changed, 2 insertions(+)
   create mode 100644 readme.txt
  ```

#### 注意：

* .git 是隐藏文件勿删，会破坏 Git 仓库
* 版本控制系统只能跟踪文本文件的改动，比如 TXT、网页文件、程序代码。而图片、视频这类二进制文件只能知道文件大小改变，包括 Word 也是二进制
* 建议使用 UTF-8 编码，无冲突
* 千万不要使用Windows自带的**记事本**编辑任何文本文件。原因是Microsoft开发记事本的团队使用了一个非常弱智的行为来保存UTF-8编码的文件，他们自作聪明地在每个文件开头添加了0xefbbbf（十六进制）的字符，你会遇到很多不可思议的问题，比如，网页第一行可能会显示一个“?”，明明正确的程序一编译就报语法错误，等等，都是由记事本的弱智行为带来的。建议你下载[Visual Studio Code](https://code.visualstudio.com/)代替记事本，不但功能强大，而且免费！

#### 疑难问题：

Q：输入`git add readme.txt`，得到错误：`fatal: not a git repository (or any of the parent directories)`。

A：Git命令必须在Git仓库目录内执行（`git init`除外），在仓库目录外执行是没有意义的。

Q：输入`git add readme.txt`，得到错误`fatal: pathspec 'readme.txt' did not match any files`。

A：添加某个文件时，该文件必须在当前目录下存在，用`ls`或者`dir`命令查看当前目录的文件，看看文件是否存在，或者是否写错了文件名。



## 时光机穿梭



* 要随时掌握工作区的状态，使用 ```git status```

* 如果 ```git status``` 告诉你文件有被修改过，用 ```git diff``` 可以查看修改的内容。

### 版本回退

* 类似`1094adb...`的是`commit id`（版本号），这点和 SVN 不一样，是由SHA1 算出来的非常大的数字，不需要写全，前5位就好。
* Git 版本回退直接改指针指向，非常快。HEAD 指向的版本是当前版本。在历史版本间来回穿梭，使用命令 ```git reset --hard <commit_id>```
* 穿梭前，用```git log``` 可以查看提交历史，找出 commit_id 回退版本。如果信息过多，可以使用```git log --pretty=onelien```。回退上一版本可以使用 ```git reset --hard HEAD^```，上上个是 ```git reset --hard HEAD^^```，上一百个是 ```git reset --hard HEAD~100```
* 要重返未来，用```git reflog``` 查看每一次的命令，找到 commit_id 来回到未来。

### 工作区和暂存区

* 工作区：在电脑里能看到的目录

* 版本库：在隐藏目录 .git，其中存储的 stage 为暂存区。自动创建的第一个分支master，HEAD 默认指向它

* 使用 git add，是添加到暂存区，git commit 是提交到分支中。未被添加过到暂存区的文件会报状态 Untracked

  ![gittmp](D:\NEW\Study\markdown\pic\git\gittmp.png)

### 管理修改

* git 管理的是修改，而不是文件
* 每次修改，如果没有添加到暂存区，就不会被 commit

### 撤销修改

* ```git checkout -- <file>``` 丢弃工作区的修改
  * 一种是 <file> 自修改后还没有放到暂存区，撤销修改则回到版本库一模一样的状态
  * 一种是 <file> 已经添加暂存区又做了修改，现在撤销修改就是回到添加到暂存区后的状态 ```==》不理解，待深入研究```

* ```git reset HEAD <file>``` 可以把暂存区的修改撤销
* 已经将不想要的修改提交到了版本库的时候，想要撤销修改，可以参考版本回退，但已经推送到远程库就需要别的方法了。

学习资料：https://www.liaoxuefeng.com/wiki/896043488029600 廖雪峰的 Git 教程

### 删除文件

* 可以在文件管理器或者 ```rm``` 删除文件，使用命令 ```git rm``` 可以删除，并且 ```git commit``` 提交（该过程和添加文件一致，工作区-》暂存区-》版本库）
* 删错的话，可以 ```git checkout -- <file>``` 回退。该命令其实是用版本库替代工作区的版本

## 远程仓库

### 创建SSH并添加到GitHub

* 使用 GitHub 仓库，它的传输是通过 SSH 加密的，步骤如下：

  1、创建 SSH Key，先查看一下**用户主目录**下有没有 .ssh 文件夹，如果有，查看是否有 ```id_rsa``` 和 ```id_rsa.pub```，若有跳过该步骤，若无：

  ```
  $ ssh-keygen -t rsa -C "youremail@example.com"
  ```

  然后一路回车。

  2、登录 GitHub，打开设置，在 SSH Keys 中添加 ```id_rsa.pub```（公钥），并提交。

### 添加远程库

1、在 GitHub 中 Create a new repo，创建新仓库并取名

2、在本地中连接远程库：（远程库名称取名为了 origin）

```
$ git remote add origin git@github.com:GrapesL/learngit.git
```

3、把本地库内容推送到远程库：（-u 会把指定的分支推送，还会与远程库中的该分支关联，于是在以后的推送和拉取就可以简化命令```==》待详细研究```）

```
$ git push -u origin master
```

未来，只需要如下命令即可提交最新修改

```
$ git push origin master
```

### 删除远程库

1、先查看远程库信息：```git remote -v```，确认无误再删除 ```git remote rm <name>```

2、该操作只是删除本地和远程的链接，要真正删除远程库需从 GitHub 中删除。



#### 注意：

#### SSH警告

当你第一次使用Git的`clone`或者`push`命令连接GitHub时，会得到一个警告：

```
The authenticity of host 'github.com (xx.xx.xx.xx)' can't be established.
RSA key fingerprint is xx.xx.xx.xx.xx.
Are you sure you want to continue connecting (yes/no)?
```

这是因为Git使用SSH连接，而SSH连接在第一次验证GitHub服务器的Key时，需要你确认GitHub的Key的指纹信息是否真的来自GitHub的服务器，输入`yes`回车即可。

Git会输出一个警告，告诉你已经把GitHub的Key添加到本机的一个信任列表里了：

```
Warning: Permanently added 'github.com' (RSA) to the list of known hosts.
```

这个警告只会出现一次，后面的操作就不会有任何警告了。





Q：

GitHub上是否有延迟贡献度?对比5.5

分支管理缺：多人协作和Rebase

推送廖老师笔记

GitHub 版本存储是增量还是完全?