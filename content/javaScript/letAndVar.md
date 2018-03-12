## let 与 var
----

```
for(let i = 0; i < 3; i++) {
  setTimeout(function() {
    console.log(i);
  }, 1000);
}
// 0
// 1
// 2
```
* 上面代码中，变量i是let声明的，当前的i只在本轮循环有效，所以每一次循环的i其实都是一个新的变量。

```
for(var i = 0; i < 3; i++) {
    setTimeout(function() {
      console.log(i);
    }, 1000);
}
// 3
// 3
// 3
```

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


