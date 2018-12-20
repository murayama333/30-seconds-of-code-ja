### CSVToJSON

CSV文字列をオブジェクトの2次元配列に置き換えます。文字列の1行目はタイトル行として処理します。

`Array.prototype.slice()`、`Array.prototype.indexOf('\n')`、`String.prototype.split(delimiter)`を使って1行目（タイトル行）を取得します。それから`String.prototype.split('\n')`を使って行ごとの文字列配列を作り、`Array.prototype.map()`と`String.prototype.split(delimiter)`を使って、個々の行の中の値を取り出します。`Array.prototype.reduce()`を使って個々の行の値を格納したオブジェクトを作ります。これらのオブジェクトはタイトル行をパースした際のキーを持ちます。第2引数を省略した場合は、デフォルトの区切り文字として`,` を使います。

```js
const CSVToJSON = (data, delimiter = ',') => {
  const titles = data.slice(0, data.indexOf('\n')).split(delimiter);
  return data
    .slice(data.indexOf('\n') + 1)
    .split('\n')
    .map(v => {
      const values = v.split(delimiter);
      return titles.reduce((obj, title, index) => ((obj[title] = values[index]), obj), {});
    });
};
```

```js
CSVToJSON('col1,col2\na,b\nc,d'); // [{'col1': 'a', 'col2': 'b'}, {'col1': 'c', 'col2': 'd'}];
CSVToJSON('col1;col2\na;b\nc;d', ';'); // [{'col1': 'a', 'col2': 'b'}, {'col1': 'c', 'col2': 'd'}];
```
