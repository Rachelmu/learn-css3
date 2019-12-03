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

###border-style值
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
