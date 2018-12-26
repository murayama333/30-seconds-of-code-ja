### splitLines

複数行の文字列を行の配列に分割します。

Splits a multiline string into an array of lines.

`String.prototype.split()`と正規表現を使って行を検出し、配列を生成します。

```js
const splitLines = str => str.split(/\r?\n/);
```

```js
splitLines('This\nis a\nmultiline\nstring.\n'); // ['This', 'is a', 'multiline', 'string.' , '']
```
