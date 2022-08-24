---
theme: juejin
highlight: tomorrow
---

大家好我是牛哥，这段时间有思考自己为什么要从事程序员这行，在绝大多数人的印象中，程序员累无止境的996，经常加班，还是个“青春饭”到了35岁面临着中年危机。今年是互联网的寒冬（可以说每年都是寒冬），曾经很多人以为大厂是程序员的避风港，往年大厂只裁业务水平跟不上的程序员，但是今年很多大厂不论技术好坏，出现了整个业务部门直接裁员。每年都说是寒冬，但是每年依旧有人拿高薪，在高薪的背后别人必定付出了很多，也恰恰说说明无论在什么样的背景下，只要肯付出并且坚持提升自我会有无限的可能。

既然选择了这一行就要热爱它，保持热爱，把它当成一种兴趣，保持内在驱动力才能走的更远，我觉得不论在任何行业都要保持持续学习，否则就会淹没在历史的潮流中。当下舒服，代表你的人生正在下坡；当下痛苦，代表你的人生正在爬坡；当下焦虑，代表你的人生正在扯淡。提升自己前要做好计划，合理安排时间，每个人精力是有限的，抓住重点，做好笔记，定时复盘，最重要的是坚持，坚持每日精进。


这里同步会更慢一些，实时更新可以到我[github](https://github.com/xiaoniuge36/ng-learning-for-1024-days)（二者同步）
# Day8【2022年7月30日】 
**学习重点：** 总结一下js数组常用的一些原生方法（API)(上)
## 1.数组方法总结(上)
###  1.1 at()
at() 方法接收一个整数值并返回该索引的项目，允许正数和负数。负整数从数组中的最后一个项目开始倒数。

方括号符号没有问题。例如，array[0]将返回第一个项目。然而，对于后面的项目，不要使用array.length，例如，对于最后一个项目，可以调用array.at(-1)。(参见以下示例)

**用法：**
```js
at(index)
```
index 表示数组中对应的整数可以为负数，若是不存在返回undefined，若是负数则默认从后往前查询。
**返回值：**

返回数组中索引对应的值。

**实例：**
```js
let array1 = [5, 12, 8, 130, 44];

console.log(array1.at(0));//5
console.log(array1.at(1));// 12
console.log(array1.at(-1));// 44
console.log(array1.at());// 5
console.log(array1.at(5));// undefined
```
### 1.2 concat()
合并两个或者多个数组，返回一个新数组，该方法不改变原数组。

**用法：**
```js
var new_array = old_array.concat(value1[, value2[, ...[, valueN]]])
```
valueN是可选

**返回值：**

返回新数组，不会改变this，返回的是浅拷贝。

**实例：**
```js
let array1 = [5, 12, 8, 130, 44];
let array2 = [6, 13, 10, 20, 45];
let array3 = [7, 14, 11, 21, 46];
let array4 = [8, 15, 12, 22, 47];

console.log(array1.concat());// [5, 12, 8, 130, 44]
console.log(array1.concat(array2));// [5, 12, 8, 130, 44, 6, 13, 10, 20, 45]
console.log(array1.concat(array2, array3));// [5, 12, 8, 130, 44, 6, 13, 10, 20, 45, 7, 14, 11, 21, 46]
console.log(array1.concat(array2, array3, array4));// [5, 12, 8, 130, 44, 6, 13, 10, 20, 45, 7, 14, 11, 21, 46, 8, 15, 12, 22, 47]
console.log(array1.concat(array2, array3, array4, [1, 2, 3]));// [5, 12, 8, 130, 44, 6, 13, 10, 20, 45, 7, 14, 11, 21, 46, 8, 15, 12, 22, 47, 1, 2, 3]
```
### 1.3 copyWithin()

**用法：**
```js
arr.copyWithin(target[, start[, end]])
```
**返回值：**

改变后的数组。

**实例：**
```js
```
### 1.4 entries()
返回一个新的数组Iterator（迭代器）对象，该对象包含数组中每个索引的键/值对。
**用法：**
```js
arr.entries()
```
**返回值：**
> 一个新的 Array 迭代器对象。Array Iterator是对象，它的原型（__proto__:Array Iterator）上有一个next方法，可用用于遍历迭代器取得原数组的 [key,value]。

**实例：**
```js
let array1 = ['a', 'b', 'c'];

let iterator1 = array1.entries();

console.log(iterator1.next());// {value: Array(2), done: false}

console.log(iterator1.next().value);// [1, 'b']

console.log(iterator1.next().value);// [2, 'c']

console.log(iterator1.next().value);//undefined

console.log(iterator1.next());// {value: undefined, done: true}
```
### 1.5 every()
检测数组中条件是否都符合条件。返回一个布尔值。如果为空数组则返回true，不改变原数组。

**用法：**
```js
arr.every(callback(element[, index[, array]])[, thisArg])
```
callback为回调函数，里面包含的参数 element表示用于当前值，index（可选）当前值的索引，array（可选）表示调用的数组，thisArg（可选）执行方法时回调函数的callback的this值（可指定），如果不指定在非严格模式下是指向全局对象window，在严格模式下指向的是undefined。

**返回值：**

