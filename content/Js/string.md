---
title: String
---
# string 字符串
String 全局对象是一个用于字符串或一个字符序列的构造函数。
## 语法
```js
let str="string text"
let str1="中文/汉语"
let str2=new String(str)
//返回值：{0: "s", 1: "t", 2: "r", 3: "i", 4: "n", 5: "g", 6: " ", 7: "t", 8: "e", 9: "x", 10: "t", length: 11, [[PrimitiveValue]]: "string text"}
```
**注意** 通过new，它返回一个新创建的 String 对象，存放的是字符串 str2 或 str2 的字符串表示
当不用 new  时，它只把 str 转换成原始的字符串，指向这个string，并返回转换后的值。

**还有从es6开始** 可以用字符串模板书写
```js
let str=`string text`
let str1=`中文/汉语`
```


_书写时可能碰到特别长的字符串_ 可以用字符串拼接书写

```js
let longString = "This is a very long string which needs " +
                 "to wrap across multiple lines because " +
                 "otherwise my code is unreadable.";
```
_或者_ 使用 `\` 在每行末尾使用反斜杠字符 `\`，以指示字符串将在下一行继续。确保反斜杠后面没有空格或任何除换行符之外的字符或缩进; 否则反斜杠将不会工作。 如下所示：
```js
let longString = "This is a very long string which needs \
to wrap across multiple lines because \
otherwise my code is unreadable.";
```
## String 属性
### String.prototype
String.prototype 属性表示 String原型对象。可以使用 String.prototype.constructor 用于创造对象的原型对象的特定的函数。
### String.length
length属性表示返回字符串长度
```js
let str ='wentoos'
str.length// 返回值：7
```
## String 方法
常用的：
```js
charAt()
//返回在指定位置的字符。
concat()
//连接字符串。
indexOf()
//检索字符串。
lastIndexOf()
//从后向前搜索字符串。
match()
//找到一个或多个正则表达式的匹配。
replace()
//替换与正则表达式匹配的子串。
search()
//检索与正则表达式相匹配的值。
slice()
//提取字符串的片断，并在新的字符串中返回被提取的部分。
small()
//使用小字号来显示字符串。
split()
//把字符串分割为字符串数组。
toString()
//返回字符串。
sub()
//把字符串显示为下标。
substr()
//从起始索引号提取字符串中指定数目的字符。
substring()
//提取字符串中两个指定的索引号之间的字符。
toLocaleLowerCase()
//把字符串转换为小写。
toLocaleUpperCase()
//把字符串转换为大写。
toLowerCase()
//把字符串转换为小写。
toUpperCase()
//把字符串转换为大写。
```
不常用的：
```js
toSource()
//代表对象的源代码。
valueOf()
//返回某个字符串对象的原始值。
anchor()
//创建 HTML 锚。
big()
//用大号字体显示字符串。
blink()
//显示闪动字符串。
bold()
//使用粗体显示字符串。
charCodeAt()
//返回在指定的位置的字符的 Unicode 编码。
fixed()
//以打字机文本显示字符串。
fontcolor()
//使用指定的颜色来显示字符串。
fontsize()
//使用指定的尺寸来显示字符串。
fromCharCode()
//从字符编码创建一个字符串。
italics()
//使用斜体显示字符串。
link()
//将字符串显示为链接。
localeCompare()
//用本地特定的顺序来比较两个字符串。
strike()
//使用删除线来显示字符串。
```
[详细介绍使用方法请到W3c](http://www.w3school.com.cn/jsref/jsref_obj_string.asp)
