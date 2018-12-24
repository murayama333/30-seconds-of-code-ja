### indentString

文字列内の各行をインデントします。

`String.prototype.replace`と正規表現を使って、指定されたインデント幅分、各行の先頭に指定された文字を追加します。第3引数`indent`が省略された場合デフォルトのインデント文字として' '（半角スペース）を使います。

```js
const indentString = (str, count, indent = ' ') => str.replace(/^/gm, indent.repeat(count));
```

```js
indentString('Lorem\nIpsum', 2); // '  Lorem\n  Ipsum'
indentString('Lorem\nIpsum', 2, '_'); // '__Lorem\n__Ipsum'
```
