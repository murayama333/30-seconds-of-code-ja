### truncateString

指定したサイズで文字列を切り詰めます。

文字列のサイズの上限を指定します。切り詰められた文字列の後部に'...'を連結して返します。

```js
const truncateString = (str, num) =>
  str.length > num ? str.slice(0, num > 3 ? num - 3 : num) + '...' : str;
```

```js
truncateString('boomerang', 7); // 'boom...'
```
