# 背景

## background属性详解

-  background-color：颜色
  - `transparent`：透明(`默认`)
  - `Keyword`：颜色关键字
  - `HEX`：十六进制色彩模式
  - `RGB`或`RGBA`：RGB/A色彩模式
  - `HSL`或`HSLA`：HSL/A色彩模式
  - `Color1/Color2`：覆盖颜色，背景颜色可能是`Color1`，若背景图像无效则使用`Color2`代替`Color1`
-  background-image：图像
  - `none`：无图像(`默认`)
  - `url()`：图像路径
-  background-repeat：图像平铺方式
  - `repeat`：图像在水平方向和垂直方向重复(`默认`)
  - `repeat-x`：图像在水平方向重复
  - `repeat-y`：图像在垂直方向重复
  - `no-repeat`：图像仅重复一次
  - `space`：图像以相同间距平铺且填充整个节点
  - `round`：图像自动缩放直到适应且填充整个节点
-  background-attachment：图像依附方式
  - `scroll`：图像随页面滚动而移动(`默认`)
  - `fixed`：图像不会随页面滚动而移动
-  background-position：图像起始位置
  - `Position`：位置，可用任何长度单位，第二个位置(Y轴)不声明默认是`50%`(默认`0% 0%`)
  - `Keyword`：位置关键字`left、right、top、bottom、center`，可单双使用，第二个关键字不声明默认是`center`
-  background-size：图像尺寸模式
  - `auto`：自动设置尺寸(`默认`)
  - `cover`：图像扩展至足够大，使其完全覆盖整个区域，图像某些部分也许无法显示在区域中
  - `contain`：图像扩展至最大尺寸，使其宽度和高度完全适应整个区域
  - `Size`：尺寸，可用任何长度单位，第二个尺寸(高)不声明默认是`auto`
-  background-origin：定位区域(与`background-position`结合使用)
  - `padding-box`：图像相对填充定位(`默认`)
  - `border-box`：图像相对边框定位
  - `content-box`：图像相对内容定位
-  background-clip：绘制区域
  - `border-box`：图像被裁剪到边框与边距的交界处(`默认`)
  - `padding-box`：图像被裁剪到填充与边框的的交界处
  - `content-box`：图像被裁剪到内容与填充的交界处
-  background-blend-mode：混合模式
  - `normal`：正常(`默认`)
  - `color-burn`：颜色加深
  - `color-dodge`：颜色减淡
  - `color`：颜色
  - `darken`：变暗
  - `difference`：差值
  - `exclusion`：排除
  - `hard-light`：强光
  - `hue`：色相
  - `lighten`：变亮
  - `luminosity`：亮度
  - `multiply`：正片叠底
  - `overlay`：叠加
  - `saturation`：饱和度
  - `screen`：滤色
  - `soft-light`：柔光

总体来说，`background`简单易用，以下三点可能需加注意。

- `repeat`和`position`包含后缀为`-x`和`-y`这两个子属性，若单独声明使用`x`或`y`即可
- `position`的`x`和`y`允许负值，当赋值`x`时正值向右负值向左，当赋值`y`时正值向下负值向上
- `background`声明多个图像路径时，若不声明`position`，那么首个图像定位在节点最顶部，剩余图像依次顺序显示
- 对于兼容性比较低的浏览器，`size`不能在`background`中连写，需单独编写

## 贴顶背景

```html
<style>
    .pasted-bg{
        display:flex;
        justify-content:center;
        align-items:center;
        height: 500px;
        /* 背景颜色 背景图像 仅重复一次 起始位置(center,top) 尺寸 */
        background: #000 url('https://static.yangzw.vip/codepen/mountain.jpg') no-repeat center center/auto 500px;
        font-weight: bold;
        font-size: 50px;
        color: #fff;
    }
</style>
<div class="pasted-bg">Background</div>
```

![](CSS背景、阴影、动画/贴图背景.gif)

## 多重背景

CSS3的`background`不仅仅增加了`size`、`origin`和`clip`这三个子属性，还增加了`多重背景`这个强大功能。多重背景可从上到下从左到右拼接背景图像，也可叠加背景图像。

```html
<style>
    .overlying-bg {
        margin-left: 20px;
        width: 400px;
        height: 400px;
        background-image: url("https://static.yangzw.vip/codepen/logo.svg"), url("https://static.yangzw.vip/codepen/mountain.jpg");
        background-repeat: repeat, no-repeat;
        background-position: left, center;
        background-size: auto 100px, auto 400px;
    }
</style>
<div class="overlying-bg"></div>
```

声明顺序靠前的背景图像的层叠等级比较高，叠加背景图像时，靠前的背景图像尽量使用`png`格式才能让靠后的背景图像显示，否则可能遮挡靠后的背景图像。

![](CSS背景、阴影、动画/image-20210706191051848.png)

## 渐变

CSS渐变分为三种，每一种都有自身的特点。

-  **线性渐变**：沿着指定方向从起点到终点逐渐改变颜色，渐变形状是一条`直线`
-  **径向渐变**：沿着任意方向从圆心往外面逐渐改变颜色，渐变形状是一个`圆形`或`椭圆形`
-  **锥形渐变**：沿着顺时针方向从圆心往外面逐渐改变颜色，渐变形状是一个`圆锥体`

> 渐变不是核心点，之后用到了再看

# 阴影

- 想要盒子轮廓产生阴影效果，使用`box-shadow`
- 想要文本轮廓产生阴影效果，使用`text-shadow`
- 想要透明图像的非透明部分轮廓产生阴影效果，使用`fliter:drop-shadow()`

三个阴影都具备以下大部分参数，只要认识以下参数，阴影效果随时能上手。

