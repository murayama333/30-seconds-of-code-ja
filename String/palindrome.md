### palindrome

与えられた文字列が回文になっているか検証します。回文の場合、true、そうでない場合、falseを返します。

`String.prototype.toLowerCase()`と`String.prototype.replace()`を使って非アルファベット文字を除去して小文字に統一し、それからスプレッドオペレータ（...）を使って文字列を文字の配列に変換し、`Array.prototype.reverse()`、`String.prototype.join('')`を使って生成した文字列と、元の文字列（非アルファベット文字を除去して小文字に統一したもの）を比較します。

```js
const palindrome = str => {
  const s = str.toLowerCase().replace(/[\W_]/g, '');
  return s === [...s].reverse().join('');
};
```

```js
palindrome('taco cat'); // true
```
