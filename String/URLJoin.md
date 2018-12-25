### URLJoin

URLのブロックを結合して、妥当なURLに置き換えます。

`String.prototype.join('/')`を使ってURLのブロックを結合し、一連の`String.prototype.replace()`と様々な正規表現使って妥当なURL（ダブルスラッシュの排除、プロトコルの適切なスラッシュの追加、パラメータの前のスラッシュの削除、2つ目以降のパラメータを&による結合）に置き換えます。

```js
const URLJoin = (...args) =>
  args
    .join('/')
    .replace(/[\/]+/g, '/')
    .replace(/^(.+):\//, '$1://')
    .replace(/^file:/, 'file:/')
    .replace(/\/(\?|&|#[^!])/g, '$1')
    .replace(/\?/g, '&')
    .replace('&', '?');
```

```js
URLJoin('http://www.google.com', 'a', '/b/cd', '?foo=123', '?bar=foo'); // 'http://www.google.com/a/b/cd?foo=123&bar=foo'
```
