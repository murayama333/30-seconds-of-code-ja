### escapeRegExp

escapeRegExp

正規表現で利用可能な文字列にエスケープします。

`String.prototype.replace()`を使って特殊文字をエスケープします。

```js
Use String.prototype.replace() to escape special characters.
```

```js
const escapeRegExp = str => str.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
escapeRegExp('(test)'); // \\(test\\)
```
