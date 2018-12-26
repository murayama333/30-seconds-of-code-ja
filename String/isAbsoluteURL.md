### isAbsoluteURL

与えられた文字列が絶対URLの場合にtrue、そうでない場合にはfalseを返します。

正規表現を使って、与えられた文字列が絶対URLか検証します。


```js
const isAbsoluteURL = str => /^[a-z][a-z0-9+.-]*:/.test(str);
```

```js
isAbsoluteURL('https://google.com'); // true
isAbsoluteURL('ftp://www.myserver.net'); // true
isAbsoluteURL('/foo/bar'); // false
```
