# コンパイル通る？ Rust編

The Book（The Rust Programming Language）の範囲から出題する、ブラウザで遊べる Rust 学習クイズです。コードを見て「コンパイルが通るか」「実行すると何が表示されるか」を当てます。

## ステージ

| ステージ | 内容 | The Book |
| --- | --- | --- |
| DAY 1 | 変数・型・関数・制御フロー | 3章 |
| DAY 2 | 所有権・借用・ベクタ | 4・8章 |
| DAY 3 | 構造体・enum・match・Option・Result | 5・6・9章 |
| ALL | 全問シャッフル | — |

## 遊び方

`index.html` をブラウザで開くだけで遊べます。ビルドや依存ライブラリは不要です。

- 正解で 100 点、連続正解ごとに +20 点のボーナス
- ライフは 3 つ。3 回間違えるとゲームオーバー
- 回答後に実際のコンパイラのエラーメッセージ（E0382 など）と直し方、対応する The Book の節が表示されます
- ステージごとのベストスコアはブラウザに保存されます

## 問題の追加

`index.html` の `Q` 配列に問題を追加します。

```js
{ day: 2, ch: "4.1 所有権（ムーブ）", type: "compile", compiles: false,
  code: `fn main() { ... }`,
  out: "error[E0382]: borrow of moved value: `s1`",
  why: "解説",
  fix: `直したコード` }
```

`type` は `"compile"`（通る／エラー）か `"output"`（選択肢から出力を選ぶ、`choices` と `answer` を指定）のどちらかです。
