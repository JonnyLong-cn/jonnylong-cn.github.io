# 字符串和字符数组

## 字符串转字符数组

```js
let str = "abcdefg";
let arr = str.split("");
```

## 字符数组转字符串

```js
let arr = ["abc","d","ef","ghi"];
let resStr = arr.join("");
```

> 不要用`toString()`，否则转出的字符串会带上`,`

# 字符串和数字数组

## 字符串转数字数组

就是在转出的字符数组用map方法进一步转为数字类型

```js
let str = "010110101100";
let arr = str.split('').map((item)=>{return +item});
```

## 数字数组转字符串

```js
let arr = [0,1,0,1,1,0,0];
let resStr = arr.join("");
```

# 进制转换

## 定义其他进制数

```js
// 二进制
let num = 0b1001;
// 八进制
let num = 077;
// 十六进制
let num = 0xff;
```

## 进制转换

最终输出的是字符串

```js
let num = 0b1001;
let str = num.toString(16);
```

# 字符串和数字

## 数字转字符串

```js
let num = 255;
let str = num.toString();
```

## 字符串转数字

```js
let str = "00012";
let num = Number(str);
// 另一种写法
let num = +str;
```

# ASCII和字符

## 字符转ASCII

```js
let ch = 'A';
let ascii = ch.charCodeAt(); // 65
```

## ASCII转字符

```js
let ascii = 66;
let res = String.fromCharCode(ascii); // B
```

# 修改字符串某个位置字符

JS中字符串不支持直接修改，不可setter

## 转为数组后修改

```js
let str = "aaaaa";
let arr = str.split('');
arr[2]='b';
let resStr = arr.join('');
console.log(resStr); // aabaa
```

封装成函数：

```js
String.prototype.replaceStr = function (index, ch) {
    let arr = this.split('');
    arr[pos] = ch;
    return arr.join('');
}

let str = "aaaaa";
let res = str.replaceStr(2, 'b');
console.log(res); // aabaa
```

## substring

```js
String.prototype.replaceStr = function (index, ch) {
    return this.substring(0, index) + ch + this.substring(index + 1);
}

let res = str.replaceStr(2, 'b');
console.log(res); // aabaa
```

# 创建m*n数组

## map+fill

```js
let m = 4;
let n = 5;
let arr = new Array(m).fill('').map((item, index) => { return new Array(n).fill(0) });
console.log(arr);
```

## 两层循环

```js
let m = 4;
let n = 5;
let arr = [];
for (let i = 0; i < m; i++) {
    arr[i] = [];
    for (let j = 0; j < n; j++) {
        arr[i][j] = 0;
    }
}
console.log(arr);
```

# 数组和集合

```js
 let arr = [1,2,3,2,3,2,3,2,3,6];
 // 数组转集合
 let set = new Set(arr);
 // 集合转数组
 let res = [...set];

 console.log(set);
 console.log(res);
```

# Map操作

## 遍历

```js
let map = new Map();
map.set("Lily", 21);
map.set("Jack", 24);
map.set("Alice", 15);
for (let item of map.entries()) {
    console.log(item);
}
for (let item of map.keys()) {
    console.log(item);
}
for (let item of map.values()) {
    console.log(item);
}

/*********************
[ 'Lily', 21 ]
[ 'Jack', 24 ]
[ 'Alice', 15 ]
Lily
Jack
Alice
21
24
15
*********************/
```

## 通过Map的值排序

```js
let map = new Map();
map.set('a', 2);
map.set('b', 10);
map.set('c', -8);
map.set('d', 3);
const list = [...map.keys()];
list.sort((a, b) => map.get(a) - map.get(b));
console.log(list);

/*
[ 'c', 'a', 'd', 'b' ]
*/
```