每一个都通过返回true（返回是[truthy](https://developer.mozilla.org/zh-CN/docs/Glossary/Truthy) 值），有一个不通过返回false

**实例：**
```js
let array = [1, 2, 3, 4, 5];

console.log(array.every((element) => element > 4));//false
console.log(array.every((element) => element < 6));// true

let array1 = [1,2,3,4,5,6];
// array1.every(function (currentValue, index, arr) {
       // 0;
//     console.log(this);
//     return this < currentValue;
// }, 0);

array1.every(function (currentValue, index, arr) {
    //window;
    console.log(this);
    return 0 < currentValue;
});
```
### 1.6 fill()
用一个值填充数组中的指定元素，可以指定开始和结束的索引，不包括结束索引。

**用法：**
```js
arr.fill(value[, start[, end]])
```
value用来填充元素的值，start（可选）起始索引，默认值为 0，end（可选）终止索引，默认值为this.length（数组最够一个数索引+1=this.length），start若是负数则默认处理为atart+arr.length，end也是如此。

**返回值：**

修改后的数组

**实例：**
```js
// fill方法
console.log([1, 2, 3, 4, 5].fill(0));// [0, 0, 0, 0, 0]
console.log([1, 2, 3, 4, 5].fill(0, 1, 3));// [1, 0, 0, 4, 5]
console.log([1, 2, 3, 4, 5].fill(0, 2));// [1, 2, 0, 0, 0]
console.log([1, 2, 3, 4, 5].fill(0, -1));// [1, 2, 3, 4, 0]
console.log([1, 2, 3, 4, 5].fill(0, 5));// [1, 2, 3, 4, 5]
console.log([1, 2, 3, 4, 5].fill([1]));// [Array(1), Array(1), Array(1), Array(1), Array(1)]

//生成一个二维数组
console.log([0,0].map(() => new Array(3).fill(0)));//[Array(3), Array(3)]
```
### 1.7 filter()
对数组中符合条件的元素进行筛选，会返回一个新数组。不改变原数组

**用法：**
```js
var newArray = arr.filter(callback(element[, index[, array]])[, thisArg])
```
callback回调函数。emement表示遍历的当前元素，index（可选）遍历当前元素的索引，array（可选）遍历数组本身，[thisArg]（可选）可用来修改callback的this指向。更every一样，this不知道默认指向全局对象window，严格模式下是undefine。

**返回值：**

返回满足条件的新数组，如果没有任何数组元素通过测试，则返回空数组。

**实例：**
```js
let array = [1, 2, 3, 4, 5];
console.log(array.filter((element) => element > 4));//[5]
console.log(array.filter((element) => element < 6));// [1, 2, 3, 4, 5]
console.log(array.filter((element) => element === 4));// [4]
console.log(array.filter((element) => element === 5));//[5]
console.log(array.filter((element) => element === 6));// []
```
### 1.8 find()
找到符合条件的第一个元素否则返回undefined，不改变原数组。

**用法：**
```js
arr.find(callback[, thisArg])
```
> callback在数组每一项上执行的函数，接收 3 个参数：element当前遍历到的元素。index可选当前遍历到的索引。array可选数组本身。thisArg可选执行回调时用作 this 的对象。

**返回值：**

返回符合条件的第一个值否则返回undefined

**实例：**
```js
let array = [1, 2, 3, 4, 5];

console.log(array.find((element) => element > 4));// 5
console.log(array.find((element) => element < 6));// 1
console.log(array.find((element) => element === 4));// 4
console.log(array.find((element) => element === 6));// undefined
```
若找到一个元素的位置或者一个元素是否存在于数组中，请使用[includes](#includes_top)和[indexOf](#indexOf_top)。
### 1.9 findIndex()
返回数组中满足条件的第一个元素的索引。若没有找到则返回-1。

**用法：**
```js
arr.findIndex(callback[, thisArg])
```
参数的用法跟find一样

**返回值：**

返回对应的索引，否则返回-1.

**实例：**
```js
let array = [1, 2, 3, 4, 5];
console.log(array.findIndex((element) => element > 4));// 4
console.log(array.findIndex((element) => element < 6));//0
console.log(array.findIndex((element) => element === 4));// 3
console.log(array.findIndex((element) => element === 6));// -1
```
跟find对应的是该方法返回的是索引find返回的是值，二者都是找到对应的第一个元素。
### 1.10 findLast()
返回数组中满足条件的最后一个元素，若没找到则返回undefined。不改变原数组。

**用法：**
```js
arr.findLast(function(element, index, array) , thisArg)
```
函数的三个参数依旧分别是，当前元素，对应索引，当前数组。

**返回值：**

返回满足条件的最大索引对应的值，否则返回undefined。

**实例：**
```js
let array = [1,2,3,4,5];

console.log(array.findLast((element) => element > 4));// 5
console.log(array.findLast((element) => element < 6));// 5
console.log(array.findLast((element) => element === 4));// 4
console.log(array.findLast((element) => element === 6));// undefined
```
### 1.11 findLastIndex()
返回数组中满足条件的最后一个元素的索引，若没找到则返回undefined。不改变原数组。

**用法：**
```js
arr.findLastIndex(function(element, index, array) , thisArg)
```
参数的含义跟findLast一样。

**返回值：**

返回满足条件的索引

**实例：**
```js
let array = [1,2,3,4,5];

console.log(array.findLastIndex((element) => element > 4));//4
console.log(array.findLastIndex((element) => element < 6));//4
console.log(array.findLastIndex((element) => element === 4));//3
console.log(array.findLastIndex((element) => element === 6));//-1
```
**待改：**
第一个匹配的元素，使用 find()。
数组中最后一个匹配元素的索引，使用 findLastIndex()。
值的索引，使用 Array.prototype.indexOf()。（它类似于 findIndex()，但是会检查每个元素是否和值相等，而不是使用一个测试函数。）
一个值是否包含在该数组中，使用 Array.prototype.includes()。同样地，它检查每个元素是否和值相等，而不是使用一个测试函数。
是否有任意一个元素满足提供的测试函数，使用 Array.prototype.some()。
### 1.12 flat()
将数组中的元素与子数组合并成一个新数组，可以指定深度递归遍历的层数。若遇到空项会直接去除。原生扁平化方法。不会改变原数组，返回的是处理过的新数组。

**用法：**
```js
var newArray = arr.flat([depth])
```
depth（可选）指定要提取嵌套数组的结构深度，默认值为 1。

**返回值：**

一个包含将数组与子数组中所有元素的新数组。

**实例：**
```js
let array = [1,2,3,4,5,[1]];
let array1 = [1,2,3,,5,[1]];
let array2 = [1,2,3,4,5,[[1]]];
console.log(array.flat());// [1, 2, 3, 4, 5, 1]
console.log(array);//[1, 2, 3, 4, 5, Array(1)]
console.log(array1.flat());// [1, 2, 3, 5, 1]
console.log(array1);// [1, 2, 3, empty, 5, Array(1)]
console.log(array2.flat(2));// [1, 2, 3, 4, 5, 1]
```
### 1.13 flatMap()
flatMap() 方法首先使用映射函数映射每个元素，然后将结果压缩成一个新数组。它与 map 连着深度值为 1 的 flat 几乎相同，但 flatMap 通常在合并成一种方法的效率稍微高一些。

**用法：**
```js
var new_array = arr.flatMap(function callback(currentValue[, index[, array]]) {
    // return element for new_array
}[, thisArg])
```
callback
可以生成一个新数组中的元素的函数，可以传入三个参数：
currentValue
当前正在数组中处理的元素
index可选
可选的。数组中正在处理的当前元素的索引。
array可选
可选的。被调用的 map 数组
thisArg可选
可选的。执行 callback 函数时 使用的this 值。

**返回值：**

一个新的数组，其中每个元素都是回调函数的结果，并且结构深度 depth 值为 1。

**实例：**
```js
const arr1 = [1, 2, [3], [4, 5], 6, []];

const flattened = arr1.flatMap(num => num);

console.log(flattened);
//  Array [1, 2, 3, 4, 5, 6]

var arr1 = [1, 2, 3, 4];

arr1.map(x => [x * 2]);
// [[2], [4], [6], [8]]

arr1.flatMap(x => [x * 2]);
// [2, 4, 6, 8]

// only one level is flattened
arr1.flatMap(x => [[x * 2]]);
// [[2], [4], [6], [8]]
```
## 2.今日精进
 9. 回文数（双向指正解题）
复习解决方案结构师准备阶段内容，学习javaSE1，2讲。

# Day9【2022年7月31日】 
**学习重点：** 总结一下js数组常用的一些原生方法（API)(中)
## 1.数组方法总结(中)
### 1.1 forEach()
对数组的每个元素执行一次给定的函数。不会改变原数组，不可终止循环，可以通过抛出异常的方式终止异常。没有返回值。

**用法：**
```js
arr.forEach(callback(currentValue [, index [, array]])[, thisArg])
```
callback
为数组中每个元素执行的函数，该函数接收一至三个参数：
currentValue
数组中正在处理的当前元素。
index 可选
数组中正在处理的当前元素的索引。
array 可选
forEach() 方法正在操作的数组。
thisArg 可选
可选参数。当执行回调函数 callback 时，用作 this 的值。

**返回值：**
undefined。

**实例：**
```js
let array1 = [1,3,2,4];
array1.forEach((item, index) => {
    console.log(item, index);
}
);
// 1 0
// 3 1
// 2 2
// 4 3
```
### 1.2 from()
方法对一个类似数组或可迭代对象创建一个新的，浅拷贝的数组实例。

**用法：**
```js
Array.from(arrayLike[, mapFn[, thisArg]])
```
arrayLike
想要转换成数组的伪数组对象或可迭代对象。
mapFn 可选
如果指定了该参数，新数组中的每个元素会执行该回调函数。
thisArg 可选
可选参数，执行回调函数 mapFn 时 this 对象。

**返回值：**

一个新的数组实例。

**实例：**
```js
console.log(Array.from('foo')); // ['f', 'o', 'o']

console.log(Array.from([1, 2, 3], x => x + x)); // [2, 4, 6]
```
<h3 id="includes_top"  > 1.3 includes() </h3>
判断数组中是否包括一个指定的值，包括返回true不包括返回false。
**用法：**
```js
arr.includes(valueToFind[, fromIndex])
```
valueToFind需要寻找的元素值。

fromIndex （可选）默认值为0，选择的话表示从该索引开始查找，若为负数则会根据公式（arr.length+fromIndex）进行转换。

**返回值：**

返回true/false，正0和负0视为相等。

**实例：**
```js
let array = [1,2,3,4,5];
console.log(array.includes(1));// true
console.log(array.includes(2));// true
console.log(array.includes(3,1));// true
console.log(array.includes(4,4));// false
console.log(array.includes(5,-1));// true
console.log(array.includes());// false
```
可以看出如果不传参的话默认返回false
<h3 id="indexOf_top"  > 1.4 indexOf() </h3>
返回数组中对应元素的索引，若不存在则返回-1。不改变原数组。

**用法：**
```js
arr.indexOf(searchElement[, fromIndex])
```
searchElement要寻找的元素
fromIndex(可选)选择开始查找的索引，若为-1则表示从后向前查找，其他负数的话以此类推，不填则默认为0。

**返回值：**

首个被找到的元素在目录中的索引位置；若无则返回 -1

**实例：**
```js
let array = [1,2,3,4,5];
console.log(array.indexOf(1));// 0
console.log(array.indexOf(2));// 1
console.log(array.indexOf(3,1));// 2
console.log(array.indexOf(4,4));// -1
console.log(array.indexOf(5,-1));// 4
console.log(array.indexOf());// -1
console.log(array);// [1, 2, 3, 4, 5]
```
### 1.7 isArray()
判断一个值是否为数组。

**用法：**
```js
Array.isArray(obj)
```
obj需要检测的值。

**返回值：**

如果是 Array，则为 true；否则为 false。

**实例：**
```js
console.log(Array.isArray([1,2,3,4,5]));// true
console.log(Array.isArray({0:1,1:2,2:3,3:4,4:5}));// false
console.log(Array.isArray(function(){}));// false
console.log(Array.isArray(/^/));// false
console.log(Array.isArray(new Date()));// false
console.log(Array.isArray(new Map()));// false
console.log(Array.isArray(new Set()));// false
console.log(Array.isArray(Array.prototype));// true
Array.isArray(new Array());// true
Array.isArray(new Array('a', 'b', 'c', 'd'))// true
```
### 1.8 join()
方法将一个数组（或一个类数组对象）的所有元素连接成一个字符串并返回这个字符串。如果数组只有一个项目，那么将返回该项目而不使用分隔符。如果一个元素为 `undefined` 或 `null`，它会被转换为空字符串。所有的数组元素被转换成字符串，再用一个分隔符将这些字符串连接起来。

将一个数组或者类数组对象（类数组是可以当作数组来使用的对象）转换成字符串，并用传入的分隔符连接起来，若数组中有一个元素为undefined或null则会被转换为空字符串。

**用法：**
```js
arr.join([separator])
```
separator 可选
指定一个字符串来分隔数组的每个元素。如果需要，将分隔符转换为字符串。如果缺省该值，数组元素用逗号（,）分隔。如果separator是空字符串 ("")，则所有元素之间都没有任何字符。



**返回值：**
一个所有数组元素连接的字符串。如果 arr.length 为 0，则返回空字符串。
**实例：**
```js
let array1 = [1,3,2,4];
console.log(array1.join(''));// 1324
console.log(array1.join('-'));// 1-3-2-4
console.log(array1.join('-', '*'));// 1-3-2-4
console.log(array1.join('-', '*', '#'));// 1-3-2-4
console.log(array1);// [1, 3, 2, 4]
```
### 1.9 keys()
方法返回一个包含数组中每个索引键的Array Iterator对象。

**用法：**
```js
arr.keys()
```
**返回值：**

一个新的 Array 迭代器对象。

**实例：**
```js
let array1 = [1,3,2,4];
console.log(array1.keys());// Array Iterator {}
console.log(array1.values());//Array Iterator {}
console.log(array1.entries());// Array Iterator {}
console.log(array1.entries().next());// {value: Array(2), done: false}
console.log(array1.entries().next().value);//  [0, 1]
console.log(array1.entries().next().value[0]);//7 0
console.log(array1);// [1, 3, 2, 4]
```
### 1.10 lastIndexOf()
方法返回指定元素（也即有效的 JavaScript 值或变量）在数组中的最后一个的索引，如果不存在则返回 -1。从数组的后面向前查找，从 fromIndex 处开始。

**用法：**
```js
arr.lastIndexOf(searchElement[, fromIndex])
```
searchElement
被查找的元素。
fromIndex 可选
从此位置开始逆向查找。默认为数组的长度减 1(arr.length - 1)，即整个数组都被查找。如果该值大于或等于数组的长度，则整个数组会被查找。如果为负值，将其视为从数组末尾向前的偏移。即使该值为负，数组仍然会被从后向前查找。如果该值为负时，其绝对值大于数组长度，则方法返回 -1，即数组不会被查找。
返回值
数组中该元素最后一次出现的索引，如未找到返回-1。

**返回值：**

lastIndexOf 使用严格相等（strict equality，即 ===）比较 searchElement 和数组中的元素。

**实例：**
```js
let array1 = [1,3,2,4];
console.log(array1.lastIndexOf(3));//1
console.log(array1.lastIndexOf(3,2));//1
console.log(array1.lastIndexOf(3,3));//1
```
### 1.11 map()
 方法创建一个新数组，这个新数组由原数组中的每个元素都调用一次提供的函数后的返回值组成。
 
**用法：**
```js
var new_array = arr.map(function callback(currentValue[, index[, array]]) {
 // Return element for new_array 
}[, thisArg])
```
callback
生成新数组元素的函数，使用三个参数：
currentValue
callback 数组中正在处理的当前元素。
index可选
callback 数组中正在处理的当前元素的索引。
array可选
map 方法调用的数组。
thisArg可选
执行 callback 函数时值被用作this。
**返回值：**

一个由原数组每个元素执行回调函数的结果组成的新数组

**实例：**
```js
let array1 = [1,3,2,4];
console.log(array1.map(item=>{return item*2}));// [2, 6, 4, 8]
console.log(array1.map(item=>{return item*2}).reduce((pre,cur)=>{return pre+cur}));// 20
console.log(array1);// [1, 3, 2, 4]
```
### 1.12 of()
创建一个具有可变数量参数的新数组实例，而不考虑参数的数量或类型。

**用法：**
```js
Array.of(element0[, element1[, ...[, elementN]]])
```
elementN
任意个参数，将按顺序成为返回数组中的元素。

**返回值：**

新的 Array 实例。

**实例：**
```js
Array.of(7);       // [7]
Array.of(1, 2, 3); // [1, 2, 3]

Array(7);          // [ , , , , , , ]
Array(1, 2, 3);    // [1, 2, 3]

```
### 1.13 pop()
方法从数组中删除最后一个元素，并返回该元素的值。此方法会更改数组的长度。
**用法：**
```js
arr.pop()
```
**返回值：**

从数组中删除的元素（当数组为空时返回undefined）。

**实例：**
```js
let array1 = [1,3,2,4];

console.log(array1.pop()); //4   
console.log(array1); //[1,3,2]
```
### 2.今日无精进 
# Day10【2022年8月1日】 
**学习重点：** 总结一下js数组常用的一些原生方法（API)(下)
## 1.数组方法总结(下)
### 1.1 push()
将一个或多个元素添加到数组的末尾，返回该数组的新长度,会改变原数组。
**用法：**
```js
arr.push(element1, ..., elementN)
```
elementN
被添加到数组末尾的元素。

