### mapString

文字列に含まれる個々の文字に対して、指定されたコールバック関数を適用して、新たな文字列を生成します。

`String.prototype.split('')`と`Array.prototype.map()`を使って、コールバック関数（引数のfn）を文字列内の個々の文字に対して適用します。それから`Array.prototype.join('')`を使って文字配列を文字列として再結合します。コールバック関数は3つの引数（現在の文字、現在の文字のインデックス、mapString関数の引数に指定された文字列）を受け取ります。

```js
const mapString = (str, fn) =>
  str
    .split('')
    .map((c, i) => fn(c, i, str))
    .join('');
```

```js
mapString('lorem ipsum', c => c.toUpperCase()); // 'LOREM IPSUM'
```
