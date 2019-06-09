## promise

promise是异步编程的一种解决方案
promise是一种容器，里面保存着未来才会结束的事件结果。
语法上来说promise是一个对象，可以获取异步操作的消息。
- promise三种状态：
    pending  进行中
    fulfilled  已成功
    reject  已失败

- promise的两个静态方法： 
    resolve   
    reject

- promise的缺点：
    外部无法控制内部的状态，只有promise的返回结果，可以控制那种状态



## let const

    js中变量作用域的基本单元一直都是function，如果需要创建一个块级作用域，最普遍的方法除了函数声明之外，就是立即调函数表达式( IIFE )
```
    var a = 2;
    (function(){
        var a = 3;
        console.log(a); //3
    })()
    console.log(a) //2
```

    es6里面，我们可以创建绑定到任意块的声明，被称为块作用域，{}就可以创建一个作用域。
```
        var a = 2;
        {
            let a = 3;
            console.log(a); //3
        }
        console.log(a) //2
```

    let 声明变量
    let 声明的变量不会提升
    同一作用域下不能出现重复变量  否则会报错

```
    let a = 10;
    let a = 5;
    console.log(a) //报错
```

    const 声明常量
    const 声明的常量不会提升
    同一作用域下不能出现重复变量  否则会报错

    let 和 const不是顶层对象的属性

- 在es5中也可以模拟es6的let
    let声明的变量不能再全局作用域里调用
    下面通过块级作用域模拟实现let
    function note(count){
        (function(){
            for (var i = 0;i < count; i++){
                console.log(i) //[0,1,2,3,4]
            }
        })()
        console.log(i) //报错
    }
    note(5)