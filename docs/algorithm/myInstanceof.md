#### instanceof作用

判断一个实例是否是其父类或者祖先类型的实例。

#### instanceof 原理

通过原型链向上查找。instanceof 在查找的过程中会遍历左边变量的原型链，直到找到有原型等于右边变量的prototype，否则查找失败，返回false。

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