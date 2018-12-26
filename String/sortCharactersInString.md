### sortCharactersInString

文字列内の文字をアルファベット順にソートします。

スプレッドオペレータ(...)と`Array.prototype.sort()`、`String.prototype.localeCompare()`を使って文字列内の文字をソートし、`String.prototype.join('')`を使って再結合します。

```js
const sortCharactersInString = str => [...str].sort((a, b) => a.localeCompare(b)).join('');
```

```js
sortCharactersInString('cabbage'); // 'aabbceg'
```
