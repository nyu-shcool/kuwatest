# 昆虫図鑑アプリ

みんなで1つのアプリを作る練習用リポジトリです。
1人1画面（＝1つの HTML ファイル）を担当して、最後に1つのアプリにまとめます。

## フォルダの中身

```
index.html            アプリの外枠（スマホの枠と下のタブ）。ふだんは触らない
pages/
  home.html           ホーム画面（完成済み）
  battle.html         対戦画面　 ← いまは「作成中」。担当者が書きかえる
  ar.html             AR探索画面 ← いまは「作成中」。担当者が書きかえる
  zukan.html          図鑑画面　 ← いまは「作成中」。担当者が書きかえる
  shop.html           ショップ画面 ← いまは「作成中」。担当者が書きかえる
  _template.html      新しい画面のひな形
```

## しくみ

下のタブは、ふつうの `<a>` タグです。

```html
<a href="pages/battle.html" target="screen">対戦</a>

<iframe name="screen" src="pages/home.html"></iframe>
```

- `target="screen"` と書くと、リンク先のページが `<iframe name="screen">` の中に開きます。
- だから、タブを押すと真ん中の画面だけが切り替わります。
- いまは `pages/battle.html` などに「作成中」画面が入っています。
- 担当者がこのファイルを書きかえると、タブを押したときに自分の画面が出るようになります。

## 担当する画面

| タブ | 書きかえるファイル |
| --- | --- |
| ⚔️ 対戦 | `pages/battle.html` |
| 📷 AR探索 | `pages/ar.html` |
| 📖 図鑑 | `pages/zukan.html` |
| 👜 ショップ | `pages/shop.html` |

デザインは `pages/home.html`（ホーム画面）に合わせると、アプリ全体の見た目がそろいます。

## 動かし方

`index.html` をダブルクリックして、ブラウザで開くだけです。

デザイン用の部品（Tailwind CSS とフォント）をインターネットから読み込んでいるので、インターネットにつながっている状態で開いてください。

## 画面の作り方

1. `pages/_template.html` の中身をまるごとコピーします。
2. 担当のファイル（例: `pages/battle.html`）の中身を消して、コピーしたものを貼り付けます。
3. `<body>` の中を自由に書きかえます。
4. `index.html` を開き、担当のタブを押して自分の画面が出ればOKです。

`index.html` を書きかえる必要はありません。

### ルール

- 自分の担当ファイル以外は書きかえない。
- CSS と JavaScript は自分のファイルの中に書く（他の人の画面に影響しません）。
- 他の画面に移動したいときは、ふつうの `<a>` タグで書く。同じ `pages/` フォルダの中なので、ファイル名だけでOKです。

  ```html
  <a href="zukan.html">図鑑へ</a>
  ```

## 提出の仕方

### やり方A: Pull Request（PR）で出す

1. このリポジトリを clone して、フォルダの中に入ります。

   ```bash
   git clone https://github.com/nyu-shcool/kuwatest.git
   ```

   ```bash
   cd kuwatest
   ```

2. 自分用のブランチを作ります。

   ```bash
   git switch -c add-battle-page
   ```

3. `pages/battle.html` を書きかえて、動くことを確認します。
4. コミットして push します。

   ```bash
   git add pages/battle.html
   ```

   ```bash
   git commit -m "バトル画面を追加"
   ```

   ```bash
   git push -u origin add-battle-page
   ```

5. GitHub で Pull Request を作ります。
6. レビューで OK が出たらマージされます。

1人1ファイルなので、他の人の PR とぶつかる（コンフリクトする）ことはほとんどありません。

### やり方B: 自分のリポジトリで作って、最後に合体する

1. 自分のリポジトリに `pages/_template.html` をコピーして、`battle.html` として作ります。
2. 1ファイルだけで動くように作ります（画像などを使う場合は相談してください）。
3. 完成したら、このリポジトリの `pages/battle.html` を、そのファイルで置きかえます（PR でも、ファイルを渡すのでもOK）。