**返回值：**

当调用该方法时，新的 length 属性值将被返回。

**实例：**
```js
let array1 = [1,2,3,4];
let array2 = [5,6,7,8];
console.log(array1.push(5));// 5
console.log(array1);// [1, 2, 3, 4, 5]
//合并两个数组，array2（第二个数组） 过大时候少用
console.log(Array.prototype.push.apply(array1, array2));// 9
```
### 1.2 reduce()
 方法对数组中的每个元素按序执行一个由您提供的 reducer 函数，每一次运行 reducer 会将先前元素的计算结果作为参数传入，最后将其结果汇总为单个返回值。

第一次执行回调函数时，不存在“上一次的计算结果”。如果需要回调函数从数组索引为 0 的元素开始执行，则需要传递初始值。否则，数组索引为 0 的元素将被作为初始值 initialValue，迭代器将从第二个元素开始执行（索引为 1 而不是 0）。
**reducer** 逐个遍历数组元素，每一步都将当前元素的值与上一步的计算结果相加（上一步的计算结果是当前元素之前所有元素的总和）——直到没有更多的元素被相加。

**用法：**
```js
reduce(function(previousValue, currentValue, currentIndex, array) { /* ... */ }, initialValue)
```
callbackFn
一个 “reducer” 函数，包含四个参数：

previousValue：上一次调用 callbackFn 时的返回值。在第一次调用时，若指定了初始值 initialValue，其值则为 initialValue，否则为数组索引为 0 的元素 array[0]。
currentValue：数组中正在处理的元素。在第一次调用时，若指定了初始值 initialValue，其值则为数组索引为 0 的元素 array[0]，否则为 array[1]。
currentIndex：数组中正在处理的元素的索引。若指定了初始值 initialValue，则起始索引号为 0，否则从索引 1 起始。
array：用于遍历的数组。
initialValue 可选
作为第一次调用 callback 函数时参数 previousValue 的值。若指定了初始值 initialValue，则 currentValue 则将使用数组第一个元素；否则 previousValue 将使用数组第一个元素，而 currentValue 将使用数组第二个元素。

**返回值：**

使用 “reducer” 回调函数遍历整个数组后的结果。

**实例：**
```js
let array1 = [1,2,3,4];

console.log(array1.reduce((acc, cur) => { return acc + cur }));//10
```
### 1.3 reduceRight() 
方法接受一个函数作为累加器（accumulator）和数组的每个值（从右到左）将其减少为单个值。
//reduceRight() 方法对数组中的每个元素执行一个由您提供的函数。
// reduceRight() 方法接受一个函数作为参数，该函数调用一个累加器（accumulator）和当前值（currentValue），并且返回一个值。
// reduceRight() 方法会从数组的右侧开始，同时将累加器的值与当前值进行累加。
// reduceRight() 方法会把累加器的值作为数组中的最后一个值，并且返回这个值。
// reduceRight() 方法会把累加器的值作为数组中的最后一个值，并且返回这个值。

**用法：**
```js
arr.reduceRight(callback(accumulator, currentValue[, index[, array]])[, initialValue])
```
callback
一个回调函数，用于操作数组中的每个元素，它可接受四个参数：
accumulator
累加器：上一次调用回调函数时，回调函数返回的值。首次调用回调函数时，如果 initialValue 存在，累加器即为 initialValue，否则须为数组中的最后一个元素（详见下方 initialValue 处相关说明）。
currentValue
当前元素：当前被处理的元素。
index可选
数组中当前被处理的元素的索引。
array可选
调用 reduceRight() 的数组。
initialValue可选
首次调用 callback 函数时，累加器 accumulator 的值。如果未提供该初始值，则将使用数组中的最后一个元素，并跳过该元素。如果不给出初始值，则需保证数组不为空。
否则，在空数组上调用 reduce 或 reduceRight 且未提供初始值（例如 [].reduce( (acc, cur, idx, arr) => {} ) ）的话，会导致类型错误 TypeError: reduce of empty array with no initial value。

**返回值：**

执行之后的返回值。

**实例：**
```js
let array1 = [1,2,3,4];
console.log(array1.reduceRight((pre, cur) => { return pre + cur }));//10
```
### 1.4 reverse() 
方法将数组中元素的位置颠倒，并返回该数组。数组的第一个元素会变成最后一个，数组的最后一个元素变成第一个。该方法会改变原数组。

**用法：**

```js
 arr.reverse()
```
**返回值：**

颠倒后的数组。

**实例：**
```js
let array1 = [1,2,3,4];
console.log(array1.reverse());//[ 4, 3, 2, 1 ]
console.log(array1);//[ 4, 3, 2, 1 ]
```
### 1.5 shift() 
方法从数组中删除第一个元素，并返回该元素的值。此方法更改数组的长度。

**用法：**
```js
arr.shift()
```
**返回值：**

从数组中删除的元素; 如果数组为空则返回undefined 。

**实例：**
```js
let array1 = [1,2,3,4];
console.log(array1.shift());// 1
console.log(array1);// [2, 3, 4]
```
### 1.6 slice() 
方法返回一个新的数组对象，这一对象是一个由 begin 和 end 决定的原数组的浅拷贝（包括 begin，不包括end）。原始数组不会被改变。

