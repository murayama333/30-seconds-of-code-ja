### reverseString

文字列を反転します。
Reverses a string.

スプレッドオペレータ(...)と`Array.prototype.reverse()`を使って文字列内の文字の並びを逆順にし`String.prototype.join('')`によって文字を連結して文字列とします。


```js
const reverseString = str => [...str].reverse().join('');
```

```js
reverseString('foobar'); // 'raboof'
```
