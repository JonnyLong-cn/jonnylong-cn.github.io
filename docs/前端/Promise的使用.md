# 为何会有Promise？

根据这篇文章： [深入理解JS事件循环机制](深入理解JS事件循环机制.md)知道，Promise、Generator、async/await都是为了实现异步编程

传统方式是通过回调函数、事件监听、发布订阅模式实现的，Promise的出现大大丰富了异步编程的实现。

# Promise的三种状态

![](Promise的使用/image-20210627093602174.png)

Promise译作承诺，**这个承诺一旦从等待状态变成为其他状态就永远不能更改状态了**，比如说一旦状态变为 resolved 后，就不能再次改变为Fulfilled。

# Promise的常规使用

## 承诺-兑现承诺结构

承诺：

`resolve(value)`：如果任务成功完成并带有结果 value。

`reject(error)`：如果出现了 error，error 即为 error 对象。

```js
let promise = new Promise(function(resolve, reject) {
    // executor（生产者代码）
});
```

`new Promise(arg)`里面的参数arg是生成者执行的函数

兑现承诺：

`.then()`：

- `.then`的第一个参数是一个函数，该函数将在`promise resolved`后运行并接收结果。
- `.then`的第二个参数也是一个函数，该函数将在`promise rejected`后运行并接收error。

`.catch()`：捕捉错误

`.finally()`：最后执行

## 例子

如下面这个加载脚本的函数，加载过程较慢，因此需要将它封装成异步函数

使用回调函数的形式：

```js
function loadScript(src, callback) {
    // 创建DOM节点
    let script = document.createElement('script');
    script.src = src;
    script.onload = () => callback(null, script);
    script.onerror = () => callback(new Error(`Script load error for ${src}`));
    document.head.append(script);
}
```



```js
function loadScript(src) {
    return new Promise(function (resolve, reject) {
        let script = document.createElement('script');
        script.src = src;

        script.onload = () => resolve(script);
        script.onerror = () => reject(new Error(`Script load error for ${src}`));

        document.head.append(script);
    });
}
```



```js
let promise = loadScript("https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.11/lodash.js");
promise.then(
    script => alert(`${script.src} is loaded!`),
    error => alert(`Error: ${error.message}`)
);
promise.then(script => alert('Another handler...'));
```



 