**用法：**
```js
arr.slice([begin[, end]])
```
begin 可选
提取起始处的索引（从 0 开始），从该索引开始提取原数组元素。如果该参数为负数，则表示从原数组中的倒数第几个元素开始提取，slice(-2) 表示提取原数组中的倒数第二个元素到最后一个元素（包含最后一个元素）。如果省略 begin，则 slice 从索引 0 开始。如果 begin 超出原数组的索引范围，则会返回空数组。
end 可选
提取终止处的索引（从 0 开始），在该索引处结束提取原数组元素。slice 会提取原数组中索引从 begin 到 end 的所有元素（包含 begin，但不包含 end）。slice(1,4) 会提取原数组中从第二个元素开始一直到第四个元素的所有元素（索引为 1, 2, 3 的元素）。如果该参数为负数， 则它表示在原数组中的倒数第几个元素结束抽取。 slice(-2,-1) 表示抽取了原数组中的倒数第二个元素到最后一个元素（不包含最后一个元素，也就是只有倒数第二个元素）。如果 end 被省略，则 slice 会一直提取到原数组末尾。如果 end 大于数组的长度，slice 也会一直提取到原数组末尾。

**返回值：**

一个含有被提取元素的新数组。

**实例：**
```js
let array1 = [1,2,3,4];
console.log(array1.slice(0, 2));//[1, 2]
console.log(array1.slice(2));// [3, 4]
console.log(array1.slice(2, 4));// [3, 4]
console.log(array1.slice(2, -2));// []
console.log(array1.slice(-2, -3));// []
console.log(array1);// [1, 2, 3, 4]
```
### 1.7 some() 
方法测试数组中是不是至少有 1 个元素通过了被提供的函数测试。它返回的是一个 Boolean 类型的值。如果用一个空数组进行测试，在任何情况下它返回的都是false。

**用法：**
```js
arr.some(callback(element[, index[, array]])[, thisArg])
```
callback
用来测试每个元素的函数，接受三个参数：
element
数组中正在处理的元素。
index 可选
数组中正在处理的元素的索引值。
array可选
some()被调用的数组。
thisArg可选
执行 callback 时使用的 this 值。

**返回值：**

数组中有至少一个元素通过回调函数的测试就会返回true；所有元素都没有通过回调函数的测试返回值才会为 false。

**实例：**
```js
let array1 = [1,2,3,4];
console.log(array1.some((item) => { return item > 2 }));// true
console.log(array1.some((item) => { return item > 5 }));// false
```
### 1.8 sort() 
方法用原地算法对数组的元素进行排序，并返回数组。默认排序顺序是在将元素转换为字符串，然后比较它们的 UTF-16 代码单元值序列时构建的

由于它取决于具体实现，因此无法保证排序的时间和空间复杂性。 会改变原数组

**用法：**
```js
arr.sort([compareFunction])
```
compareFunction 可选
用来指定按某种顺序进行排列的函数。如果省略，元素按照转换为的字符串的各个字符的 Unicode 位点进行排序。
firstEl
第一个用于比较的元素。
secondEl
第二个用于比较的元素。

**返回值：**

排序后的数组。请注意，数组已原地排序，并且不进行复制。

**实例：**
```js
let array1 = [1,3,2,4];
console.log(array1.sort((a, b) => { return a - b }));// [1, 2, 3, 4]
console.log(array1.sort((a, b) => { return b - a }));// [4, 3, 2, 1]
console.log(array1);// [4, 3, 2, 1]
```
### 1.9 splice() 
方法通过删除或替换现有元素或者原地添加新的元素来修改数组，并以数组形式返回被修改的内容。此方法会改变原数组。
方法用于删除数组中的一部分，并返回被删除的元素。

**用法：**
```js
array.splice(start[, deleteCount[, item1[, item2[, ...]]]])
```
start
指定修改的开始位置（从 0 计数）。如果超出了数组的长度，则从数组末尾开始添加内容；如果是负值，则表示从数组末位开始的第几位（从 -1 计数，这意味着 -n 是倒数第 n 个元素并且等价于 array.length-n）；如果负数的绝对值大于数组的长度，则表示开始位置为第 0 位。
deleteCount 可选
整数，表示要移除的数组元素的个数。如果 deleteCount 大于 start 之后的元素的总数，则从 start 后面的元素都将被删除（含第 start 位）。如果 deleteCount 被省略了，或者它的值大于等于array.length - start(也就是说，如果它大于或者等于start之后的所有元素的数量)，那么start之后数组的所有元素都会被删除。如果 deleteCount 是 0 或者负数，则不移除元素。这种情况下，至少应添加一个新元素。
item1, item2, ... 可选
要添加进数组的元素，从start 位置开始。如果不指定，则 splice() 将只删除数组元素

**返回值：**

由被删除的元素组成的一个数组。如果只删除了一个元素，则返回只包含一个元素的数组。如果没有删除元素，则返回空数组。

**实例：**
```js

let array1 = [1,3,2,4];
console.log(array1.splice(1,2));//[ 3, 2 ]
console.log(array1);//[1,4]
```
### 1.10 toLocaleString() 
返回一个字符串表示数组中的元素。数组中的元素将使用各自的 toLocaleString 方法转成字符串，这些字符串将使用一个特定语言环境的字符串（例如一个逗号 ","）隔开

**用法：**
```js
arr.toLocaleString([locales[,options]]);
```
locales 可选
带有 BCP 47 语言标记的字符串或字符串数组，关于locales参数的形式与解释，请看Intl页面。
options 可选
一个可配置属性的对象，对于数字 Number.prototype.toLocaleString()，对于日期Date.prototype.toLocaleString().

**返回值：**

表示数组元素的字符串。

**实例：**
```js
let array1 = [1,3,2,4];
console.log(array1.toLocaleString());//1,3,2,4

```
### 1.11 toString() 
返回一个字符串，表示指定的数组及其元素。

**用法：**
```js
arr.toString()
```
**返回值：**

一个表示指定的数组及其元素的字符串。

**实例：**
```js
let array1 = [1,3,2,4];
console.log(array1.toString());//2 1,3,2,4
```
### 1.12 unshift() 
方法将一个或多个元素添加到数组的开头，并返回该数组的新长度（该方法修改原有数组）。

**用法：**
```js
arr.unshift(element1, ..., elementN)
```
elementN
要添加到数组开头的元素或多个元素。

**返回值：**

当一个对象调用该方法时，返回其 length 属性值。

**实例：**
```js

let array1 = [1,3,2,4];
console.log(array1.unshift(5));//5
console.log(array1);//[5, 1, 3, 2, 4]
```
### 1.13 values() 
方法返回一个新的 Array Iterator 对象，该对象包含数组每个索引的值。

**用法：**
```js
arr.values()
```
**返回值：**

一个新的 Array 迭代对象。

**实例：**
```js
let array1 = [1,3,2,4];
console.log(array1.values());// Array Iterator {}
console.log(array1);// [1, 3, 2, 4]
```
## 今日精进
leetcode 无重复字符的最长子串(滑块窗口解题)解题思路很重要。

# Day10【2022年8月2日】 
**学习重点：** 总结js基本对象Object常用方法（上）
## 1.Object方法总结（上）
### 1.1 assign()
Object.assign() 方法将所有可枚举（Object.propertyIsEnumerable() 返回 true）和自有（Object.hasOwnProperty() 返回 true）属性从一个或多个源对象复制到目标对象，返回修改后的对象。是浅拷贝的一种。对象是null或undefined时不会报错。如果目标对象与与源对象有相同的key，则源对象会覆盖目标对象。

**用法：**
```js
Object.assign(target, ...sources)
```
target目标对象，接收源对象属性的对象，也是修改后的返回值。sources源对象，包含将被合并的属性。

**返回值：**

目标对象

**实例：**
```js
let target = { a: 1, b: 2 };
let source = { b: 4, c: 5 };

let returnedTarget = Object.assign(target, source);
console.log(target); // { a: 1, b: 4, c: 5 }
console.log(returnedTarget); // { a: 1, b: 4, c: 5 }

target.a = 6;
console.log(target); // { a: 6, b: 4, c: 5 }
console.log(returnedTarget); // { a: 6, b: 4, c: 5 }

let target2 = {  };
let source2 = { a: 1, b: 2 };
let returnedTarget2 = Object.assign(target2, source2);
console.log(target2); // { a: 1, b: 2 }
console.log(returnedTarget2); // { a: 1, b: 2 }
```
### 1.2 create()
方法创建一个新对象，使用现有的对象作为新创建对象的原型（prototype）。浅拷贝。

**用法：**
```js 
Object.create(proto)
Object.create(proto, propertiesObject)
```
proto新创建对象的原型对象。
propertiesObject 可选
如果该参数被指定且不为 undefined，则该传入对象的自有可枚举属性（即其自身定义的属性，而不是其原型链上的枚举属性）将为新创建的对象添加指定的属性值和对应的属性描述符。这些属性对应于 Object.defineProperties() 的第二个参数。
proto 参数需为
null 或
除基本类型包装对象以外的对象
如果 proto 不是这几类值，则抛出一个 TypeError 异常。

**返回值：**

一个新对象，带着指定的原型对象及其属性。

