### capitalize


文字列の先頭文字を大文字に変換します。

配列の分割代入と`String.prototype.toUpperCase()`を使って先頭の文字を大文字にします。 ...restには先頭文字を除く文字の配列が格納されるので`Array.prototype.join('')`を使って再び文字列に復元しています。lowerRestパラメータが指定されなかった場合は残りの文字列（先頭文字を除く）をそのまま使います。lowerRestパラメータにtrueが指定された場合は残りの文字列を小文字に置き換えます。

```js
const capitalize = ([first, ...rest], lowerRest = false) =>
  first.toUpperCase() + (lowerRest ? rest.join('').toLowerCase() : rest.join(''));
```

```js
capitalize('fooBar'); // 'FooBar'
capitalize('fooBar', true); // 'Foobar'
```

### capitalizeEveryWord

文字列内の単語ごとの先頭文字を大文字に変換します。

各単語の先頭文字を`String.prototype.replace()`でマッチさせ、`String.prototype.toUpperCase()`で大文字に変換します。

Use `String.prototype.replace()` to match the first character of each word and `String.prototype.toUpperCase()` to capitalize it.

```js
const capitalizeEveryWord = str => str.replace(/\b[a-z]/g, char => char.toUpperCase());
```

```js
capitalizeEveryWord('hello world!'); // 'Hello World!'
```

### compactWhitespace

連続するホワイトスペース文字（スペース、タブ、改ページ、改行）をホワイトスペース文字1文字に置き換えます。

正規表現と`String.prototype.replace()`を使うことで、2文字以上のホワイトスペース文字を1文字に置き換えます。

```js
const compactWhitespace = str => str.replace(/\s{2,}/g, ' ');
```

```js
compactWhitespace('Lorem    Ipsum'); // 'Lorem Ipsum'
compactWhitespace('Lorem \n Ipsum'); // 'Lorem Ipsum'
```


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

### CSVToJSON
### decapitalize
### escapeHTML
### escapeRegExp
### fromCamelCase
### indentString
### isAbsoluteURL
### isAnagram
### isLowerCase
### isUpperCase
### mapString
### mask
### pad
### palindrome
### pluralize
### removeNonASCII
### reverseString
### sortCharactersInString
### splitLines
### stringPermutations
### stripHTMLTags
### toCamelCase
### toKebabCase
### toSnakeCase
### toTitleCase
### truncateString
### unescapeHTML
### URLJoin
### words
