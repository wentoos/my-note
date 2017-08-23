---
title: Git 本地工作流
---
<!-- toc -->
# Git简介

Git是一个开源的分布式版本控制系统，
可以有效、高速的处理从很小到非常大的项目版本管理

## Git特点

开发者可以提交到本地，每个开发者通过克隆（git clone），在本地机器上拷贝一个完整的Git仓库

## 版本控制系统

记录一个或若干文件内容变化，以便将来查阅特定版本修订情况的系统

## Git优点

1. 适合分布式开发，强调个体。
2. 公共服务器压力和数据量都不会太大。
3. 速度快、灵活。
4. 任意两个开发者之间可以很容易的解决冲突。
5. 离线工作。

Git 是一个 **版本控制** 工具，什么是版本控制，我们下面实际操作一下就一目了然了。

## Git 本地工作流

Git **本地工作流**（没有网络操作）可以分为以下几步：

- 第一步，使用 atom 创建并编辑项目
- 第二步，使用 `git init` 命令，把一个**普通项目**变成一个**Git 仓库**
- 第三步，使用 `git add -A` 命令，添加修改内容到 Git
- 第四步，使用 `git commit -m"my commit msg"` 命令，制作一个版本

## 下面来走一个 Git 本地工作流的 Demo

首先，我们先来创建一个项目：

```js
mkdir trygit
```

然后进入项目，创建一个 index.html 文件

```js
cd trygit
```

现在我们来把一个**普通项目**变成一个**仓库** ，需要执行

```git
$ git init
Initialized empty Git repository in /Users/peter/Desktop/project/.git/
```
init 是英文 initialization （初始化）的缩写。
输出信息的英文意思是：

>已经在 project/.git/ 初始化了一个空的 git 仓库

运行这个命令之后，如果我们敲
```js
ls
```
会看到没有任何变化。因为，命令创建的 `.git` 文件夹是一个隐藏文件夹（所有以点开头的文件或者文件夹在 Linux 系统下都是隐藏的）。

要**查看隐藏文件夹**，可以敲
```bash
ls -a
```
这样可以看到输出中包含 `.git` 文件夹了。

`.git` 文件夹是 Git 仓库的心脏，未来所有的版本历史都会保存在 .git 文件夹中。所以
```js
仓库 == 项目 + .git/改版历史
```
注：**仓库** ，英文是 **Repo** ，是我们使用 Git，Github 必须要了解的一个概念。

如果要制作一个**版本**，一共分两步：添加修改和制作版本。

首先来添加修改到 git ：
```js
git add -A
```

**小贴士**： -A 的意思是添加“所有当前修改内容”

要想把添加的内容制作成版本，还需要执行

```js
git commit -m"I add a file"
```

**小贴士**： `commit` 的意思是”做一件很重要的事”，但是在 git 这里，它的意思就是**版本** 。`-m` 就是 message 的简写，后面的内容是**再版留言** 。

问题来了，新用户首次执行上面的命令，会看到下面的报错信息
```js
please tell me who you are
```

解决方法是，运行下面的命令
```js
git config --global user.name  "wentoos"
git config --global user.email  "1217167967@qq.com"
```

来设置用户名和邮箱。这样再次执行
```js
$ git commit -m"I add a file"
[master (root-commit) dcb0329] I add index.html
 1 file changed, 1 insertion(+)
 create mode 100644 index.html
```
就可以成功制作一个版本了。也就是 Git 本地工作流就完成了一个完整的循环。

后续如果再做第二第三个版本，就是只需要：

- 修改内容
- git add -A
- git commit -m"msg"

即可。

>注意：一个项目中 git init 只需要执行一次就可以了。

### 查看改版历史

改版历史（所有我们做过的版本组成的一条线，就叫历史）中，会包含多个版本。每个版本中起码要包含4个 W （ Who When What Why ）。

那么如何来查看改版历史呢？

```js
git log -p
```

`log` 是日志的意思。`-p` 是 patch （补丁，也就是修改内容）的缩写。


小技巧：`q` 可以退出 `git log -p` 的界面，敲 `j` 可以往下翻，敲 `k` 可以往上翻。

>注意，实际中查看版本历史从来不用 git log 命令，而是使用一个前端工具叫做 tig 。安装和使用方式可以参考：http://www.haoduoshipin.com/v/49.html

### 忽略特定文件或者文件夹

有时候，项目文件夹中有一些文件或者文件夹，并不是我们写的代码，例如 node_modules 。那么我们就没有必要把它们进行版本控制，这样我们可以吧这个文件或者文件夹的名字添加到，项目文件夹内的一个特殊文件，叫做 .gitignore 中。

```js
vi .gitignore
```

然后，.gitignore 中填写如下内容：

```js
/node_modules
```

这样，git 就会忽略 node_modules 文件夹，以及里面的所有文件了。

没有 .gitignore 的技巧，我们就会把 node_modules 中的文件也进行版本控制，这样带来两个明显不爽的现象：

- 版本历史混乱
- git push 到 github.com 就会很慢

所以，我们需要学习 .gitignore 的配置技巧。

## 总结

这样，我们就学会了如何在本地创建 git **版本**，查看各个**版本** ，下面一节我们来研究如何把本地的这些**版本**上传到 github.com 。

## 参考

 - Git官网：[点击进入](https://git-scm.com/)
 - 廖雪峰的Git教程：[点击进入](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
