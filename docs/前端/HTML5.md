# H5中新增的语义标签

- `<section>` 表示区块
- `<article>` 表示文章。如文章、评论、帖子、博客
- `<header>` 表示页眉
- `<footer>` 表示页脚
- `<nav>` 表示导航
- `<aside>` 表示侧边栏。如文章的侧栏
- `<figure>`表示媒介内容分组。
- `<mark>` 表示标记 (用得少)
- `<progress>` 表示进度 (用得少)
- `<time>` 表示日期

## H5表单

H5中新增的表单类型：

- `email` 只能输入email格式。自动带有验证功能。
- `tel` 手机号码。
- `url` 只能输入url格式。
- `number` 只能输入数字。
- `search` 搜索框
- `range` 滑动条
- `color` 拾色器
- `time` 时间
- `date` 日期
- `datetime` 时间日期
- `month` 月份
- `week` 星期

`<fieldset>` 标签将表单里的内容进行打包，代表一组；而`<legend> `标签的则是 fieldset 里的元素定义标题。

## 表单属性

- `placeholder` 占位符（提示文字）
- `autofocus` 自动获取焦点
- `multiple` 文件上传多选或多个邮箱地址
- `autocomplete` 自动完成（填充的）。on 开启（默认），off 取消。用于表单元素，也可用于表单自身(on/off)
- `form` 指定表单项属于哪个form，处理复杂表单时会需要
- `novalidate` 关闭默认的验证功能（只能加给form）
- `required` 表示必填项
- `pattern` 自定义正则，验证表单。

## 表单事件

- `oninput()`：用户输入内容时触发，可用于输入字数统计。
- `oninvalid()`：验证不通过时触发。比如，如果验证不通过时，想弹出一段提示文字，就可以用到它。

# 多媒体

音频：

```html
<audio src="music/yinyue.mp3" autoplay controls> </audio>
```

视频：

```html
<video src="video/movie.mp4" controls autoplay></video>
```

- `autoplay` 自动播放。写成`autoplay` 或者 `autoplay = ""`，都可以。
- `controls` 控制条。（建议把这个选项写上，不然都看不到控件在哪里）
- `loop` 循环播放。
- `preload` 预加载 同时设置 autoplay 时，此属性将失效。

- `width`：设置播放窗口宽度。
- `height`：设置播放窗口的高度。

# 拖拽

可以拖拽的元素：即页面中设置了 `draggable="true"` 属性的元素。

**拖拽元素的事件监听**：（应用于拖拽元素）

- `ondragstart`当拖拽开始时调用
- `ondragleave` 当**鼠标离开拖拽元素时**调用
- `ondragend` 当拖拽结束时调用
- `ondrag` 整个拖拽过程都会调用

# 全屏

开启/关闭全屏显示：

```js
requestFullscreen()   //让元素开启全屏显示
cancleFullscreen()    //让元素关闭全屏显示
```

检查当前是否全屏：

```js
document.fullScreen
```

# 存储

两种存储方式：

1、`window.sessionStorage` 会话存储：

- 保存在内存中。
- **生命周期**为关闭浏览器窗口。也就是说，当窗口关闭时数据销毁。
- 在同一个窗口下数据可以共享。

2、`window.localStorage` 本地存储：

- 有可能保存在浏览器内存里，有可能在硬盘里。
- 永久生效，除非手动删除（比如清理垃圾的时候）。
- 可以多窗口共享。

Web存储的特性：

（1）设置、读取方便。

（2）容量较大，`sessionStorage`约5M、`localStorage`约20M。

（3）只能存储字符串，可以将对象`JSON.stringify()`编码后存储。

常见API：

+ `setItem(key, value)`：设置存储内容
+ `getItem(key)`：读取存储内容
+ `removeItem(key)`：删除存储内容
+ `clear()`：清空存储内容
+ `key(n)`：通过key获取value

使用方式：

```js
sessionStorage.setItem(key, value);
localStorage.setItem(key, value);
```

# 网络状态

我们可以通过 `window.onLine` 来检测用户当前的网络状况，返回一个布尔值。另外：

- `window.online`：用户网络连接时被调用。
- `window.offline`：用户网络断开时被调用（拔掉网线或者禁用以太网）。

网络监听实例：

```js
window.addEventListener('online', function () {
	alert('网络连接建立！');
});
window.addEventListener('offline', function () {
	alert('网络连接断开！');
})
```



