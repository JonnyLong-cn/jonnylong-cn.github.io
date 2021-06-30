# 一、path
文件操作在 Node.js 编程中使用频率很高，路径处理是文件操作的前提，Node.js 通过 path 模块提供了路径处理的基础 API

## Windows和POSIX
当在 Windows 操作系统上运行时， path 模块会假定正被使用的是 Windows 风格的路径（C:\\temp\\myfile.html），而在 POSIX 操作系统会默认使用 POSIX 的路径风格（/tmp/myfile.html）

> POSIX是UNIX系统的设计标准，如Linux、MacOS

`path.basename()`方法用于返回一个路径的 basename

```bash
// Windows 下执行
path.basename('C:\\temp\\myfile.html'); // myfile.html

// POSIX 下执行
path.basename('C:\\temp\\myfile.html'); //C:\\temp\\myfile.html
```
## path 属性
 + `path.basename`: 返回 path 最后一部分
 + `path.delimiter`: 返回操作系统路径界定符，Windows 返回`;`，POSIX 返回`: `
 + `path.dirname`：返回文件目录名
 + `path.extname`：返回路径的拓展名（jquery.min.js 拓展名是 .js）
 + `path.isAbsolute`：检测路径是否是绝对路径
 + `path.sep`：返回路径分隔符，Windows 返回`\`POSIX 返回`/`
## path 方法
 + `parse(path)`：解析路径成一个对象
 + `format(parseObject)`：将对象反解析成路径
 + `normalize(path)`：规范化给定的path
 + `join([...paths])`：路径拼接
 + `path.relative(from, to)`：根据当前工作目录返回 from 到 to 的相对路径
 + `path.resolve([...paths])`：将路径或路径片段的序列解析为绝对路径
```js
const path = require('path');
// parse 解析路径
let res1 = path.parse('/home/user/dir/file.txt');
let res2 = path.parse('G:\\src\\components\\file.js');
console.log(res1);
console.log(res2);
// format 反解析到路径
let fm = path.format({
    root: '/',
    dir: '/home/user/dir',
    base: 'file.txt',
});
console.log(fm);
// normalize 规范化
let nr = path.normalize('../foo\/../bar//baz/\/\\\asdf/quux/../image');
console.log(nr);
// join 拼接
let jo = path.join('/foo', 'bar', 'baz/asdf', 'quux', '..');
console.log(jo);
// relative 当前工作目录返回 from 到 to 的相对路径
let re = path.relative('/data/orandea/test/aaa', '/data/orandea/impl/bbb');
console.log(re);
// resolve 将路径或路径片段的序列解析为绝对路径ss
let reso1 = path.resolve('/foo/bar', '/tmp/file/');
let reso2 = path.resolve('wwwroot', 'static_files/pic', '../image.gif');
console.log(reso1);
console.log(reso2);
```
输出如下：
```bash
{
  root: '/',
  dir: '/home/user/dir',
  base: 'file.txt',
  ext: '.txt',
  name: 'file'
}
{
  root: 'G:\\',
  dir: 'G:\\src\\components',
  base: 'file.js',
  ext: '.js',
  name: 'file'
}
/home/user/dir\file.txt
..\bar\baz\asdf\image
\foo\bar\baz\asdf
..\..\impl\bbb
G:\tmp\file
G:\JSTest\nodeTest\wwwroot\static_files\image.gif
```
# 二、事件
## 引入events
```js
const EventEmitter = require('events');
const ee = new EventEmitter();
```
EventEmitter的实例对象ee会维护一个listener 数组，监听的事件会放入到这个数组中
## 监听
### on
```js
const ee = new EventEmitter();
ee.on('foo', () => console.log('a'));
```
1.EventEmitter 实例会维护一个 listener 数组，每次 listener 默认会被添加到**数组尾部。**

2.每次添加 listener 不会检查是否添加过，多次调用 on 传入相同的 eventName 和 listener，会导致 listener 被添加多次
### prependListener
```js
const ee = new EventEmitter();
ee.prependListener('foo', () => console.log('a'));
```
与on类似，只不过是放在listener 数组**头部**。
### once
如果希望 listener 被触发一次后就不再触发，可以使用 once 来绑定事件
```js
const ee = new EventEmitter();
ee.once('foo', () => console.log('a'));
```
## 触发
### 基本使用
使用：`emitter.emit(eventName[, ...args])`

```js
const EventEmitter = require('events');
const myEmitter = new EventEmitter();
// 第一个监听器。
myEmitter.once('event', function firstListener() {
    console.log('第一个监听器');
});
// 第二个监听器。
myEmitter.on('event', function secondListener(arg1, arg2) {
    console.log(`第二个监听器中的事件有参数 ${arg1}、${arg2}`);
});
// 第三个监听器
myEmitter.prependListener('event', function thirdListener(...args) {
    const parameters = args.join(', ');
    console.log(`第三个监听器中的事件有参数 ${parameters}`);
});
console.log(myEmitter.listeners('event'));
myEmitter.emit('event', 1, 2, 3, 4, 5);
console.log('***********************************');
myEmitter.emit('event', 'Alice', 'Bob', 'Lily', 'June');
```
输出结果：
```bash
G:\JSTest\nodeTest>node index.js
[
  [Function: thirdListener],
  [Function: firstListener],
  [Function: secondListener]
]
第三个监听器中的事件有参数 1, 2, 3, 4, 5
第一个监听器
第二个监听器中的事件有参数 1、2
***********************************
第三个监听器中的事件有参数 Alice, Bob, Lily, June
第二个监听器中的事件有参数 Alice、Bob
```
### this的指向
```js
const EventEmitter = require('events');
const myEmitter = new EventEmitter();
myEmitter.on('event', (a, b) => {
    console.log(a, b);
    console.log(this);
    console.log(this === myEmitter);
});
myEmitter.emit('event', 'a参数', 'b参数');
```
输出结果：
```bash
a参数 b参数
EventEmitter {
  _events: [Object: null prototype] { event: [Function] },
  _eventsCount: 1,
  _maxListeners: undefined
}
true
```
### 异步调用
EventEmitter 以注册的顺序同步地调用所有 listener，这样可以确保事件的正确排序，listener 可以使用`setImmediate()`和`process.nextTick()`方法切换到异步的操作模式。
```js
const EventEmitter = require('events');
const myEmitter = new EventEmitter();
myEmitter.on('event', (a, b) => {
  setTimeout(() => {
    console.log('异步地发生');
  },1000);
});
myEmitter.emit('event', 'a', 'b');
```
## 卸载
### off/removeListener
off 方法是 removeListener 方法的别名，用于清理事件绑定

使用：`emitter.removeListener(eventName, listener) `
```js
const callback = (stream) => {
  console.log('已连接');
};
server.on('connection', callback);
// ...
server.removeListener('connection', callback);
```
`removeListener()`最多**只会从监听器数组中移除一个监听器。** 如果监听器被多次添加到指定`eventName`的监听器数组中，则必须多次调用`removeListener()`才能移除所有实例。

### removeAllListeners
使用：`emitter.removeAllListeners([eventName])`

有参数就移除eventName所有的的监听器，如果不指定eventName则移除事件对象emitter所有的监听器

# 三、process
process 对象是一个全局变量，是一个 **EventEmitter 实例**，提供了当前 **Node.js 进程的信息和操作方法。**
## 系统信息
process 对象提供了属性用于返回关键系统信息，常用的有
+ title：进程名称，默认值 node，程序可以修改，可以让错误日志更清晰
+ pid：当前进程 pid
+ ppid：当前进程的父进程 pid
+ platform：运行进程的操作系统（aix、drawin、freebsd、linux、openbsd、sunos、win32）
+ version：Node.js 版本
+ env：当前Shell的所有环境变量

## 属性
### stdin & stdout
标准输入和输出

```js
process.stdin.pipe(process.stdout)
```
### process.execPath
process.execPath 属性返回执行当前脚本的 Node 二进制文件的绝对路径

### process.argv
返回一个数组，内容是执行脚本时的参数，但前两项固定，分别为：

1.执行当前脚本的 Node 二进制文件的绝对路径

2.当前执行文件绝对路径
```js
console.log(process.argv);
```
控制台输出：
```bash
G:\JSTest\nodeTest>node index.js hello China
[
  'G:\\All tools installation\\Node.js\\node.exe',
  'G:\\JSTest\\nodeTest\\index.js',
  'hello',
  'China'
]
```
### process.execArgv
返回命令行参数数组
```js
console.log(process.execArgv);
```
控制台输出：
```bash
G:\JSTest\nodeTest>node --inspect index.js
Debugger listening on ws://127.0.0.1:9229/e2c7f755-62a4-4f68-89df-210aa37e2117
For help, see: https://nodejs.org/en/docs/inspector
[ '--inspect' ]
```
## 方法
+ `process.chdir()`：切换工作目录到指定目录
+ `process.cwd()`：返回运行当前脚本的工作目录的路径，也就是执行 node 命令时候的目录
+ `process.exit()`：退出当前进程
+ `process.memoryUsage()`：返回 Node.js 进程的内存使用情况

## 事件
### exit
触发条件：

1.显式调用`process.exit()`方法

2.事件循环不再需要执行任何其他工作
```js
process.on('exit', (code) => {
    console.log(`退出码: ${code}`);
});
```
### uncaughtException
当前进程抛出一个没有被捕捉的错误时，会触发`uncaughtException`事件

```js
process.on('uncaughtException', function (err) {
	console.error(err.stack);
});
```
### beforeExit
在退出前触发，即事件循环被清空后没有其他工作要安排

```js
process.on('beforeExit', (code) => {
	console.log('进程 beforeExit 事件的代码: ', code);
});
```
# 四、文件
## API风格
下面示例展示了不同风格 API 调用`fs.stat`方法
### callback风格
`callback(err, returnValue)`

1.err：如果程序处理出现异常，错误信息放在回调函数的第一个参数，如果没有错误 err 为 null

2.returnValue：程序正常处理完成后结果放在回调函数第二个参数
```js
const fs = require('fs');
fs.stat('.', (err, stats) => {
    if (err) {
        // 处理错误。
    } else {
        // 使用 stats
    }
});
```
### fs promise API
> `require('fs/promises')` v14 后可用
```js
const fs = require('fs').promises;
// const fs = require('fs/promises');
fs.stat('.').then(stats => {
    // 使用 stats
}).catch(error => {
    // 处理错误
});
```

### promisify

```js
const util = require('util');
const fs = require('fs');

