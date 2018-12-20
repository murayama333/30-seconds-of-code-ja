### decapitalize

文字列の先頭文字を小文字に変換します。

配列の分割代入と`String.prototype.toLowerCase()`を使って先頭の文字を大文字にします。 ...restには先頭文字を除く文字の配列が格納されるので`Array.prototype.join('')`を使って再び文字列に復元しています。引数のupperRestが指定されなかった場合は残りの文字列（先頭文字を除く）をそのまま使います。upperRestにtrueが指定された場合は残りの文字列を大文字に置き換えます。

```js
const decapitalize = ([first, ...rest], upperRest = false) =>
  first.toLowerCase() + (upperRest ? rest.join('').toUpperCase() : rest.join(''));
```

```js
decapitalize('FooBar'); // 'fooBar'
decapitalize('FooBar', true); // 'fOOBAR'
```
