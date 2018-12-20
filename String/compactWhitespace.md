### compactWhitespace

連続するホワイトスペース文字（スペース、タブ、改ページ、改行）をホワイトスペース文字1文字に置き換えます。

正規表現と`String.prototype.replace()`を使うことで、2文字以上のホワイトスペース文字を1文字に置き換えます。

```js
const compactWhitespace = str => str.replace(/\s{2,}/g, ' ');
```

```js
compactWhitespace('Lorem    Ipsum'); // 'Lorem Ipsum'
compactWhitespace('Lorem \n Ipsum'); // 'Lorem Ipsum'
```
