#### call()

> call()方法使用一个指定的this值和单独给出的一个或多个参数来调用一个函数  --MDN

#### call()语法

```js
function.call(thisArg, arg1, arg2, ...)
```

#### 模拟实现call

```js
Function.prototype.myCall = function(context, ...args) {
  if (!(this instanceof Function)) {
    throw Error(`typeError: ${this} not function.`);
  }
  const ctx = context || window;

  const func = Symbol();
  ctx[func] = this;

  const result = args.length ? ctx[func](...args) : ctx[func]();

  delete ctx[func];

  return result;
}

const test = params => console.log(params);

console.log(test.myCall(null, 'er')); // 'er'

const person = {
  name: 'xiaohua',
  showName() {
    console.log(this.name);
  }
}

const xiaoLi = {
  name: 'xiaoLi',
}

person.showName.myCall(xiaoLi); //'xiaoLi'
```