- 查找两个数组之间的差异

```js
function difference(arrA, arrB) {
  const tempArr = new Set(arrB);
  return arrA.filter(item => !tempArr.has(item));
}

difference([1, 2, 3], [1, 2, 4]); // [3]
```