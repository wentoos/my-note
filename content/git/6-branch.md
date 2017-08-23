# Github分支
<!-- toc -->
## 什么是分支？

分支就是科幻电影里面的平行宇宙，当你正在电脑前努力学习Git的时候，另一个你正在另一个平行宇宙里努力学习SVN。

如果两个平行宇宙互不干扰，那对现在的你也没啥影响。不过，在某个时间点，两个平行宇宙合并了，结果，你既学会了Git又学会了SVN！

![分支示例图片](../images/0.png)

## 分支管理

### 查看本地分支

```js
git branch  
```

### 查看本地和远程分支

```js
git branch -a  
```

> **小贴士**：`*`代表当前的分支

```js
$ git branch -a
  gh-pages
* master
  remotes/origin/gh-pages
  remotes/origin/master
```

> **小贴士**：默认情况下，origin指向本地的代码库托管在Github上的版本

### 创建分支

```js
git branch [branch-name]
```

### 切换分支

```js
git checkout [branch-name]
```

### 创建并切换分支

```js
git branch -b [branch-name]
```

### 把分支推到远程分支

```js
git push -u origin [branch-name]  
```

### 删除本地分支

```js
Git branch -d [branch-name]
```

### 删除远程版本

```js
git push origin :[branch-name]
```

### 删除远程分支  

```js
git branch -r -d origin/[branch-name]
git push origin :[branch-name]
```

### 合并指定分支到当前分支

```js
git merge [branch-name]
```

### git reset --hard HEAD~ 删除最近版本，回到上个版本

### git reset --hard HEAD 删除新的修改
