---
title: npm 命令
---
<!-- toc -->
# npm
NPM的全称是Node Package Manager，是随同NodeJS一起安装的包管理和分发工具，它很方便让JavaScript开发者下载、安装、上传以及管理已经安装的包。

## **装包**

```js
npm install [包名]@3.9.1 --save
//简写：npm i
//@3.9.1：指定版本号
//--save：将包添加到packae.json
```

## **安装工具**

```js
npm install [包名]@3.9.1 --save-dev
//简写：-D
```

## **全局安装**

```js
npm install [包名] --global
//简写：-g
```

## **卸载**

```js
npm uninstall [包名]
```

删除全局环境下的包：

```js
npm uninstall [包名] -g
```

## **查看全局插件命令**：

```js
npm list -g --depth
//简写：npm ls -g
```

查看模块版本

```js
npm version
//简写：npm -v
```
检查模块是否已经过时

```js
npm outdated
```
