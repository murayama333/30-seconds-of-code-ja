### CSVToArray

CSV文字列を2次元配列に置き換えます。

第3引数の`omitFirstRow`が`true`の場合`Array.prototype.slice()`と`Array.prototype.indexOf('\n')`を使って先頭行を削除します。それから`String.prototype.split('\n')`を使って個々の行を配列に変換します。第2引数の`delimiter`が省略された場合はデフォルトの区切り文字として`,`を使います。また第3引数が省略された場合はCSV文字列の先頭行（タイトル行）を処理対象として含みます。

```js
const CSVToArray = (data, delimiter = ',', omitFirstRow = false) =>
  data
    .slice(omitFirstRow ? data.indexOf('\n') + 1 : 0)
    .split('\n')
    .map(v => v.split(delimiter));
```

```js
CSVToArray('a,b\nc,d'); // [['a','b'],['c','d']];
CSVToArray('a;b\nc;d', ';'); // [['a','b'],['c','d']];
CSVToArray('col1,col2\na,b\nc,d', ',', true); // [['a','b'],['c','d']];
```
