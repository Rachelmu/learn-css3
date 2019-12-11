# css3总结

## css选择器
### css3选择器分为五大类：基本选择器、层次选择器、伪类选择器、伪元素和属性选择器

### 基本选择器
- 通配选择器 *
- 元素选择器 E
- ID选择器 #id
- 类选择器 .class
- 群组选择器 selector1,selectorN

### 层次选择器
- 后代选择器（包含选择器） E F
- 子选择器              E>F
- 相邻兄弟选择器         E+F
- 通用选择器            E～F

### 动态伪类选择器
#### CSS3的伪类选择器可以分成六种：动态伪类选择器、目标伪类选择器、语言伪类选择器、UI状态伪类选择器、结构伪类选择器和否定伪类选择器。
#### 伪类选择器语法书写时和其他的CSS选择器写法有所区别，都以冒号（：）开头。
- 动态伪类选择器
  + 链接伪类选择器 E:link
  + 链接伪类选择器 E:visited
  + 用户行为伪类选择器 E:active
  + 用户行为伪类选择器 E:hover
  + 用户行为伪类选择器 E:focus
- 目标伪类选择器
  + 选择匹配E的所有元素，且匹配元素被相关URL指向 E:target
- 语言伪类选择器
  + 语言伪类选择器是根据元素的语言编码匹配元素  E:lang
- UI元素状态伪类选择器
  + 选中状态伪类选择器    E:checked
  + 启用状态伪类选择器    E:enabled
  + 不可用状态伪类选择器   E:disabled
- 结构伪类选择器
  + 可以根据元素在文档树中的某些特性（如相对位置）定位到它们。
    - E:first-child
    - E:last-child
    - E:root
    - E F:nth-child(n)
    - E F:nth-last-child(n)
    - E:nth-of-type(n)
    - E:nth-last-of-type(n)
    - E:first-of-type
    - E:last-of-type
    - E:only-child
    - E:only-of-type
    - E:empty
#### 参数n为关键词“odd”奇数（2n-1）、参数n为关键词“even”偶数（2n）
- 否定伪类选择器
  + 用来定位不匹配该选择器的元素  :not()
- 伪元素
  + 双冒号与单冒号在CSS3中主要用来区分伪类和伪元素
  + 选择文本块的第一个字母，除非在同一行中包含一些其他元素 ::first-letter
  + 用来匹配元素的第一行文本 ::first-line
  + 可以插入额外内容的位置,要为伪元素生成内容，还需要配合content属性 ::before ::after
  + 用来匹配突出显示的文本  ::selection （仅接受两个属性，一个是background,另一个是color）
- 属性选择器
  + E[attr]
  + E[attr=val]
  + E[attr|=val] val、val-
  + E[attr~=val] val元素属性中要包含val，并不仅是字符串。
  + E[attr*=val] val任何位置只要包含了字符串
  + E[attr^=val] val以开头的任何字符
  + E[attr$=val] val以结尾的任何字符

## css边框
- border-width: 设置元素边框的粗细
- border-color: 设置元素边框的颜色
- border-style: 设置元素边框的类型
```
border: border-width border-style border-color;
```
#### border-(top/right/bottom/left)-style 写单独边框
+ solid 四条边
+ solid dotted 上下 左右
+ solid dotted dashed 上 左右 下
+ solid dotted dashed inse 上 右 下 左

### border-style值
+ none    无边框
+ hidden  用于表时除外，对于表，hidden用于解决边框冲突
+ dotted  点状边框
+ dashed  虚线边框
+ solid   实线边框
+ double  双线，宽度等于border-width的值
+ groove  3D凹槽边框，其效果取决于border-color的值
+ ridge   3D垄状边框，其效果取决于border-color的值
+ inset   3D inset边框，其效果取决于border-color的值
+ outset  3D outset边框，其效果取决于border-color的值
+ inherit 应该从父元素继承边框央视。部分浏览器不支持这个属性