- OffsetX：水平偏移，阴影的水平位置(必选)

  - `Offset`：偏移，可用任何长度单位，允许负值，正值向右负值向左(默认`0`)

- OffsetY

  ：垂直偏移，阴影的垂直位置(必选)

  - `Offset`：偏移，可用任何长度单位，允许负值，正值向下负值向上(默认`0`)

- Blur：模糊半径，阴影的清晰程度(虚色)

  - `Length`：长度，可用任何长度单位，值越大边缘越模糊(默认`0`)

- Spread：扩展距离，阴影的实体尺寸(实色)

  - `Length`：长度，可用任何长度单位，允许负值，正值扩大负值缩小(默认`0`)

- Color：投影颜色

  - `transparent`：透明(`默认`)
  - `Keyword`：颜色关键字
  - `HEX`：十六进制色彩模式
  - `RGB`或`RGBA`：RGB/A色彩模式
  - `HSL`或`HSLA`：HSL/A色彩模式

- Position：投影位置

  - `outset`：阴影显示在外部(`默认`)
  - `inset`：阴影显示在内部

# 变换

变换分为`2D变换`和`3D变换`。2D变换在平面上操作，3D变换在空间上操作，2D和3D的概念相信很多同学都会了吧。变换可理解成将节点复制一份并生成新的图层，原节点隐藏，使用新节点进行变换操作。

声明`transform-style`可实现`2D变换`和`3D变换`间的切换，不同变换空间需使用对应的变换函数。当然`transform-style`需声明在父节点中，即需发生变换的节点的父节点。

-  **flat**：所有变换效果在平面上呈现(`默认`)
-  **preserve-3d**：所有变换效果在空间上呈现

笔者已将`2D变换函数`和`3D变换函数`整理好，在不同变换空间使用对应的变换函数即可。

-  translate()：位移
  -  **translate(x,y)**：2D位移
  -  **translate3d(x,y,z)**：3D位移
  -  **translateX(x)**：X轴位移，等同于`translate(x,0)`或`translate3d(x,0,0)`
  -  **translateY(y)**：Y轴位移，等同于`translate(0,y)`或`translate3d(0,y,0)`
  -  **translateZ(z)**：Z轴位移，等同于`translate3d(0,0,z)`
  - 描述
    - 单位：`Length`长度，可用任何长度单位，允许负值
    - 默认：XYZ轴不声明默认是`0`
    - 正值：沿X轴向右位移/沿Y轴向上位移/沿Z轴向外位移
    - 负值：沿X轴向左位移/沿Y轴向下位移/沿Z轴向内位移
-  scale()：缩放
  -  **scale(x,y)**：2D缩放
  -  **scale3d(x,y,z)**：3D缩放
  -  **scaleX(x)**：X轴缩放，等同于`scale(x,1)`或`scale3d(x,1,1)`
  -  **scaleY(y)**：Y轴缩放，等同于`scale(1,y)`或`scale3d(1,y,1)`
  -  **scaleZ(z)**：Z轴缩放，等同于`scale3d(1,1,z)`
  - 描述
    - 单位：`Number`数值或`Percentage`百分比，允许负值
    - 默认：XYZ轴不声明默认是`1`或`100%`
    - 正值：`0<(x,y,z)<1`沿X轴缩小/沿Y轴缩小/沿Z轴变厚，`(x,y,z)>1`沿X轴放大/沿Y轴放大/沿Z轴变薄
    - 负值：`-1<(x,y,z)<0`翻转沿X轴缩小/沿Y轴缩小/沿Z轴变厚，`(x,y,z)<-1`翻转沿X轴放大/沿Y轴放大/沿Z轴变薄
-  skew()：扭曲
  -  **skew(x,y)**：2D扭曲
  -  **skewX(x)**：X轴扭曲，等同于`skew(x,0)`
  -  **skewY(y)**：Y轴扭曲，等同于`skew(0,y)`
  - 描述
    - 单位：`Angle`角度或`Turn`周
    - 默认：XY轴不声明默认是`0`
    - 正值：沿X轴向左扭曲/沿Y轴向下扭曲
    - 负值：沿X轴向右扭曲/沿Y轴向上扭曲
-  rotate()：旋转
  -  **rotate()**：2D旋转
  -  **rotate3d(x,y,z,a)**：3D旋转，`[x,y,z]`是一个向量，数值都是`0~1`
  -  **rotateX(a)**：X轴旋转，等同于`rotate(1,0,0,a)`，正值时沿X轴向上逆时针旋转，负值时沿X轴向下顺时针旋转
  -  **rotateY(a)**：3D Y轴旋转，等同于`rotate(0,1,0,a)`，正值时沿Y轴向右逆时针旋转，负值时沿Y轴向左顺时针旋转
  -  **rotateZ(a)**：3D Z轴旋转，等同于`rotate(0,0,1,a)`，正值时沿Z轴顺时针旋转，负值时沿Z轴逆时针旋转
  - 描述
    - 单位：`Angle`角度或`Turn`周
    - 正值：2D旋转时顺时针旋转
    - 负值：2D旋转时逆时针旋转
-  matrix()：矩阵
  -  **matrix(a,b,c,d,e,f)**：2D矩阵(位移、缩放、扭曲、旋转的综合函数)
  -  **matrix(a,b,c,d,e,f,g,h,i,j,k,l,m,n,o,p)**：3D矩阵(位移、缩放、扭曲、旋转的综合函数)
-  perspective()：视距
  - `Length`：长度，可用任何长度单位

`transform`的使用场景很多，不局限于某种特定场景，若结合`transition`和`animation`使用还必须注意性能问题。

