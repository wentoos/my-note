---
title: 数组遍历
---
# 数组遍历
## 排序
### sort 快速排序
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
### 冒泡排序
```js
var newArr = [2,3,1,2,4,33,22,11,55,22];
for(var j = 0;j<arr.length;j++){
	for(var i = 0;i<arr.length-j-1;i++){
		if(arr[i]>arr[i+1]){
			var da = arr[i];
			arr[i] = arr[i+1];
			arr[i+1] = da;
		}
	}
}
```
利用for循环将值传递赋值进行排序
## 数组去重
### 直接去重
```js
var arr = [1,3,22,3,3,3];
for(var i = 0;i<arr.length;i++){
	for(var j = i+1;j<arr.length;j++){
		if(arr[i]===arr[j]){
			arr.splice(i,1);
			j=j-1;
		}
	}
}
```
### 排序后去重
```js
for(var j = 0;j<arr.length;j++){
	for(var i = 0;i<arr.length-j-1;i++){
		if(arr[i]>arr[i+1]){
			var da = arr[i];
			arr[i] = arr[i+1];
			arr[i+1] = da;
		}
	}
}
console.log(arr)
for(var j = arr.length;j>=0;j--){
	if(arr[j] == arr[j-1]){
		console.log(j)
		arr.splice(j,1);
	}
}
```
### indexOf() 去重
```js
    var arr = [1,3,4,5,6,7,4,3,2,4,5,6,7,3,2];
        var newArr = [];
        for (var i = 0; i < arr.length; i++) {
            if (newArr.indexOf(arr[i]) == -1 ) {
                newArr.push(arr[i])
        }
    }
```
**注释：** indexOf() 方法查询遍历出的数组在新数组中是否出现,出现就返回 -1