### border-color 属性
+ border-color: [ color(颜色值) | transparent] {1,4} | inherit

### border-image 属性
+ border-image: none(默认值) | image(背景图片) [ number(用来设置边框或者边框背景图片的大小) | percentage(用来设置边框或者边框背景图片的大小) ] {1,4} [/ border-width {1,4}] ? [(三个参数是用来设置边框图片的铺放方式)stretch(会拉伸边框背景图片) | repeat(会重复边框背景图片) | round(平铺边框背景图片)] {0,2}
+ Internet Explorer 不支持 border-image 属性。
+ 如果省略值，会设置其默认值
+ 详细属性方法分解（仅仅理解，并不能真分解）
    - border-image-source   引入背景图片 
    - border-image-slice    切割引入背景图片
    - border-image-width    边框图片的宽度
    - border-image-repeat   边框背景图片的排列方式
+ border-image-source: url(image url)
+ border-image-slice: [number | percentage] {1,4} && fill ?  number可以有1到4个值，可以是数值或者是百分比
+ border-image-width [length | percentage | number | auto] {1,4} 用来设置背景图片的显示大小，其实也可以理解为border-width。
+ border-image-repeat [stretch | repeat | round] {1,2}  用来制定边框背景图片的排列，其默认值为stretch。只接受两个参数，一个水平的排列方式，一个垂直排列方式。

### border-radius 属性
```
border-radius: none | <lenght> {1,4} [/<length> {1,4}] ?
```
- none: 默认值，表示元素没有圆角。
- length: 由浮点数字和单位标识符组成的长度值。不可用是负值。
- 如果要设置没有圆角，一定要设置数值为0，none无效。
- 可拆出四个子属性,先Y轴再X轴。
    + border-top-left-radius
    + border-top-right-radius
    + border-bottom-left-radius
    + border-bottom-right-radius
- border-radius包含两个参数值，第一个是水平圆角半径值，第二个垂直圆角半径值。
- border-radius支持除去Webkit内核浏览器下图片的圆角，图片圆角可以放在背景图里
- 表格圆角，当表格样式属性border-collapse是collapse时，表格不能正常显示，只有border-collapse属性值为separate时，表格圆角才能正常显示。
- 圆形
    + 元素的宽度和高度相同
    + 圆角的半径值为元素宽度或宽度的一半或者直接设置圆角半径值为50%
- 半圆
    + 制作上半圆或下半圆，元素的宽度值是高度值的2倍，而且圆角半径值为元素的高度值
    + 制作左半圆或右半圆，元素的高度值是宽度值的2倍，而且圆角半径值为元素的宽度值
- 扇形
    + 使用border-radius属性制作四分之一圆形。
    + 遵遁“三通，一不同”，三同指元素的宽度、高度和圆角半径值相同。一不同指圆角位置不同。
- 椭圆
    + 元素宽度是高度的2倍，而且border-radius的水平半径等于元素宽度，垂直半径等于元素高度
    + 垂直椭圆刚好与水平椭圆的参数相反

### box-shadow属性的语法及参数
```
box-shadow: none | [<length> <length> <length> ? <length>? || <color>],[<length> <length> <length>? <lenght> ?|| <color>]+
```
+ none:默认值，元素没有任何阴影效果
+ inset:阴影类型
+ x-offset:阴影水平偏移量
+ y-offset:阴影垂直偏移量
+ blur-radius:阴影模糊半径
+ spread-radius:阴影扩展半径
+ color:阴影颜色

