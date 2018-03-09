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

