# snippers

## curry
a complicated curry js example

```
function foo(p1,p2) { 
  this.val = p1 + p2;
}
// 之所以使用 null 是因为在本例中我们并不关心硬绑定的 this 是什么 // 反正使用 new 时 this 会被修改
var bar = foo.bind( null, "p1" );
var baz = new bar( "p2" ); baz.val; // p1p2
```

```
function foo(a,b) {
  console.log( "a:" + a + ", b:" + b );
}
// 把数组“展开”成参数
foo.apply( null, [2, 3] ); // a:2, b:3
// 使用 bind(..) 进行柯里化
var bar = foo.bind( null, 2 ); bar( 3 ); // a:2, b:3
```


注意`bind`使用时可以传不止一个参数

今天知道`bind`后返回的`function`是没有`prototype`的，但是不影响`new`调用后的结果，`new`后返回的实例的`__proto`扔指向`bind`前那个`function`的`prototype`

> 摘自你不知道的JavaScript上卷


## arrow functions don’t create a closure
```
function puzzle() {
  return function () {
    console.log(arguments)
  }
}
puzzle('a', 'b', 'c')(1, 2, 3)
```

```
function puzzle() {
  return () => console.log(arguments)
}
puzzle('a', 'b', 'c')(1, 2, 3)
```

## arrow function's curly brac
```
[1, 2, 3].map(value => { number: value })
```
```
[1, 2, 3].map(value => ({ number: value }))
```

