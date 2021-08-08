#### instanceof 原理

通过原型链向上查找。

```js
function myInstanceOf(left, right) {
  if (typeof left !== 'object' || left === null) {
    return false;
  }

  let proto = Object.getPrototypeOf(left);
  // let proto = left.__proto__;

  while(true) {
    if (proto == null) {
      return false;
    }
    if (proto == right.prototype) {
      return true;
    }

    proto = Object.getPrototypeOf(proto);
  }
}

console.log(myInstanceOf('111', String)); // false
console.log(myInstanceOf(new String('111'), String)); // true
```