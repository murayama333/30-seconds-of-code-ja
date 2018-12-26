### stringPermutations

⚠️ 警告：この関数は文字数が増えると処理時間が指数関数的に増加します。8-10文字を超えると、ブラウザはすべての異なる組み合わせを試みるのでハングするでしょう。

文字列のすべての置換（並び替えた文字列）を生成します（重複を含みます）。

再帰を使います。与えられた文字列の各文字について、残りの文字すべての部分置換を生成します。`Use Array.prototype.map()`を使って文字と部分置換を連結し、`Array.prototype.reduce()`によって配列の中のすべての置換を連結します。処理が再帰しますが、文字列が2文字か1文字の場合をベースケースとしています。

```js
const stringPermutations = str => {
  if (str.length <= 2) return str.length === 2 ? [str, str[1] + str[0]] : [str];
  return str
    .split('')
    .reduce(
      (acc, letter, i) =>
        acc.concat(stringPermutations(str.slice(0, i) + str.slice(i + 1)).map(val => letter + val)),
      []
    );
};
```

```js
stringPermutations('abc'); // ['abc','acb','bac','bca','cab','cba']
```
