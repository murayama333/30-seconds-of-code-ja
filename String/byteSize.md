### byteSize

文字列の長さをbytesで返します。

文字列をBlobオブジェクトに変換してsizeプロパティを参照します。

```js
const byteSize = str => new Blob([str]).size;
```

```js
byteSize('😀'); // 4
byteSize('Hello World'); // 11
```
