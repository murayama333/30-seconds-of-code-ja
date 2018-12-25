### words

文字列を単語の配列に変換します。

指定された正規表現パターン（デフォルトでは非アルファベット文字）と`String.prototype.split()`を使って、単語文字列の配列に変換します。また`Array.prototype.filter()`によって空の文字列を除去しています。第2引数が省略された場合はデフォルトの正規表現パターンを使います。

```js
const words = (str, pattern = /[^a-zA-Z-]+/) => str.split(pattern).filter(Boolean);
```

```js
words('I love javaScript!!'); // ["I", "love", "javaScript"]
words('python, javaScript & coffee'); // ["python", "javaScript", "coffee"]
```
