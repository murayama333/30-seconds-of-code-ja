### capitalize


文字列の先頭文字を大文字に変換します。

配列の分割代入と`String.prototype.toUpperCase()`を使って先頭の文字を大文字にします。 ...restには先頭文字を除く文字の配列が格納されるので`Array.prototype.join('')`を使って再び文字列に復元しています。引数のlowerRestが指定されなかった場合は残りの文字列（先頭文字を除く）をそのまま使います。lowerRestにtrueが指定された場合は残りの文字列を小文字に置き換えます。

```js
const capitalize = ([first, ...rest], lowerRest = false) =>
  first.toUpperCase() + (lowerRest ? rest.join('').toLowerCase() : rest.join(''));
```

```js
capitalize('fooBar'); // 'FooBar'
capitalize('fooBar', true); // 'Foobar'
```
