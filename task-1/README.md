# Filtering private object properties by key

## Task

Write a function to filter private object properties by key with prefix "_".

```js
const obj = {
    _id: 1,
    foo: "foo",
    bar: "bar",
    baz: "baz"
}

getPublic(obj);
// Expected output:
// {
//     foo: "foo",
//     bar: "bar",
//     baz: "baz"
// }
```

## Answer

```js
function getPublic(obj) {
  return Object.keys(obj).reduce((res, key) => {
    if (!key.startsWith("_")) {
      res[key] = obj[key];
    }
    return res;
  }, {});
}
```