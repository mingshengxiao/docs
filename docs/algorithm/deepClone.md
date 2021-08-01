#### 方法一: JSON.parse(JSON.stringify(obj))

**使用注意点**:

1. Boolean|Number|String 类型会自动转换成对应的原始值.
```js
  a = { b: new Number(4) };
  c = JSON.parse(JSON.stringify(a));
  console.log(c) // {b:4}
```
2. undefined、任意函数以及 symbol，会被忽略（出现在非数组对象的属性值中时），或者被转换成 null（出现在数组中时）。
```js
  a = {b: new Number(3), c: function() {console.log(3)}, d: undefined, e: Symbol('tst')};
  c = JSON.parse(JSON.stringify(a));
  console.log(c) // {b:3}
```   
3. 不可枚举的属性会被忽略
```js
  a = {b: 5};
  Object.defineProperty(a, 'f', {
    value: 'f',
    enumerable: false
  });
  c = JSON.parse(JSON.stringify(a));
  console.log(c) // {b:5}
```
4. 如果一个对象的属性值通过某种间接的方式指回该对象本身，即循环引用，属性也会被忽略。  
5. 属性值Infinity,-Infinity,NaN经过stringify转换后会变成null
```js
  a = {b: new Number(3), c: NaN, d: undefined, e: Symbol('tst'), g: Infinity};
  JSON.parse(JSON.stringify(a)) // {b: 3, c: null, g: null}
```

#### 方法二: 使用lodash的deepclone函数
#### 手写deepClone
```js
  function deepClone(obj) {
    
  }
```