**实例：**
```js
const person = {
  isHuman: false,
  printIntroduction: function() {
    console.log(`My name is ${this.name}. Am I human? ${this.isHuman}`);
  }
};

const me = Object.create(person);

me.name = 'Matthew'; // "name" is a property set on "me", but not on "person"
me.isHuman = true; // inherited properties can be overwritten

me.printIntroduction();
// expected output: "My name is Matthew. Am I human? true"
```

### 1.3 defineProperties() 
在一个对象上定义新的属性或修改现有属性，并返回该对象。可同时修改多个。

**用法：**
```js
Object.defineProperties(obj, props)
```
obj
在其上定义或修改属性的对象。
props
要定义其可枚举属性或修改的属性描述符的对象。对象中存在的属性描述符主要有两种：数据描述符和访问器描述符（更多详情，请参阅 Object.defineProperty()）。描述符具有以下键：
configurable
true 只有该属性描述符的类型可以被改变并且该属性可以从对应对象中删除。
默认为 false
enumerable
true 只有在枚举相应对象上的属性时该属性显现。
默认为 false
value
与属性关联的值。可以是任何有效的 JavaScript 值（数字，对象，函数等）。
默认为 undefined.
writable
true只有与该属性相关联的值被assignment operator (en-US)改变时。
默认为 false
get
作为该属性的 getter 函数，如果没有 getter 则为undefined。函数返回值将被用作属性的值。
默认为 undefined
set
作为属性的 setter 函数，如果没有 setter 则为undefined。函数将仅接受参数赋值给该属性的新值。
默认为 undefined

**返回值：**

修改后的对象

**实例：**
```js
let target3 = { a: 1};
target3.a; //get
target3.b = 2; // set
console.log(target3); // { a: 1, b: 2 }

let target4 = {a : 1, b : 2};
Object.defineProperties(target4, { 
    a : {
        value : 3,
        // writable : false, 是否可以修改
        // enumerable : true, 是否可以遍历
        // configurable : true 是否可以删除

    },
    c: {
        value: 3,
    },
    d: {
        value: 4,
    }
}
);
console.log(target4); // { a: 3, b: 2, c: 3, d: 4 }
```
直接拿出对象属性并修改相当于执行了get和set方法。
### 1.4 Object.defineProperty() 
在一个对象上定义一个新属性，或者修改一个对象的现有属性，并返回此对象。修改一个属性。添加的属性值是不可修改（immutable）的。

**用法：**
```js
Object.defineProperty(obj, prop, descriptor)
```
obj要定义属性的对象。prop要定义或修改的属性的名称或 Symbol 。descriptor要定义或修改的属性描述符。（传递的属性跟defineProperties一样）。

**返回值：**

修改后的对象

**实例：**
```js
let target5 = { a: 1, b: 2 };

Object.defineProperty(target5, 'a', { });
target5.a = 3;
console.log(target5); // { a: 3, b: 2 }

let target6 = { a: 1, b: 2 };
Object.defineProperty(target6, 'c', { value: 3 }); // 创建一个新属性
console.log(target6); // { a: 1, b: 2, c: 3 }
target6.c = 4; // 修改一个属性
console.log(target6); // { a: 1, b: 2, c: 3 }
```
待补充
### 1.5 entries()
返回一个给定对象自身可枚举属性的键值对数组，其排列与使用 for...in 循环遍历该对象时返回的顺序一致（区别在于 for-in 循环还会枚举原型链中的属性）。不改变原对象

**用法：**
```js
Object.entries(obj)
```
obj可以返回其可枚举属性的键值对的对象。
**返回值：**
给定对象自身可枚举属性的键值对数组。

**实例：**
```js
let target7 = { a: 1, b: 2 };
console.log(Object.entries(target7)); // [Array(2), Array(2)]0: (2) ['a', 1]1: (2) ['b', 2]length: 2[[Prototype]]: Array(0)
console.log(Object.keys(target7)); // ['a', 'b']
console.log(Object.values(target7));// [1, 2]

let target10 = { a: 1, b: 2 };
let entries = Object.entries(target10);
console.log(entries); // [ ['a', 1], ['b', 2] ]
console.log(target10);  // { a: 1, b: 2 }
```
### 1.6 freeze() 
冻结一个对象，不能修改，不能添加新属性，不能删除已有属性，不能修改该对象已有属性的可枚举性、可配置性、可写性，以及不能修改已有属性的值，冻结后对象的原型也不能修改。

**用法：**
```js
Object.freeze(obj)
```
obj
要被冻结的对象。

**返回值：**

被冻结的对象。

**实例：**
```js
let target8 = { a: 1, b: 2 };
 Object.freeze(target8);
 target8.a = 3;
 console.log(target8); // { a: 1, b: 2 }
 let target9 =[1,23,4,5,6,7,8,9,10];
Object.freeze(target9);
target9.push(11);
console.log(target9);   // [1, 23, 4, 5, 6, 7, 8, 9, 10, 11]
// TypeError: Cannot add property 9, object is not extensible
```
### 1.7 fromEntries() 
把键值对列表转换为一个对象。不改变原键值对列表而是生成一个新对象。

**用法：**
```js
Object.fromEntries(iterable);
```
iterable类似 Array 、 Map 或者其它实现了可迭代协议的可迭代对象。

**返回值：**

一个由该迭代对象条目提供对应属性的新对象。

**实例：**
```js
let target10 = { a: 1, b: 2 };
let entries = Object.entries(target10);
console.log(entries); // [ ['a', 1], ['b', 2] ]
Object.fromEntries(entries);
console.log(target10); // { a: 1, b: 2 }

//Map转换为对象
let map = new Map([['a', 1], ['b', 2]]);
console.log(Object.fromEntries(map)); // { a: 1, b: 2 }
```
### 1.8 getOwnPropertyDescriptor() 
方法返回指定对象上一个自有属性对应的属性描述符。（自有属性指的是直接赋予该对象的属性，不需要从原型链上进行查找的属性）

**用法：**
```js
Object.getOwnPropertyDescriptor(obj, prop)
```
obj需要查找的目标对象
prop目标对象内属性名称

**返回值：**

如果指定的属性存在于对象上，则返回其属性描述符对象（property descriptor），否则返回 undefined。

**实例：**
```js
let target11 = { a: 1, b: 2 };
let d = Object.getOwnPropertyDescriptor( target11, 'a' );
console.log(d);  // { value: 1, writable: true, enumerable: true, configurable: true }
let f = Object.getOwnPropertyDescriptor(target11 , 'c');
console.log(f); // undefined
```
### 1.9 getOwnPropertyDescriptors() 
方法用来获取一个对象的所有自身属性的描述符。
用法：

```js
Object.getOwnPropertyDescriptors(obj)
```
obj
任意对象

**返回值：**

所指定对象的所有自身属性的描述符，如果没有任何自身属性，则返回空对象。

**实例：**
```js
let target12 = { a: 1, b: 2 };
let d = Object.getOwnPropertyDescriptors( target12 );
console.log(d); // { a: { value: 1, writable: true, enumerable: true, configurable: true }, b: { value: 2, writable: true, enumerable: true, configurable: true } }

let target13 = {};
let d2 = Object.getOwnPropertyDescriptors( target13 );
console.log(d2); // {}
```
### 1.10 getOwnPropertyNames()
方法返回一个由指定对象的所有自身属性的属性名（包括不可枚举属性但不包括 Symbol 值作为名称的属性）组成的数组。

**用法：**
```js
Object.getOwnPropertyNames(obj)
```
obj
一个对象，其自身的可枚举和不可枚举属性的名称被返回。

**返回值：**

对应的字符串数组。

**实例：**
```js
let target14 = { a: 1, b: 2 };
Object.getOwnPropertyNames(target14).forEach(function(key) {
//['a','b']
    console.log(key);
});
// a b
let target15 = { a: 1, b: 2 };
 let b =Object.getOwnPropertyNames(target15)
    console.log(b); // [ 'a', 'b' ]
VM10599:3 (2) ['a', 'b']
```
## 2今日精进
leetcode 4. 寻找两个正序数组的中位数（二分法解题）
# Day11【2022年8月3日】 
**学习重点：** 总结js基本对象Object常用方法（中）
## 1.Object方法总结（中）
### 1.1 getOwnPropertySymbols()
返回一个给定对象自身的所有 Symbol 属性的数组。若对象没有smbol则返回空数组。

**用法：**
```js
Object.getOwnPropertySymbols(obj)
```
obj要返回 Symbol 属性的对象。

**返回值：**

在给定对象自身上找到的所有 Symbol 属性的数组。

**实例：**
```js 
let a = {};

Object.getOwnPropertySymbols(a);//[]

let b = {a:1};

Object.getOwnPropertySymbols(b);//[]

var obj = {};
var a = Symbol("a");
var b = Symbol.for("b");

obj[a] = "localSymbol";
obj[b] = "globalSymbol";

var objectSymbols = Object.getOwnPropertySymbols(obj);

console.log(obj); // {a: "localSymbol", Symbol(b): "globalSymbol"}
console.log(objectSymbols.length); // 2
console.log(objectSymbols)         // [Symbol(a), Symbol(b)]
console.log(objectSymbols[0])      // Symbol(a) 

```
### 1.2 getPrototypeOf()
> 返回指定对象的原型（内部`[[Prototype]]`属性的值）。

