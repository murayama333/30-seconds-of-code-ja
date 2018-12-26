### removeNonASCII

印刷できないASCII文字を除去します。

正規表現を使って印刷できないASCII文字を除去します。

```js
const removeNonASCII = str => str.replace(/[^\x20-\x7E]/g, '');
```

```js
removeNonASCII('äÄçÇéÉêlorem-ipsumöÖÐþúÚ'); // 'lorem-ipsum'
```
