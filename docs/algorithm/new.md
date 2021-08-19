##### new一个对象的执行过程

1. 创建一个对象
2. 将对象的__proto__指向构造函数的prototype
3. 将这个对象作为构造函数的this
4. 返回这个对象

```js
// Con: 构造函数
function myNew(Con, ...args) {
  let obj = Object.create(Con.prototype);
  let result = Con.apply(obj, args);
  return typeof obj === 'object' ? result : obj;
}
```
    