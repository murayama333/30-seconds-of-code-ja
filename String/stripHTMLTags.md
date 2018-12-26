### stripHTMLTags

文字列からHTML/XMLタグを除去します。

正規表現を使って、文字列からHTML/XMLタグを除去します。

```js
const stripHTMLTags = str => str.replace(/<[^>]*>/g, '');
```

```js
stripHTMLTags('<p><em>lorem</em> <strong>ipsum</strong></p>'); // 'lorem ipsum'
```