**用法：**
```js
Object.getPrototypeOf(object)
```
object要返回原型的对象。

**返回值：**

给定对象的则原型。如果没有继承属性，返回null。

**实例：**
```js
let a = {a:1};
let b = Object.create(a);
console.log(a); // {a: 1}
console.log(b); // {} 在原型链上没有a属性，但是在Object.create(a)上有a属性 Object.create(a)是a的一个实例 因此b也有a属性
console.log(b.a); // 1
console.log(Object.getPrototypeOf(b) === a); // true


```
### 1.3 hasOwn()
> 如果指定的对象具有指定的属性作为其自己的Object.hasOwn()属性，则静态方法返回。如果属性被继承或不存在，则该方法返回。 truefalse。
判断对象中是否具有某个属性用来替代Object.hasOwnProperty().
方法返回`true`— 即使属性值为`null`or `undefined`
**用法：**
```js
hasOwn(instance, prop)
```
instance要测试的对象实例。
prop要测试的属性的String名称或符号

**返回值：**

如果指定的对象直接定义了指定的属性true。否则false

**实例：**
```js
let obj = { a:0, b:1,c:null,d:undefined };
Object.hasOwn(obj, "a"); // true
Object.hasOwn(obj, "b"); // true
Object.hasOwn(obj, "c"); // true
Object.hasOwn(obj, "d"); // true
Object.hasOwn(obj, "e"); // false

```
### 1.4 hasOwnProperty()
返回一个布尔值，指示对象是否具有指定的属性作为它自己的属性（而不是继承它）。

**用法：**
```js
hasOwnProperty(prop)
```
prop要测试的属性的String名称或符号。

**返回值：**

true如果对象具有指定的属性作为自己的属性，则 返回；false 否则。

**实例：**
```js
let obj1 = {a:2 ,b:1};

obj1.hasOwnProperty('a'); // true
obj1.hasOwnProperty('b'); // true
obj1.hasOwnProperty('c'); // false
```
回看总结一下二者的区别。
for in可以查看原型上是否有该属性，而该方法只可查看自身属性，不包括原型
### 1.5 is()
确定两个值是否 相同。

**用法：**
```js
Object.is(value1, value2);
```
value1比较的第一个值
value2比较的第二个值

**返回值：**

true/false

**实例：**
```js
// Case 1: Evaluation result is the same as using ===
Object.is(25, 25);                // true
Object.is('foo', 'foo');          // true
Object.is('foo', 'bar');          // false
Object.is(null, null);            // true
Object.is(undefined, undefined);  // true
Object.is(window, window);        // true
Object.is([], []);                // false
const foo = { a: 1 };
const bar = { a: 1 };
Object.is(foo, foo);              // true
Object.is(foo, bar);              // false

// Case 2: Signed zero
Object.is(0, -0);                 // false
Object.is(+0, -0);                // false
Object.is(-0, -0);                // true
Object.is(0n, -0n);               // true

// Case 3: NaN
Object.is(NaN, 0/0);              // true
Object.is(NaN, Number.NaN)        // true

"" == false//true
Object.is("",false)//false
```
以下表示相等：（与==和===都不相同）
两个都undefined
两个都null
两者true或两者false
两个字符串长度相同，字符顺序相同
都是同一个对象（意味着两个值都引用内存中的同一个对象）
两个数字和
两个都+0
两个都-0
两个都NaN
或两者都非零且都非零且NaN两者具有相同的值

> 与==不相同。运算符在 `==`测试相等性之前对双方应用各种强制（如果它们不是相同的类型）（导致诸如 be 的行为 `"" == false`）`true`，但`Object.is`不会强制任何一个值。
> 
> yu===不相同。`Object.is()`和之间的唯一区别在于`===`它们对有符号零和 NaN 的处理。例如，`===` 运算符（和`==`运算符）将数值`-0` 和`+0`视为相等。此外，`===`运算符将 [`Number.NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/NaN)和[`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN)视为不相等。
### 1.6 isExtensible()
确定对象是否可扩展（是否可以添加新属性）。

**用法：**
```js
Object.isExtensible(obj)
```
**返回值：**

true/false

**实例：**
```js
let empty = {};
Object.isExtensible(empty); // === true

Object.preventExtensions(empty);
Object.isExtensible(empty); // === false


let sealed = Object.seal({});
Object.isExtensible(sealed); // === false


let frozen = Object.freeze({});
Object.isExtensible(frozen); // === false

let obj = {a:1,b:2};
Object.isExtensible(obj); // === true

```
默认情况下，对象是可扩展的：它们可以添加新属性，并且[[Prototype]]可以重新分配它们。Object.preventExtensions()可以使用、Object.seal()、Object.freeze()或之一将对象标记为不可扩展Reflect.preventExtensions()（Reflect反射）。
### 1.7 isFrozen()
对象是否被冻结。

**用法：**
```js
Object.isFrozen(obj)
```

**返回值：**

true/false

**实例：**
```js
let obj1 = {a:1,b:2};
Object.isFrozen(obj1); // === false

let obj2 = Object.freeze({a:1,b:2});
Object.isFrozen(obj2); // === true

let obj3 = Object.seal({a:1,b:2});
Object.isFrozen(obj3); // === true

let obj4 = Object.preventExtensions({a:1,b:2});
Object.isFrozen(obj4); // === true

let obj5 = Object.defineProperty({a:1,b:2},'c',{value:3});
Object.isFrozen(obj5); // ===  false  因为它没有被冻结

let obj6 = Object.defineProperty({a:1,b:2},'c',{value:3,writable:false});
Object.isFrozen(obj6); // === false 因为它没有被冻结

```
### 1.8 isPrototypeOf()
检查一个对象是否存在于另一个对象的原型链中。

**用法：**
```js
isPrototypeOf(object)
```
**返回值：**

true/false

**实例：**
```js
function Foo() {}
function Bar() {}
function Baz() {}

Bar.prototype = Object.create(Foo.prototype);
Baz.prototype = Object.create(Bar.prototype);

const foo = new Foo();
const bar = new Bar();
const baz = new Baz();

// prototype chains:
// foo: Foo <- Object
// bar: Bar <- Foo <- Object
// baz: Baz <- Bar <- Foo <- Object
console.log(Baz.prototype.isPrototypeOf(baz));    // true
console.log(Baz.prototype.isPrototypeOf(bar));    // false
console.log(Baz.prototype.isPrototypeOf(foo));    // false
console.log(Bar.prototype.isPrototypeOf(baz));    // true
console.log(Bar.prototype.isPrototypeOf(foo));    // false
console.log(Foo.prototype.isPrototypeOf(baz));    // true
console.log(Foo.prototype.isPrototypeOf(bar));    // true
console.log(Object.prototype.isPrototypeOf(baz)); // true

```
### 1.9 isSealed()
确定对象是否被密封。如果一个对象是不可扩展的，并且它的所有属性都是不可配置的，因此是不可移除的（但不一定是不可写的），那么它就是密封的。（要求更少）

**用法：**
```js
Object.isSealed(obj)
```
**返回值：**

true/false

**实例：**
```js
let obj1 = {a:1,b:2};
Object.isSealed(obj1); // === false

let obj2 = Object.seal({a:1,b:2});
Object.isSealed(obj2); // === true

let obj3 = Object.freeze({a:1,b:2});
Object.isFrozen(obj3); // === true

let obj4 = Object.preventExtensions({a:1,b:2});
Object.isExtensible(obj4); // === false

let obj5 = Object.defineProperty({a:1,b:2},'c',{value:3});
Object.isExtensible(obj5); // === true
```
### 1.10 keys()
返回给定对象自己的可枚举属性名称Object.keys()的数组，以与正常循环相同的顺序进行迭代。

**用法：**
```js
Object.keys(obj)
```
**返回值：**

表示给定对象的所有可枚举属性的字符串数组。

**实例：**
```js
let obj1 = {a:1,b:2};
Object.keys(obj1); // ['a', 'b']
//对象没有长度的概念用这个方法获取对象的长度
```
## 2.今日精进
leetcode 最长回文数。
既然选择了这一行就要热爱它，保持热爱，把它当成一种兴趣，形成持续内驱动力才能走的更远，不论在任何行业都要保持持续学习，否则就会淹没在历史的潮流中，坚持精进。


# Day12【2022年8月4日】 
**学习重点：** 总结js基本对象Object常用方法（下）
## 1.Object方法总结（下）
### 1.1 preventExtensions()
让对象不能添加新属性，变得不可扩展。只对其自身属性有效，该操作不可逆。

**用法：**
```js
Object.preventExtensions(obj)
```
**返回值：**

不可扩展的对象

**实例：**
```js
let obj = {a:1};
Object.preventExtensions(obj);
obj.b = 2;
try {
    Object.defineProperty(obj, 'c', {value: 3});
}
catch(e) {
    console.log(e.message);
    }
console.log(obj);
// Cannot define property c, object is not extensible
// {a: 1}
```
### 1.2 propertyIsEnumerable()  
方法返回一个布尔值，表示指定的属性是否可枚举。可以判断该属性是否可以被for...in遍历

