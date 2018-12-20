### escapeHTML

HTMLで利用可能な文字列（HTML特殊文字）にエスケープします。

Escapes a string for use in HTML.

`String.prototype.replace()`と正規表現を使って、マッチした文字をエスケープします。このときコールバック関数を使ってディクショナリ（オブジェクト）によって管理された特殊文字に変換します。

```js
const escapeHTML = str =>
  str.replace(
    /[&<>'"]/g,
    tag =>
      ({
        '&': '&amp;',
        '<': '&lt;',
        '>': '&gt;',
        "'": '&#39;',
        '"': '&quot;'
      }[tag] || tag)
  );
```

```js
escapeHTML('<a href="#">Me & you</a>'); // '&lt;a href=&quot;#&quot;&gt;Me &amp; you&lt;/a&gt;'
```
