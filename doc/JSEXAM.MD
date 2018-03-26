1. 快速数组去重。

```javascript
[...new Set([7,21,23,7,9,7,9])]
```
2. 创建一个长度为n，每个值都是m的数组。
```javacript
new Array(n).fill(m)
```
3. JS中使用type of 能得到哪些类型?

```javascript
undefined, string, number, boolean, object, function
```

4. 如何判断一个变量强制转换后是true还是false

```  javascript
var a = 1;
!!a 
```

5. 何时使用== ,合适使用 ===

> 我只在判断 `a === null || a === undefined` 时使用 `a == null` ,其余全部使用`===` 

6. 写一个原型链继承的例子

```javascript
function Elem(id) {
  this.elem = document.getElementById(id)
}

Elem.prototype.html = function (val) {
  var elem = this.elem
  if (val) {
    elem.innerHTML = val
    return this
  } else {
    return elem.innerHTML
  }
}

Elem.prototype.on = function(type, fn) {
  var elem = this.elem
  elem.addEventListenr(type, fn)
}
```

7. 快速数组合并

```javascript
[...arr1, ...arr2]
```

8. 快速数组拷贝

```javascript
let copy = [...arr]
```

9. 筛选出数组中的个别元素

```javascript
const posts = [
  {id: 1, title: 'Title 1'},
  {id: 2, title: 'Title 2'},
]
const title = posts.find(p => p.id === 1).title
```

10. 将对象转换为query字符串

```javascript
const params = {color: 'red', minPrice: 8000, maxPrice: 10000};
const query = '?' + Object.keys(params)
  .map(k =>
    encodeURIComponent(k) + '=' + encodeURIComponent(params[k])
  ).join('&')
```

11.一个简单的模板字符串替换

```javascript
String.prototype.render = function (context) {
  return this.replace(/{{(.*?)}}/g, (match, key) => context[key.trim()])
}
```

12.字符串a是否包含b

```javascript
~a.indexOf(b)
a.includes(b)
```

13.对象深拷贝

```javascript
function deepCopy(obj){
	let newObj = obj.constructor === Array ? []: {}   //判断是深拷贝对象还是数组
    
    for(let i in obj){
        if(typeof obj[i] === 'object') {
            newObj[i] = deepCopy(obj[i])    //  如果要拷贝的对象的属性依然是个复合类型，递归
        } else {
            newObj[i] = obj[i]
        }
    }
    
    return newObj
}

```

14 .闭包的例子

```javascript
for (var i = 0; i < 10; i ++) {
    setTimeout(
        (function() {
        	console.log(i)
    	})()
    )
}
```

15.什么是严格模式，有什么区别。

```javascript
1. 消除Javascript语法的一些不合理、不严谨之处，减少一些怪异行为;
2. 消除代码运行的一些不安全之处，保证代码运行的安全；
3. 提高编译器效率，增加运行速度；
4. 为未来新版本的Javascript做好铺垫。

a. 全局变量显式声明
b. 静态绑定: 不能使用with, 创设eval作用域
c. 增强的安全措施: 禁止this关键字指向全局对象, 禁止在函数内部遍历调用栈
d. 禁止删除变量, 只有configurable设置为true的对象属性，才能被删除
e. 显式报错
f. 重名错误
g. 禁止八进制表示法
h. arguments对象的限制: 不允许对arguments赋值,不再追踪参数的变化,禁止使用arguments.callee
i. 函数必须声明在顶层
j. 保留字 implements, interface, let, package, private, protected, public, static, yield
```

16. 实现 `add(2)(5) // 7` 函数

```javascript
const add = (a) => (b) => a + b
```
17.