### background 属性
#### backgroun-color 属性
```
background-color: transparent || <color>
```
+ transparent：默认值，不设置任何颜色的情况下透明色。
+ color：颜色参数，颜色名，rgb，hls值，十六制值
#### backgorund-image属性
```
backgroun-image: none || <url>
```
+ none: 默认值
+ url: 背景图片的地址
#### background-repeat属性
```
background-repeat: repeat || repeat-x || repeat-y || no-repeat
```
+ repeat: 背景沿着X轴和Y轴同时平铺
+ repeat-x: 背景图沿元素的X轴平铺
+ repeat-y: 背景图沿着元素的Y轴平铺
+ no-repeat: 不进行任何平铺
#### background-attachment属性
```
background-attachment: scroll || fixed
```
+ scroll: 默认值，背景图片会随浏览器滚动条一起滚动
+ fixe: 背景图片固定不动
#### background-position属性
```
background-position: <percentage> || <length> || [left|center|right] [,top|center|bottom]
```
+ 设置元素背景图片的位置，默认值为（0,0）|| (0%,0%) || (left top)
#### background-origin绘制图片的起点
+ 根据自己的需求改变背景图片的background-position起始位置
```
backgroun-origin: padding || border || conternt
backgroun-origin: padding-box || border-box || conternt-box
```
+ IE9+才支持的语法
+ padding-box(padding):默认值，决定background-position起始位置从padding的外边缘(border的内边缘)开始显示背景图
+ border-box(border):决定background-position起始位置从border的外边缘开始展示背景图
+ content-box(content):决定background-position起始位置从content的外边缘（padding的内边缘）开始显示背景图片
+ IE8版本background-origin的默认值为border
#### background-clip 裁切属性
+ padding-box: 背景颜色到padding的外边缘，但不会超出边框的范围。
+ border-box: 背景图片在边框下，这个也是background-clip的默认值
+ content-box: 背景仅在内容区域绘制，不会超出padding和边框的范围
```
background-clip: border-box || padding-box || content-box
```
+ Gecko内核浏览器（firefox3.6版本以前content-box不支持）,语法如下
```
background-clip: border || padding
```
+ text属性：只在Webkit内核才有效，要配合Webkit内核的私有属性text-fill-color:transparent可以制作背景图片填充文本的效果。
```
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
```
#### background-size 背景尺寸属性
```
background-size: auto || <length> || <perentage> || cover || contain
```
+ auto: 默认值。将保持背景片的原始高度和宽度。
+ length: 取具体的整数值（例如px值），将改变背景图片的大小。
+ percentage:取值为百分值。同样改变背景图片的大小，但此值是相对于元素但宽度来进行计算的，并不是根据背景图片的宽度来进行计算的
+ cover: 将背景图片放大，以适合铺满整个容器。
+ contain: 保持背景图片本身的宽高比，将背景图像缩放到宽度或高度正好适应所定义背景容器的区域。
### background-break内联元素背景图像平铺循环方式
+ bounding-box: 背景图像在整个内联元素中进行平铺。
+ each-box: 背景图像在行内中进行平铺
+ continuous: 下一行对背景图像紧接着上一行中对图像继续平铺
### css3多背景语法及参数
```
background: [background-image] | [background-position] [/background-size] | [background-repeat] | [background-attachment] | [background-clip] | [background-origin], *
```
### 文本属性
#### font符合属性
```
font: font-style font-weight/line-height font-family;
```
+ font-style: 字体样式
+ font-weight: 字体粗细
+ font-family: 字体类型
#### text-shadow属性
```
text-shadow: none | <length> none |[shadow,]*<shadow> 或 none | <color> [,<color>]*
text-shadow: [颜色 color] x轴位移（x-offset） y轴位移（y-offset）模糊半径（blur-radius）
```
#### text-overflow 溢出文本属性
```
text-overflow:clip | ellipsis
```
+ clip: 不显示省略标记，只是简单的裁切。
+ ellipsis: 文本溢出是显示省略标记。
+ 要实裁剪效果，还需要强制文本在一行显示（white-space:nowrap）和溢出内容隐藏（overflow:hidden）,并且需要定义容器的宽度。
    - width: 明确给需要截取文本的容器设置宽度
    - white-space:nowrap: 给文本容器设置强制不换行，让元素文本一行内显示
    - overflow:hidden: 设置容器文本溢出时隐藏
