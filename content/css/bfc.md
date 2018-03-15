# <font color=#0099ff size=5 face="黑体">BFC</font>
----
### 概念：
BFC：全称 Block Formatting Context，块级格式化上下文，它就是一个环境。

### BFC的生成
1. 浮动元素、
2. 绝对定位元素，
3. 块级元素以及块级容器(比如inline-block、table-cell、table-capation)
4. overflow值不为visible的块级盒子
5. 根元素

### BFC特性及应用
1. 同一个 BFC 下外边距会发生折叠。
  * 首先这不是 CSS 的 bug，我们可以理解为一种规范，如果想要避免外边距的重叠，可以将其放在不同的 BFC 容器中。
2. BFC 可以包含浮动的元素（清除浮动）。
  * 由于容器内元素浮动，脱离了文档流，所以容器高度塌陷。如果使触发容器的 BFC，那么容器将会包裹着浮动元素。
3. BFC 可以阻止元素被浮动元素覆盖。



