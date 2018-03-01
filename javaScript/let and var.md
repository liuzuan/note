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

* 上面代码中，变量i是let声明的，当前的i只在本轮循环有效，所以每一次循环的i其实都是一个新的变量，所以最后输出的是6。