---
title: findLastKey
tags: object,function,intermediate
---

Returns the last key that satisfies the provided testing function.
Otherwise `undefined` is returned.

Use `Object.keys(obj)` to get all the properties of the object, `Array.prototype.reverse()` to reverse their order and `Array.prototype.find()` to test the provided function for each key-value pair.
The callback receives three arguments - the value, the key and the object.

```js
const findLastKey = (obj, fn) =>
  Object.keys(obj)
    .reverse()
    .find(key => fn(obj[key], key, obj));
```

```js
findLastKey(
  {
    barney: { age: 36, active: true },
    fred: { age: 40, active: false },
    pebbles: { age: 1, active: true }
  },
  o => o['active']
); // 'pebbles'
```