### isAnagram

文字列が他の文字列（大文字小文字は無視し、スペース、句読点、特殊文字は除去した文字列）のアナグラム（文字配列の並び替え）であるか検証します。

`String.prototype.toLowerCase()`と、適切な正規表現を適用した`String.prototype.replace()`を使って、不要な文字を除去し、
`String.prototype.split('')`、`Array.prototype.sort()`、`Array.prototype.join('')`を使ってノーマライズ（文字の並びを整理）するnormalize関数を定義します。引数の2つの文字列にnormalize関数を適用して、文字列の並びが等しいか検証します。

```js
const isAnagram = (str1, str2) => {
  const normalize = str =>
    str
      .toLowerCase()
      .replace(/[^a-z0-9]/gi, '')
      .split('')
      .sort()
      .join('');
  return normalize(str1) === normalize(str2);
};
```

```js
isAnagram('iceman', 'cinema'); // true
```
