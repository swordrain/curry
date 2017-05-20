# curry
a complicated curry js example


```
function foo(p1,p2) { 
  this.val = p1 + p2;
}
// 之所以使用 null 是因为在本例中我们并不关心硬绑定的 this 是什么 // 反正使用 new 时 this 会被修改
var bar = foo.bind( null, "p1" );
var baz = new bar( "p2" ); baz.val; // p1p2
```

> 摘自你不知道的JavaScript上卷
