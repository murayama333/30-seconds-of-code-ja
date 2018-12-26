### isLowerCase

文字列が小文字か検証します。

`String.prototype.toLowerCase()`を使って、与えられた文字列を小文字に変換し、元の文字列と等しいか比較します。

```js
const isLowerCase = str => str === str.toLowerCase();
```

```js
isLowerCase('abc'); // true
isLowerCase('a3@$'); // true
isLowerCase('Ab4'); // false
```
