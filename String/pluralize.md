### pluralize

入力された数値によって、基準となる文字列を単数系、あるいは複数形にして返します。第1引数にオブジェクトが指定された場合、関数によって返却されるクロージャを返します。これは"s"による単純な複数形の変換だけでなく、指定されたディクショナリに含まれる複数形単語を返却します。

numが-1か1の場合、単数系の単語を返却します。numがそれ以外の値の場合、複数形の単語を返却します。第3引数のpluralが省略された場合、デフォルトで第2引数のwordに"s"を連結した文字列を複数形の単語として処理するので、必要に応じてカスタマイズすることができます。第1引数のvalがオブジェクトの場合、複数形の単語を格納したディクショナリを保持したクロージャを返却します。

```js
const pluralize = (val, word, plural = word + 's') => {
  const _pluralize = (num, word, plural = word + 's') =>
    [1, -1].includes(Number(num)) ? word : plural;
  if (typeof val === 'object') return (num, word) => _pluralize(num, word, val[word]);
  return _pluralize(val, word, plural);
};
```

```js
pluralize(0, 'apple'); // 'apples'
pluralize(1, 'apple'); // 'apple'
pluralize(2, 'apple'); // 'apples'
pluralize(2, 'person', 'people'); // 'people'

const PLURALS = {
  person: 'people',
  radius: 'radii'
};
const autoPluralize = pluralize(PLURALS);
autoPluralize(2, 'person'); // 'people'
```