const stat = util.promisify(fs.stat);
stat('.').then(stats => {
  // 使用 stats
}).catch(error => {
  // 处理错误
});
```

### 同步方法

fs 为大部分方法提供了一个同步版本，命名规则是方法名称后面添加 `Sync` ，比如`fs.readFile`和`fs.readFileSync`，stat 方法也有对应的同步版本

```js
const fs = require('fs');
try {
    const stats = fs.statSync('.');
    // 使用stats
} catch(error) {
    // 处理错误
}
```

## 文件读取

### fs.readFile

`fs.readFile(path[, options], callback)` 是最常用的读取文件方法，用于**异步读取文件的全部内容**

```js
const fs = require('fs');

/**
 * encoding: 编码格式
 * 'r': Open file for reading
 */
fs.readFile('./123.txt', { encoding: 'utf8', flag: 'r' }, (err, data) => {
    if (err){
        throw err;
    }
    console.log(data);
});
```

## 文件写入

### fs.writeFile

`fs.writeFile(file, data[, options], callback)`

- `file`：文件名或文件描述符
- `data`：常用的主要是 string 和 buffer
- `callback(err)`

当 `file` 是文件名时，则异步地写入数据到文件，如果文件已存在，则**覆盖文件内容**

```js
const fs = require('fs');

const data = Buffer.from('Hello,World!');
fs.writeFile('./123.txt', data, err => {
    if (err) throw err;
    console.log('文件已被保存');
});
```

### fs.appendFile

`fs.appendFile(path, data[, options], callback)` 将数据追加到文件尾部，如果文件不存在则创建该文件

```js
const fs = require('fs');

const data = Buffer.from('\n花开堪折直须折，莫待无花空折枝');
fs.appendFile('./123.txt', data, err => {
    if (err) throw err;
    console.log("追加完成");
})
```

# 五、buffer和stream

## buffer







