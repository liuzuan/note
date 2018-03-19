# <font color=#0099ff size=5 face="黑体">ie兼容问题</font>
### 一、 JS相关

 1. IE7及以下不支持对字符串用下标检索
 
  例如：
    ```
    var s='abc';
    console.log(s[0]);//在IE7及以下浏览器下结果是undefined
    解决办法是用charAt进行检索
    console.log(s.chatAt(0));//结果是a
    ```

 2. 事件绑定

    IE8及以下不支持addEventListener进行事件绑定，而是用attachEvent进行事件绑定。
    但是，IE9及以上版本就开始支持addEventListener进行事件绑定了。
    既然谈到事件绑定，就说一下addEventListener和attachEvent的区别

    （1）前者 是DOM2级事件，在IE9及以上浏览器、火狐、谷歌等支持；后者只在IE8及以下浏览器中支持。

    （2）两者的参数个数及表现形式有所不同
    ```
    addEventListener('click',function(){},false);  //第三个参数如果为true表示在捕获阶段调用事件处理程序，为false则表示在冒泡阶段调用事件处理程序
    attachEvent('onclick',function(){}); //第一个参数事件名一定要加'on'
    ```
    （3）前者会在所属元素的作用域内运行，即this指向所绑定的元素；后者会在全局作用域中运行，即this指向window

    （4）两者执行的顺序不一样。当同一元素绑定多个事件处理程序时，前者会按绑定顺序从上到下按顺序执行，而后者执行顺序刚好相反。

### 二、CSS相关

1. IE6下，对block元素设置margin-left:auto;margin-right:auto;起不到居中的效果。
2. 盒子模型，IE盒子模型width包括内容的width、padding的width、border的width。但标准盒子模型width仅包括内容的width。
3. IE6不支持min-height和min-width,max-width和max-height
4. IE8及以下不支持opacity
5. IE6不支持子选择器方法

  如:
  ```
  ul>li{width:200px;height:200px; border:1px solid #ccc;}是不起作用的
  ```