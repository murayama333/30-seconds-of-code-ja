### unescapeHTML

HTML特殊文字をアンエスケープします。

正規表現と
`String.prototype.replace()`と正規表現を使って、マッチした文字をアンエスケープします。このときコールバック関数を使ってディクショナリ（オブジェクト）によって管理されたアンエスケープ文字に変換します。

```js
const unescapeHTML = str =>
  str.replace(
    /&amp;|&lt;|&gt;|&#39;|&quot;/g,
    tag =>
      ({
        '&amp;': '&',
        '&lt;': '<',
        '&gt;': '>',
        '&#39;': "'",
        '&quot;': '"'
      }[tag] || tag)
  );
```

```js
unescapeHTML('&lt;a href=&quot;#&quot;&gt;Me &amp; you&lt;/a&gt;'); // '<a href="#">Me & you</a>'
```
