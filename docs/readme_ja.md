<p align="center">
 <img width="100px" src="https://res.cloudinary.com/anuraghazra/image/upload/v1594908242/logo_ccswme.svg" align="center" alt="GitHub Readme Stats" />
 <h2 align="center">GitHub Readme Stats</h2>
 <p align="center">あなたの README に自動生成された GitHub の統計情報を載せましょう！</p>
</p>
  <p align="center">
    <a href="https://github.com/anuraghazra/github-readme-stats/actions">
      <img alt="Tests Passing" src="https://github.com/anuraghazra/github-readme-stats/workflows/Test/badge.svg" />
    </a>
    <a href="https://codecov.io/gh/anuraghazra/github-readme-stats">
      <img src="https://codecov.io/gh/anuraghazra/github-readme-stats/branch/master/graph/badge.svg" />
    </a>
    <a href="https://github.com/anuraghazra/github-readme-stats/issues">
      <img alt="Issues" src="https://img.shields.io/github/issues/anuraghazra/github-readme-stats?color=0088ff" />
    </a>
    <a href="https://github.com/anuraghazra/github-readme-stats/pulls">
      <img alt="GitHub pull requests" src="https://img.shields.io/github/issues-pr/anuraghazra/github-readme-stats?color=0088ff" />
    </a>
    <br />
  </p>

  <p align="center">
    <a href="#demo">View Demo</a>
    ·
    <a href="https://github.com/anuraghazra/github-readme-stats/issues/new/choose">Report Bug</a>
    ·
    <a href="https://github.com/anuraghazra/github-readme-stats/issues/new/choose">Request Feature</a>
  </p>
</p>

# 主な機能

