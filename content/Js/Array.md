---
title: array
---
# Array 对象
## 啥是Array
Array 对象用于在单个的变量中存储多个值。
```js
let arr =[1,2,3]
```
## 创建 array 语法
```js
let arr =['arr','acc']
let arr2=new Array('arr','acc')
let arr2 = [];
arr2[0] = 1;
```
## Array 属性

### Array.prototype
Array.prototype  属性表示 Array 构造函数的原型，并允许您向所有Array对象添加新的属性和方法。
### Array.length
length属性表示返回Array长度
```js
let str =[1,2,3]
str.length//返回值：3
```
## Array 方法
### Array.concat()
合并数组并返回新的数组
```js
var arr = [1,2,3];
var arr1 = [4,5,6];
var arr2 = arr1.concat(arr);
console.log(arr2)
console.log(arr)
console.log(arr1)
```
### Array.reverse()
颠倒数组并返回新的数组（原数组已经改变）
```js
var arr = [1,2,3,4,5];
var arr1 = arr.reverse();
console.log(arr);
console.log(arr1);
```
判断一个数是否为回文数：
```js
//例如：123321
let num ='123321';
let arr =num.split('')
let arr1 =arr.reverse()
console.log(arr===arr1);
```
### Array.pop()
删除并返回数组的最后一个元素
```js
var arr = [1,2,3,4,6];
var num = arr.pop();
console.log(arr);
//[1,2,3,4]
console.log(num);
//6
```
### Array.shift()
删除并返回数组的第一个元素
```js
var arr = [1,2,3,4,6];
var num1 = arr.shift();
console.log(arr);
//[2,3,4,6]
console.log(num1);
//1
```
### Array.push()
向数组最后面添加一个或多个元素返回新数组的长度
```js
var arr = [1,2,3,4,6];
var num2 = arr.push(6,6)
console.log(arr);
//[1,2,3,4,6,6,6]
console.log(num2);]
// 7
```
push(a,b,c)  abc 要添加的元素，必有一个
### Array.unshift()
向数组最前面添加一个或多个元素返回新数组的长度
```js
var arr = [1,2,3,4,6];
var num3 = arr.unshift(1);
console.log(arr)
//[1,1,2,3,4,6]
console.log(num3)
//6
```
### Array.splice(a,b,c)
a 代表删除或者添加的位置（数组的下标） b 删除的个数 c 代表添加的内容  添加或删除元素并返回删除的数组
```js
var arr = [1,2,3,4,6];
var num4 = arr.splice(2,2,56)
console.log(arr)
//[1,2,56,6]
console.log(num4)
//[3,4]
```
### Array.slice(a,b)
截取数组 a-b(数组下标) 包括a 不包括 b 并返回被截取数组
```js
var arr = [1,2,3,4,6];
var num5 = arr.slice(1,2);
console.log(arr)
//[1,2,3,4,6]
console.log(num5)
//[1,2,3]
```
### Array.sort()
数组排序
```js
var newArr = [2,3,1,2,4,33,22,11,55,22];
var newStr = ["eee","sjhgk","uytjl","a","c","b"];
newArr.sort();
console.log(newArr);  
newStr.sort();
console.log(newStr)
var c = function(a,b){return b-a};
newArr.sort(c);
console.log(newArr);
```
使用sort排序时，如果调用该方法时没有使用参数，将按字母顺序对数组中的元素进行排序，说得更精确点，是按照字符编码的顺序进行排序。如达到按照值的大小排列时，必须给sort方法传一个函数，这样才能真正的排序：
```js
var c = function(a,b){return b-a} || var c = function(a,b){return a-b}
```
**参数a,b：** b-a 倒序  a-b 正序
### Array.join(a)
把数组转化为字符串  a:链接数组每一项的字符串
```js
var newArr = [2,3,1,2,4,33,22,11,55,22];
var str = newArr.join("+");
console.log(newArr);
// [2, 3, 1, 2, 4, 33, 22, 11, 55, 22]
console.log(str);
// 2+3+1+2+4+33+22+11+55+22
```
