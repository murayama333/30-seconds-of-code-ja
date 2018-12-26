### pad

対象の文字列が、指定された文字数を下回る場合に、文字列の両側に指定された文字を連結します。

`String.prototype.padStart()`と`String.protorype.padEnd()`を使って与えられた文字列の両側に文字を連結します。第3引数が省略された場合、半角スペースがデフォルトの文字として連結されます。

```js
const pad = (str, length, char = ' ') =>
  str.padStart((str.length + length) / 2, char).padEnd(length, char);
```

```js
pad('cat', 8); // '  cat   '
pad(String(42), 6, '0'); // '004200'
pad('foobar', 3); // 'foobar'
```
