### capitalizeEveryWord

文字列内の単語ごとの先頭文字を大文字に変換します。

各単語の先頭文字を`String.prototype.replace()`でマッチさせ、`String.prototype.toUpperCase()`で大文字に変換します。

```js
const capitalizeEveryWord = str => str.replace(/\b[a-z]/g, char => char.toUpperCase());
```

```js
capitalizeEveryWord('hello world!'); // 'Hello World!'
```