- [GitHub Stats Card](#github-stats-card)
- [GitHub Extra Pins](#github-extra-pins)
- [Top Languages Card](#top-languages-card)
- [Themes](#テーマの変更)
- [Customization](#テーマを自分でカスタマイズする)
- [Deploy Yourself](#自分の-Vercel-インスタンスにデプロイする)

# GitHub Stats Card

以下のコードをコピーして、あなたの Markdown ファイルに貼り付けるだけです。
簡単ですね！

`?username=` の値は、あなたの GitHub アカウントのユーザー名に変更してください。

```md
[![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=anuraghazra)](https://github.com/anuraghazra/github-readme-stats)
```

_Note: カードに表示されるランクはユーザの統計情報に基づいて計算されています。詳しくは、[src/calculateRank.js](../src/calculateRank.js)をご覧ください。_

### 特定の統計情報を隠す

クエリパラメータ `?hide=` に値をカンマ区切りで渡すことで、特定の統計情報を隠すことができます。

> Options: `&hide=stars,commits,prs,issues,contribs`

```md
![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=anuraghazra&hide=contribs,prs)
```

### プライベートリポジトリへのコミットをカウントする

クエリパラメータ `?count_private=true` を使用することで、プライベートリポジトリへのコミット数を総数に追加することができます。

_Note: このプロジェクトを自分でデプロイしている場合、デフォルトではプライベートリポジトリへのコミットがカウントされます。_

> Options: `&count_private=true`

```md
![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=anuraghazra&count_private=true)
```

### アイコンを表示する

クエリパラメータ `?show_icons=true` を使用することで、アイコンの表示が有効になります。

```md
![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=anuraghazra&show_icons=true)
```

### テーマの変更

内蔵されているテーマを使用すれば、[手動のカスタマイズ](#customization)を行うことなくカードの外観を変更することができます。

`?theme=THEME_NAME` は以下のように使います。

```md
![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=anuraghazra&show_icons=true&theme=radical)
```

#### 内蔵テーマの一覧

dark, radical, merko, gruvbox, tokyonight, onedark, cobalt, synthwave, highcontrast, dracula

<img src="https://res.cloudinary.com/anuraghazra/image/upload/v1595174536/grs-themes_l4ynja.png" alt="GitHub Readme Stat Themes" width="600px"/>

その他の使用可能なテーマの[プレビュー](../themes/README.md)や[設定ファイル](../themes/index.js)もご覧ください。もしよろしければ、**新しいテーマを投稿してみてください** :smile:

### テーマを自分でカスタマイズする

`Stats Card` や `Repo Card` の外観を URL パラメータを使って好きなようにカスタマイズすることができます。

#### 共通のオプション

- `title_color` - タイトルの色 _(16 進数カラーコード)_
- `text_color` - 中身のテキストの色 _(16 進数カラーコード)_
- `icon_color` - アイコンの色（変更可能な場合のみ） _(16 進数カラーコード)_
- `bg_color` - 背景の色 _(16 進数カラーコード)_ **または** _angle,start,end_ の形式でグラデーションを指定することも可
- `hide_border` - カードの境界線を非表示にします _(ブール値)_
- `theme` - [使用可能なテーマ一覧](../themes/README.md) から選んだテーマ名
- `cache_seconds` - キャッシュ時間の秒数 _(最小値: 1800, 最大値: 86400)_
- `locale` - カードに言語を設定する _(例えば cn, de, es, 等)_

##### bg_color の グラデーション指定

bg_color オプションで複数のカンマ区切りの値を指定してグラデーションをレンダリングすることができます。フォーマットは以下の通りになります。

```
&bg_color=DEG,COLOR1,COLOR2,COLOR3...COLOR10
```

> キャッシュに関する注意点: Repo cards のデフォルトのキャッシュは、フォーク数とスター数が 1k 未満の場合は 30 分(1800 秒) で、それ以外の場合は 2 時間(7200) です。また、キャッシュは最低でも 30 分、最大でも 24 時間に制限されていることに注意してください。

#### Stats Card だけに存在するオプション

- `hide` - 特定の統計情報を隠す _(カンマ区切りで指定)_
- `hide_title` - _(boolean)_
- `hide_rank` - _(boolean)_
- `show_icons` - _(boolean)_
- `include_all_commits` - 今年度のコミット数だけでなく、コミット数の総数をカウントする _(boolean)_
- `count_private` - プライベートリポジトリへのコミットをカウントする _(boolean)_
- `line_height` - テキストの行の高さ _(number)_
- `custom_title` - タイトル文字列を変更する
- `disable_animations` - カードのアニメーションを無効にする _(boolean)_

#### Repo Card だけに存在するオプション

- `show_owner` - リポジトリのオーナーを表示する _(boolean)_

#### Language Card だけに存在するオプション

- `hide` - 特定の言語を隠す _(カンマ区切りで指定)_
- `hide_title` - _(boolean)_
- `layout` - `default` か `compact` のいずれかのレイアウトに切り替える
- `card_width` - カードの横幅 _(number)_
- `langs_count` - 表示される言語の数　_(1 ~ 10, 初期値 5)_
- `exclude_repo` - 指定されたリポジトリを除外する _(カンマ区切りで指定)_
- `custom_title` - タイトル文字列を変更する

> :warning: **重要:**
> [Percent Encoding](https://en.wikipedia.org/wiki/Percent-encoding) で指定されているように、プログラミング言語の名前は URL エンコードされている必要があります。
> (例: `c++` は `c%2B%2B`, `jupyter notebook` は `jupyter%20notebook`, など)

---

# GitHub Extra Pins

GitHub extra pins を使うと、GitHub の readme プロフィールを使って、自分のプロフィールに 6 つ以上のリポジトリをピン留めすることができます。

やったー! もはや、リポジトリをピン留めできる数が 6 つに制限されることはありません。

### 使い方

以下のコードをあなたの readme にコピー & ペーストし、リンクを変更してください。

エンドポイント: `api/pin?username=anuraghazra&repo=github-readme-stats`

```md
[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=anuraghazra&repo=github-readme-stats)](https://github.com/anuraghazra/github-readme-stats)
```

### デモ

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=anuraghazra&repo=github-readme-stats)](https://github.com/anuraghazra/github-readme-stats)

リポジトリのオーナーのユーザー名を含める場合は、show_owner 変数を使用します。

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=anuraghazra&repo=github-readme-stats&show_owner=true)](https://github.com/anuraghazra/github-readme-stats)

# Top Languages Card

Top languages card には、その GitHub ユーザーが最も利用している Top languages が表示されます。

_NOTE: Top languages は、ユーザのスキルレベルを示すものではなく、GitHub 上でどの言語で最も多くのコードを書いているかを示す GitHub の指標です。_

### 使い方

以下のコードをあなたの readme にコピー & ペーストし、リンクを変更してください。

エンドポイント: `api/top-langs?username=anuraghazra`

```md
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=anuraghazra)](https://github.com/anuraghazra/github-readme-stats)
```

### 特定の言語を隠す

クエリパラメータ `?hide=language1,language2` 使用することで、特定の言語を非表示にすることができます。

```md
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=anuraghazra&hide=javascript,html)](https://github.com/anuraghazra/github-readme-stats)
```

### レイアウトをコンパクトにする

クエリパラメータ `&layout=compact` を使用することで、カードのデザインを変更することができます。

```md
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=anuraghazra&layout=compact)](https://github.com/anuraghazra/github-readme-stats)
```

### デモ

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=anuraghazra)](https://github.com/anuraghazra/github-readme-stats)

- Compact layout の場合

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=anuraghazra&layout=compact)](https://github.com/anuraghazra/github-readme-stats)

---

### 全てのデモ

- デフォルト

![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=anuraghazra)

- 特定の統計情報を隠す

![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=anuraghazra&hide=contribs,issues)

- アイコンを表示する

![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=anuraghazra&hide=issues&show_icons=true)

- コミット数の総数をカウントする

![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=anuraghazra&include_all_commits=true)

- テーマの変更

任意の[テーマ](#themes)を選択できます。

![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=anuraghazra&show_icons=true&theme=radical)

- グラデーション

![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=anuraghazra&bg_color=30,e96443,904e95&title_color=fff&text_color=fff)

- stats card のカスタマイズ

![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api/?username=anuraghazra&show_icons=true&title_color=fff&icon_color=79ff97&text_color=9f9f9f&bg_color=151515)

- repo card のカスタマイズ

![Customized Card](https://github-readme-stats.vercel.app/api/pin?username=anuraghazra&repo=github-readme-stats&title_color=fff&icon_color=f9f9f9&text_color=9f9f9f&bg_color=151515)

- Top languages

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=anuraghazra)](https://github.com/anuraghazra/github-readme-stats)

---

### クイックヒント (カードを並べる)

通常、画像を並べてレイアウトすることはできません。画像を並べるには、以下のような方法があります。

```md
<a href="https://github.com/anuraghazra/github-readme-stats">
  <img align="center" src="https://github-readme-stats.vercel.app/api/pin/?username=anuraghazra&repo=github-readme-stats" />
</a>
<a href="https://github.com/anuraghazra/convoychat">
  <img align="center" src="https://github-readme-stats.vercel.app/api/pin/?username=anuraghazra&repo=convoychat" />
</a>
```