#### css3文本换行
#### word-wrap属性实现长单词与URL地址的自动换行
```
word-wrap: normal | break-word
```
+ normal: 默认值，浏览器只在半角空格或连字符的地方进行换行
+ break-word: 将内容在边界内换行（不截断英文单词换行）
+ word-wrap应用在pre和table中时，是没有任何效果的
#### word-break属性来决定自动换行的处理方法
```
word-break: normal | break-all | keep-all
```
+ normal: 默认值，根据语言自己的规则确定换行方式
+ break-all: 可以强行截断英文单词，达到词内换行效果。
+ keep-all: 不允许字断开（只有IE浏览器有效果）。对于中文来说，只能在半截空格或连字符或任何标点符号的地方换行，中文与中文之间不能换行。
#### white-space属性主要用来声明建立布局过程中如何处理元素中的空白符
```
white-spage: normal || pre || nowrap || pre-line || pre-wrap || inherit
```
+ normal: 默认值。空白处会被浏览器忽略。
+ pre: 文本空白处会被浏览器扣留
+ nowrap: 文本不会换行，文本会在同一行上
+ pre-line: 合并空白符序列，但保留换行符
+ pre-wrap: 保留空白符序列，但是正常进行换行
+ inherit: 继承父元素但white-space属性值，此属性值在所有的IE浏览器都不支持
### CSS3 颜色
#### opacity属性能够使任何元素呈现半透明效果
```
opacity: alphavalue || inherit
```
+ alphavalue: 默认值为1。透明度0～1之间，1完全不透明
+ inherit: 继承父元素opacity设置的值
### CSS3盒子模型
#### 盒子模型：inline、inline-block、block、table、absolute position、float。
#### box-sizing 能够事先定义盒子模型的尺寸解析方式
```
box-sizing: content-box | border-box | inherit
```
+ content-box: 默认值，让元素维持W3C的标准盒模型
+ border-box: 重新定义CSS2.1中盒子模型组成模式，让元素维持IE传统的盒子模型。
+ inherit: 此值使元素继承父元素的盒模型模式
+ 只有Mozilla Gecko引擎的浏览器需要添加其私有属性
#### css3内容溢出属性
#### overflow-x和overflow-y,水平和垂直方向内容溢出的剪切
```
overflow-x: visible | hidden | scroll | auto | no-display | no-content
overflow-y: visible | hidden | scroll | auto | no-display | no-content
```
+ visible: 默认值，表示不剪切容器中的任何内容、不添加滚动条
+ auto: 在需要时剪切内容并添加滚动条
+ hindden: 内容溢出容器时，所有内容都将隐藏，而且不显示滚动条
+ scroll: 不管内容有咩用溢出容器，都会显示滚动条
+ no-display: 当内容溢出容器时不显示元素，此时类似于元素添加了display: none声明一样
+ no-content: 当内容溢出容器时不显示内容，此时类似于添加了visibility:hidden声明一样
#### css3自由缩放属性
#### resize属性主要是用来改变元素尺寸大小
```
resize: none | both | horizontal | vertical | inherit
```
+ none: 用户不能拖动元素修改尺寸大小
+ both: 用户可以拖拽元素，同时修改元素的宽度和高度
+ horizontal: 用户可以拖动元素，仅可以修改元素的宽度，但不能修改元素的高度
+ vertical: 用户可以拖动元素，仅可以修改元素的高度，但不能修改元素的高度
+ inherit: 继承父元素的resize属性值
#### css3外轮廓属性
#### outline，主要是用来在元素周围绘制一条轮廓线，可以起到突出元素的作用。
```
outline: [outline-color] || [outline-style] || [outline-width] || [outline-offset] || inherit
```
+ outline-color: 轮廓线的颜色
+ outline-style: 轮廓线的样式
+ outline-width: 轮廓线的宽度
+ outline-offset: 轮廓边框的偏移位置
+ inherit: 元素继承父元素的效果