**用法：**
```js
obj.propertyIsEnumerable(prop)
```
**返回值：**
true/false
**实例：**
```js
let arr =  [11, 2, 3];
let obj = {a: 1};

arr.propertyIsEnumerable('length'); // false
//数组要用下标访问
arr.propertyIsEnumerable('0'); // true
arr.propertyIsEnumerable('11'); // false
obj.propertyIsEnumerable('a'); // true
```
### 1.3 seal()
封闭一个对象，阻止添加新属性并将所有现有属性标记为不可配置（不能删除
）。当前属性的值只要原来是可写的就可以改变。
**用法：**
```js
Object.seal(obj)
```
**返回值：**
对象
**实例：**
```js
let obj = {a:1};
Object.seal(obj);
obj.a = 3;
console.log(obj);// {a: 3}
delete obj.a;
console.log(obj);//{a: 3}
```
### 1.4 .setPrototypeOf() 
设置一个指定的对象的原型 ( Prototype）到另一个对象或 null。
该方法性能不好推荐使用Object.create() 

### 1.5 toLocaleString() 
> 返回一个该对象的字符串表示。此方法被用于派生对象为了特定语言环境的目的（locale-specific purposes）而重载使用。
**用法：**
```js
obj.toLocaleString();
```
**返回值：**
字符串
**实例：**
```js
let obj = {a:1};

obj.toLocaleString() //'[object Object]'
```
### 1.6 toString()
返回一个表示该对象的字符串。

**用法：**
```js
obj.toString()
```
**返回值：**

字符串

**实例：**
```js
let obj = {a:1};
obj.toString(); // "[object Object]"
// 重写toString方法 可以输出对象的属性 和值
// 如果对象属性是对象 则会输出对象的属性和值 如果对象属性是数组 则会输出数组的属性和值 如果对象属性是函数 则会输出函数的属性和值
// 如果对象属性是字符串 则会输出字符串的属性和值 如果对象属性是数字 则会输出数字的属性和值 如果对象属性是布尔值 则会输出布尔值的属性和值
// 如果对象属性是null 则会输出null的属性和值 如果对象属性是undefined 则会输出undefined的属性和值 如果对象属性是symbol 则会输出symbol的属性和值
// 如果对象属性是object 则会输出object的属性和值 
obj.toString = function() {
    return 'hello';
}
console.log(obj.toString()); // hello

obj.toString; // function toString() { [native code] }

function Dog(name) {
    this.name = name;
  }
  
  const dog1 = new Dog('Gabby');
  // 重写toString方法
  Dog.prototype.toString = function dogToString() {
    return `${this.name}`;
  };
  
  console.log(dog1.toString());//"Gabby"
```
### 1.7 valueOf() 
返回指定对象的原始值。

**用法：**
```js
object.valueOf()
```
**返回值：**
该对象的原始值。

**实例：**
```js
let obj = {a:1};

obj.valueOf();
{a: 1}
```

![1659585027860.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/26d3ce2b6223448ab40683377bcf574e~tplv-k3u1fbpfcp-watermark.image?)
### 1.8 values()
返回一个给定对象自身的所有可枚举属性值的数组，值的顺序与使用for...in循环的顺序相同 ( 区别在于 for-in 循环枚举原型链中的属性 )。

**用法：**
```js
Object.values(obj)
```
**返回值：**

一个包含对象自身的所有可枚举属性值的数组。

**实例：**
```js
let obj = {a:1};
obj.values(); // [1]

// 不可枚举的属性不能被for...in循环遍历
let obj2 = {a:1};
Object.defineProperty(obj2, 'b', {value: 2, enumerable: false});
Object.values(obj2); // [1]

console.log(obj2);
for (let key in obj2) {
    console.log(key);
} // a 
```
## 今日精进
现在是一个信息爆炸的时代，很多杂乱的信息影响我们，提升自我要学会做减法，提炼关键信息，总结方法，若能打通不同知识点间的联系找到共同点那进步会很快，做事也是如此，思维和方法很重要。
# Day12【2022年8月5日】 
**学习重点：** 函数相关知识总结
函数是**头等 (** first-class **)** 对象，因为它们可以像任何其他**对象**一样具有属性和方法。它们与其他对象的区别在于函数可以被调用。简而言之，它们是`Function`对象。每个 JavaScript 函数实际上都是一个 `Function` 对象。运行 `(function(){}).constructor === Function // true` 便可以得到这个结论。

ECMAScript 中的函数是对象，因此有属性和方法。每个函数都有两个属性：length
和 prototype。其中，length 属性保存函数定义的命名参数的个数

## 1.函数定义的方式目前来说分为以下几种
```js
//函数声明方式定义函数 ，函数声明方式定义函数
function test(arg){
    console.log(arg);
}

// 函数表达式定义函数
var test = function(arg){
    console.log(arg);
}

// 箭头函数定义函数
var test = (arg) => {
    console.log(arg);
}
// 构造函数Function定义函数 
//不推荐影响性能 会被解析两次
//Function构造函数创建的函数仅在全局范围内执行。
var test = new Function('arg','console.log(arg)');

//匿名函数定义函数 无函数名称 
 var test = function(arg){
    console.log(arg);
}

//立即执行函数定义函数 跟名称一样立即执行
//第一个参数是函数名称，第二个参数是函数体 
(function(arg){
    console.log(arg);
})('hello');
```
## 2.形参和实参
形参（参数 parameter）：定义 函数时，小括号中的参数，是用来接收参数用的，在函数内部 作为变量使用
实参（参数 argument）：调用 函数时，小括号中的参数，是用来把数据传递到 函数内部 用的

**例子：** arg在定义阶段是形参，调用函数时，'hello'作为实参传入函数中。
```js
function  test(arg){
    console.log(arg);
}

test('hello');
```
## 3.return
一般在函数中return的值才有意义，例如在业务代码中return 一个状态 或者对数据进行一系列处理都要return出去，这样才能运用到别处，这里列举一些return需要注意的事项。
如果一个函数中没有使用 return 语句，则它默认返回undefined。要想返回一个特定的值，则函数必须使用 return 语句来指定一个要返回的值。(使用new关键字调用一个构造函数除外)。

如下图 new关键字调用构造函数不用return有人会返回-**后文会有解释**
<img src="https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/b5ea7deae81943e4b158723444766f0e~tplv-k3u1fbpfcp-watermark.image?" alt="1659690175036.png" width="70%" />
**函数就会立即停止执行并退出。return 语句后面的代码不会被执行。**
```js
function test(arg){
    console.log(arg);
    return 'hello';
    console.log('world');
}

test('hello'); //hello
```
**一个函数可以有多个返回值：**
```js
// 一个函数可以有多个返回值
function test(arg){
    if(arg == 'hello'){
        return 'hello';
    } else {
        return 'world';
    }
}
```
**提前解释函数时使用：**
```js
//提前终止函数执行
function test(arg){
    return ;
    console.log(arg);
}
```
**严格模式对函数也有一些限制：**
- 函数不能以 eval 或 arguments 作为名称；
- 函数的参数不能叫 eval 或 arguments； 
- 两个命名参数不能拥有同一个名称。

如果违反上述规则，则会导致语法错误，代码也不会执行。

## 4.箭头函数

箭头函数不能使用 arguments、super 和new.target，也不能用作构造函数。此外，箭头函数也没有 prototype 属性。箭头函数是ES6中的提出来的，它没有prototype，也没有自己的this指向，更不可以使用arguments参数，所以不能New一个箭头函数。

### 箭头函数与普通函数的区别

**（1）箭头函数比普通函数更加简洁**

-   如果没有参数，就直接写一个空括号即可,多个参数，用逗号分割
```js
// 没有参数需要括号
let getRandom = () => { return Math.random(); };
// 多个参数需要括号
let sum = (a, b) => { return a + b; };
```
-   如果只有一个参数，可以省去参数的括号
```js
//一个参数省略参数的括号 省略return 后的代码不会被执行 
//如果函数体的返回值只有一句，可以省略大括号
let test = a =>  a;
// 以下两种写法都有效，而且返回相应的值

let double = (x) => { return 2 * x; };
let triple = (x) => 3 * x;

// 可以赋值
let value = {};
let setName = (x) => x.name = "Matt";
setName(value);
console.log(value.name); // "Matt"
```
-   如果函数体不需要返回值，且只有一句话，可以给这个语句前面加一个void关键字。最常见的就是调用一个函数：
```js
let fn = () => void doesNotReturn();
```
**（2）箭头函数没有自己的this**

箭头函数不会创建自己的this， 所以它没有自己的this，它只会在自己作用域的上一层继承this,默认是定义箭头函数的上下文。所以箭头函数中this的指向在它在定义时已经确定了，之后不会改变。

箭头函数没有自己的this，说默认绑定外层this式错误的说法，其实箭头函数的this类似于变量查找规则，这样显得箭头函数中有自己的this，本质上式符合变量查找规则。

在对sayColor()的两次调用中，this 引用的都是 window 对象，因为这个箭头函数是在 window 上下文中定义的：
```js
window.color = 'red'; 
let o = { 
 color: 'blue' 
}; 
let sayColor = () => console.log(this.color); 
sayColor(); // 'red' 
o.sayColor = sayColor; 
o.sayColor(); // 'red' 
```
如果在事件回调或定时回调中调用某个函数时，this 值指向的并非想要的对象。此时将
回调函数写成箭头函数就可以解决问题。这是因为箭头函数中的 this 会保留定义该函数时的上下文：
```js
function King() { 
 this.royaltyName = 'Henry'; 
 // this 引用 King 的实例
 setTimeout(() => console.log(this.royaltyName), 1000); 
} 
function Queen() { 
 this.royaltyName = 'Elizabeth'; 
 // this 引用 window 对象
 setTimeout(function() { console.log(this.royaltyName); }, 1000); 
} 
new King(); // Henry 
new Queen(); // undefined
```
**（3）箭头函数继承来的this指向永远不会改变**

```
var id = 'GLOBAL';
var obj = {
  id: 'OBJ',
  a: function(){
    console.log(this.id);
  },
  b: () => {
    console.log(this.id);
  }
};
obj.a();    // 'OBJ'
obj.b();    // 'GLOBAL'
new obj.a()  // undefined
new obj.b()  // Uncaught TypeError: obj.b is not a constructor
```

对象obj的方法b是使用箭头函数定义的，这个函数中的this就永远指向它定义时所处的全局执行环境中的this，即便这个函数是作为对象obj的方法调用，this依旧指向Window对象。需要注意，定义对象的大括号`{}`是无法形成一个单独的执行环境的，它依旧是处于全局执行环境中。

**（4）call()、apply()、bind()等方法不能改变箭头函数中this的指向**

```
var id = 'Global';
let fun1 = () => {
    console.log(this.id)
};
fun1();                     // 'Global'
fun1.call({id: 'Obj'});     // 'Global'
fun1.apply({id: 'Obj'});    // 'Global'
fun1.bind({id: 'Obj'})();   // 'Global'
```

**（5）箭头函数不能作为构造函数使用**

构造函数在new的步骤在上面已经说过了，实际上第二步就是将函数中的this指向该对象。 但是由于箭头函数时没有自己的this的，且this指向外层的执行环境，且不能改变指向，所以不能当做构造函数使用。

**（6）箭头函数没有自己的arguments**

箭头函数没有自己的arguments对象。在箭头函数中访问arguments实际上获得的是它外层函数的arguments值。

**（7）箭头函数没有prototype**

**（8）箭头函数不能用作Generator函数，不能使用yeild关键字**

**（9）不能New一个箭头函数**

**new操作符的实现步骤如下：**

1.  创建一个对象({})
2.  将构造函数的作用域赋给新对象（也就是将对象的__proto__属性指向构造函数的prototype属性）将该属性链接至构造函数的原型对象 。
3.  指向构造函数中的代码，构造函数中的this指向该对象（也就是为这个对象添加属性和方法）
```js
//没添加属性
function Car(make, model, year) {
        let a = 1;
        // this.make = make;
        // this.model = model;
        // this.year = year;
      }
      
    //   const car1 = new Car("Honda", "Civic", "2000");
    let car1 = new Car();
    console.log(car1);
```
```js
//添加属性
function Car(make, model, year) {
        let a = 1;
        this.make = make;
        this.model = model;
        this.year = year;
      }
      
      const car1 = new Car("Honda", "Civic", "2000");
    // let car1 = new Car();
      
      console.log(car1); // Car {make: 'Honda', model: 'Civic', year: '2000'}
```
4.  返回新的对象（ 如果该函数没有返回对象，则返回this）
5.  所以，上面的第二、三步，箭头函数都是没有办法执行的，箭头函数没有自己的原型对象prototype，没有自己的this。

## 5.函数声明、表达式和函数作为值传递
### 5.1函数声明提升
事实上，JavaScript 引擎在加载数据时对它们是区别对待的。JavaScript 引擎在任何代码执行之前，会先读取函数声明，并在执行上下文中生成函数定义。而函数表达式必须等到代码执行到它那一行，才会在执行上下文中生成函数定义。因为函数声明会在任何代码执行之前先被读取并添加到执行上下文。这个过程叫作函数声明提升。
**如下所示**
```js
// 函数声明形式没问题 
console.log(sum(10, 10)); 
function sum(num1, num2) { 
 return num1 + num2; 
}
//函数表达式形式报错 let var const 一样会报错
console.log(sum(10, 10)); 
let sum = function(num1, num2) { 
 return num1 + num2; 
};
```
### 5.2函数作为值传递
因为函数名在 ECMAScript 中就是变量，所以函数可以用在任何可以使用变量的地方。这意味着不
仅可以把函数作为参数传给另一个函数，而且还可以在一个函数中返回另一个函数。
```js
function callSomeFunction(someFunction, someArgument) {
return someFunction(someArgument);
}
```

## 6.arguments
> 它是一个类数组对象，包含调用函数时传入的所有参数。这个对象只有以 function 关键字定义函数（相对于使用箭头语法创建函数）时才会有。虽然主要用于包含函数参数，但 arguments 对象其实还有一个 callee 属性，是一个指向 arguments 对象所在函数的指针。
arguments对象不是一个 Array 。它类似于Array，但除了 length 属性和索引元素之外没有任何Array属性。

箭头函数没有自己的arguments对象。在箭头函数中访问arguments实际上获得的是它外层函数的arguments值。

**类数组转化为数组一些方法。**

用使用Array.from()方法或扩展运算符将参数转换为真实数组还可以用slice
```js
function test(arg) {
    console.log(arguments);
    //var args = Array.from(arguments);
    //var args = [...arguments];
    // var args = [].slice.call(arguments)
    var args = Array.prototype.slice.call(arguments);
    console.log(args);
}

test(1);

// Arguments [1, callee: ƒ, Symbol(Symbol.iterator): ƒ]
// [1]
```



- 函数表达式与函数声明是不一样的。函数声明要求写出函数名称，而函数表达式并不需要。没有名称的函数表达式也被称为匿名函数。
- JavaScript 中函数定义与调用时的参数极其灵活。arguments 对象，以及 ES6 新增的扩展操作符，可以实现函数定义和调用的完全动态化。
- 函数内部也暴露了很多对象和引用，涵盖了函数被谁调用、使用什么调用，以及调用时传入了什么参数等信息。
- JavaScript 引擎可以优化符合尾调用条件的函数，以节省栈空间。
- 闭包的作用域链中包含自己的一个变量对象，然后是包含函数的变量对象，直到全局上下文的变量对象。
- 通常，函数作用域及其中的所有变量在函数执行完毕后都会被销毁。
- 闭包在被函数返回之后，其作用域会一直保存在内存中，直到闭包被销毁。
- 函数可以在创建之后立即调用，执行其中代码之后却不留下对函数的引用。
- 立即调用的函数表达式如果不在包含作用域中将返回值赋给一个变量，则其包含的所有变量都会被销毁。
- 虽然 JavaScript 没有私有对象属性的概念，但可以使用闭包实现公共方法，访问位于包含作用域中定义的变量。
- 可以访问私有变量的公共方法叫作特权方法。
- 特权方法可以使用构造函数或原型模式通过自定义类型中实现，也可以使用模块模式或模块增强模式在单例对象上实现。

[eval()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/eval)总结

因为Console控制台的实质，即eval（）全局函数函数，所以当输入的表达式或语句没有返回值时，会返回 undefined 。
而浏览器默认要打印出执行函数的返回值，才会打印undefined；如果在控制台定义的函数return出一个具体的值，那么控制台会打印这个具体的值。
## 今日精进
理论与实践：
理论知识，是基础。掌握了这个基础，在实践过程中，就会游刃有余，得心应手。缺少了理论指导，实践很难朝着正确的方向发展。只有理论没有实践，学再多都是空谈，这是嘴把式，更无法的充分理论。实践出真知，实践是检验真理的唯一标准，理论与实践相结合，才是学习的本质。

# Day13【2022年8月6日】 
今日休息，外出
## 今日精进

高效的时间管理会让你快人一步，同是24小时一天，每个人所能做的有意义的事都是不尽相同的。可以通过以下几个方式进行时间管理，做时间的主人：1、列出计划，可根据自身情况列举出每天每周每月计划，完成后打勾没完成写明理由鞭策自我，定期复盘。 2、拒绝拖延，提高工作效率拖延会导致一系列的问题，提高工作效率会让你事半功倍。 3、拒绝无意义的社交无意义的事情，把专注度都放在自身主要事情上。4、利用碎片化时间提升自我，每天会有很多碎片化时间可以利用比如坐地铁利可用好这些碎片化时间来看看有意义的书籍。
# Day14【2022年8月7日】 
今日休息
## 今日精进
一个人内心足够强大，无论外界发生什么，都能从容应对。


# 参考资料
-   JavaScript高级程序设计（第4版）
-  [MDN](https://developer.mozilla.org/en-US/)
-  [鲨鱼哥的面试题总结](https://github.com/BigSharkLx/front-end-interview/blob/main/5%20offer%E6%94%B6%E5%89%B2%E6%9C%BA%E4%B9%8BJavaScript%E7%AF%87.md)
-  解锁前端面试体系核心攻略
-  [细数JavaScript中那些遍历和循环](https://cuggz.blog.csdn.net/article/details/107649549)

#  结语

志同道合的小伙伴可以加我，一起交流进步，我们坚持每日精进（互相监督思考学习，如果坚持不下来我可以监督你）。另外共享学习资料的小伙伴也可以联系我，进群技术交流资料free共享，我们交换资料一起努力鸭！
——>[点击这里](https://juejin.cn/pin/7123425224455880740)

# 备注
按照时间顺序倒叙排列，完结后按时间顺序正序排列方便查看知识点,工作日更新。