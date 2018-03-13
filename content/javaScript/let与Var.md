## let 与 var
----
先看一段正常的for循环代码
```
var arr = [];
for(var i = 0; i < 3; i++) {
  arr[i] = i; 
}
// [0, 1, 2]
```

但是，通常情况下我们需要在循环体中实现更多功能

```
var arr = [];
for(var i = 0; i < 3; i++) {
  arr[i] = function(){
    return i; 
  }
}
alert(arr[0]()) // 3 
// 输出3并不是我们想要的
```

* ①用let而不用var

```
var arr = [];
for(let i = 0; i < 3; i++) {
  arr[i] = function(){
    return i; 
  }
}
alert(arr[0]()) // 0
// 上面代码中，变量i是let声明的，当前的i只在本轮循环有效，所以每一次循环的i其实都是一个新的变量。

```
* ②如果要使用var，可以用闭包来
```
for(var i = 0, arr = []; i < 3; i++) {
  arr.push((function(prop){
    return function() {
      console.log(prop)
    }
  })(i))
}
arr[0]() // 0
arr[1]() // 1
arr[2]() // 2
```

```
for(var i = 0, arr = []; i < 3; i++) {
  arr.push(
    function() {
      console.log(i)
    }
  )
}
arr[0]() // 3
arr[1]() // 3
arr[2]() // 3
```


