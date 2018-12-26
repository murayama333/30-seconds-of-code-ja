### isUpperCase

文字列が大文字か検証します。

`String.prototype.toUpperCase()`を使って、与えられた文字列を大文字に変換し、元の文字列と等しいか比較します。

Convert the given string to upper case, using String.prototype.toUpperCase() and compare it to the original.

```js
const isUpperCase = str => str === str.toUpperCase();
```

```js
isUpperCase('ABC'); // true
isLowerCase('A3@$'); // true
isLowerCase('aB4'); // false
```
