# rasbt-machine-learning-book-verification

`rasbt/machine-learning-book` を読み取り専用サブモジュールとして参照しつつ、各章の Notebook を最新の Python パッケージ環境で継続検証できる形へ移行するためのリポジトリです。

移行後の Notebook は [`src/`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src) 配下に配置し、CI では `uv run pytest --nbmake src/` を実行してヘッドレス検証します。

## 使い方

依存関係の同期:

```bash
uv sync
```

Notebook の一括検証:

```bash
uv run pytest --nbmake src/
```

特定の章だけ検証:

```bash
uv run pytest --nbmake src/ch19/ch19.ipynb
```

## 移行済み章

- [`src/ch01/ch01.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch01/ch01.ipynb)
- [`src/ch02/ch02.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch02/ch02.ipynb)
- [`src/ch03/ch03.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch03/ch03.ipynb)
- [`src/ch04/ch04.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch04/ch04.ipynb)
- [`src/ch05/ch05.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch05/ch05.ipynb)
- [`src/ch06/ch06.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch06/ch06.ipynb)
- [`src/ch07/ch07.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch07/ch07.ipynb)
- [`src/ch08/ch08.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch08/ch08.ipynb)
- [`src/ch09/ch09.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch09/ch09.ipynb)
- [`src/ch10/ch10.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch10/ch10.ipynb)
- [`src/ch11/ch11.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch11/ch11.ipynb)
- [`src/ch12/ch12.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch12/ch12.ipynb)
- [`src/ch13/ch13.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch13/ch13.ipynb)
- [`src/ch14/ch14.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch14/ch14.ipynb)
- [`src/ch15/ch15.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch15/ch15.ipynb)
- [`src/ch16/ch16.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch16/ch16.ipynb)
- [`src/ch17/ch17.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch17/ch17.ipynb)
- [`src/ch18/ch18.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch18/ch18.ipynb)
- [`src/ch19/ch19.ipynb`](/Users/kohei/Desktop/workspace-coma-pm/rasbt-machine-learning-book-verification/src/ch19/ch19.ipynb)

## 方針

- `machine-learning-book/` 配下の原本は編集しません。
- 移行先の Notebook は CI で止まらないように、GUI 依存、対話入力、巨大な外部ダウンロードを避けます。
- 原本の教育的意図は保ちつつ、古い API や重すぎる処理は最新環境向けに置き換えます。
