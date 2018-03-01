# BFC
----
### 概念：
*  BFC：全称 Block Formatting Context，块级格式化上下文，它就是一个环境。

### BFC的生成：
1. 浮动元素、
2. 绝对定位元素，
3. 块级元素以及块级容器(比如inline-block、table-cell、table-capation)
4. overflow值不为visible的块级盒子
5. 根元素

### 执行规则：
1. 在一个块级排版上下文中，盒子是从包含块顶部开始，垂直的一个接一个的排列的。每个盒子的左外边是触碰到包含块的左边的（对于从右向左的排版，则相反）。
2. 相邻两个盒子之间的垂直的间距是被margin属性所决定的，在一个块级排版上下文中相邻的两个块级盒之间的垂直margin是折叠的。
3. BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素。

