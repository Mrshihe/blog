#### LHS查询 / RHS查询
- LHS查询试图找到变量的容器本身，从而可以对其赋值
- RHS可以理解为取到某某的源值
```
console.log( a )
a为RHS查询, 需要查找并获取a的值,将值传递给console.log

a = 2
a为LHS查询, 当前只需要为=2这个赋值操作找到一个目标
```
```
function foo(a) {
  // 隐式变量分配 a = 2 <LHS>
  var b<LHS> = a<RHS>;
  return a<RHS> + b<RHS>
}
var c<LHS> = foo(2)<RHS>
```
LHS(赋值操作的目标是谁) RHS(谁是赋值操作的源头/目标的值是多少)
ReferenceError 通常表示在作用域内未找到该变量, TypeError 通常表示对结果的操作不合法

#### this绑定
this指向在调用时产生,且由最后一次调用决定
```
1. 由 new 调用？绑定到新创建的对象
2. 由 call 或者 apply（或者 bind）调用, 绑定到指定的对象
3. 由上下文对象调用, 绑定到那个上下文对象
4. 默认：在严格模式下绑定到 undefined, 否则绑定到全局对象
```
- 箭头函数this由词法作用域来决定
