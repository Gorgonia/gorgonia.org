---
title: "ドキュメントへの貢献を始める"
date: 2020-01-31T14:59:03+01:00
draft: false
---

Gorgonia のドキュメントへの貢献を始めたい場合は、このページとこのページからリンクされたトピックが開始に役立ちます。Gorgonia のドキュメントとユーザ体験に大きな影響を与える様な開発者であったりテクニカルライターである必要はありません。このページのトピックに必要なのは、GitHub アカウントとウェブブラウザだけです。

Gorgonia のコードリポジトリへの貢献を開始する方法についてお探しの場合、[貢献ガイドライン](https://github.com/gorgonia/gorgonia/blob/master/CONTRIBUTING.md)を参照してください。

### ドキュメントに関する基本事項

Gorgonia のドキュメントは Markdown で記述され、Hugo を使って処理および展開されます。ソースは GitHub の https://github.com/gorgonia/gorgonia.github.io にあります。ほぼ全てのドキュメントソースは `/content/` に保存されています。

issue の登録、コンテンツの編集、他のユーザーからの変更のレビュー、その他全てを GitHub のウェブサイトから行えます。GitHub 組み込みの履歴表示や検索ツールを使用することもできます。

### ドキュメントのレイアウト

ドキュメントは [What nobody tells you about documentation](https://www.divio.com/blog/documentation/) の記事で説明されているレイアウトに沿っています。

これは4つのセクションに分かれています。各セクションはリポジトリの `content/` ディレクトリのサブディレクトリです。

#### チュートリアル

チュートリアルとは:

- 学習指向であり
- 新参の方でも始められ
- レッスンであること

類似: 小さな子供に料理を教える

リポジトリ内のコンテンツのソース: [`content/tutorials`](https://github.com/gorgonia/gorgonia.github.io/tree/develop/content/tutorials)


#### ハウツーガイド

ハウツーガイドとは:

- 目標指向であり
- 特定の問題を解決する方法を示しており
- 一連の手順であること

類似: 料理本のレシピ

リポジトリ内のコンテンツのソース: [`content/how-to`](https://github.com/gorgonia/gorgonia.github.io/tree/develop/content/how-to)

#### 説明

説明とは:

- 理解志向であり
- 説明しており
- 背景とコンテキストを提供すること

類似: 料理の社会史に関する記事

リポジトリ内のコンテンツのソース: [`content/about`](https://github.com/gorgonia/gorgonia.github.io/tree/develop/content/about)

#### リファレンス

- 情報指向であり
- 機構について説明しており
- 正確で完全であること

類似: 参照百科事典の記事

リポジトリ内のコンテンツのソース: [`content/reference`](https://github.com/gorgonia/gorgonia.github.io/tree/develop/content/reference)

### 複数の言語

ドキュメントソースは /content/ の中で複数の言語で利用できます。各ページは [ISO 639-1 standard](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) で決められた2文字のコードを追加することにより、任意の言語に翻訳できます。
接尾辞のないファイルのデフォルトは英語です。

例えばフランス語のドキュメントページの名前は `page.fr.md` です。

## ドキュメントの改善

### 既存のコンテンツの修正

ドキュメントのバグやタイプミスを修正することでドキュメントを改善できます。
既存のコンテンツを改善するには _fork_ を作成した後 _pull request(PR)_ を登録します。これらの2つは[GitHub固有](https://help.github.com/categories/collaborating-with-issues-and-pull-requests/)の用語です。
このトピックではウェブブラウザを使ってすべてを遂行できるため、それらに関して全てを知る必要はありません。

### 新しいコンテンツの作成

{{% notice info %}}
リポジトリのソースは `develop` ブランチで管理されています。よってこのブランチは新しいブランチのベースである必要があり、PR もこのブランチを指している必要があります。
{{% /notice %}}
新しいコンテンツを作成するには、ドキュメントのトピックに対応するディレクトリに新しいページを作成してください([ドキュメントのレイアウト](＃layout-of-the-documentation)の段落を参照)

ローカルに `hugo` がインストールされている場合は、次のコマンドで新しいページを作成できます。

```shell
hugo new content/about/mypage.md
```

それ以外の場合は、以下の様なヘッダを付けて新しいページを作成してください:

```yaml
---
title: "The title of the page"
date: 2020-01-31T14:59:03+01:00
draft: false
---

あなたのコンテンツ
```

そして以下で説明するようにプルリクエストを送信します。

### プルリクエストの登録

次の手順に従って Gorgonia のドキュメントを改善するためのプルリクエストを登録します。

- 問題のあるページで、右上の "このページを編集" アイコンをクリックします。
    新しい GitHub ページが表示され、ヘルプテキストが表示されます。
- Gorgonia のドキュメントリポジトリのフォークを作成していない場合は、作成するように求められます。
    メンバになっているかもしれない組織ではなく、GitHub ユーザー名でフォークを作成します。
    競合する名前のリポジトリがすでにある場合を除き、フォークには通常 `https:
    //github.com/<username>/website` といった URL になります。

    フォークを作成するように求められるのは、Gorgonia のリポジトリのブランチに直
    接プッシュするアクセス権がないためです。

- GitHub Markdown エディタが表示され、ソースの Markdown ファイルが読み込まれます。
    変更を加えます。エディタの下でフォーム **ファイル変更の提案** に入力します。
    最初のフィールドはコミットメッセージの要約であり、50文字を超えてはいけません。
    2番目のフィールドはオプションですが、必要に応じて詳細を含めることができます。
    **Propose file change** をクリックします。変更は、フォークの新しいブランチ
    にコミットとして保存され `patch-1` の様な名前が自動的に付けられます。

{{% notice info %}}
他の GitHub の issue への参照を含めたりプルリクエストをコミットメッセージで参照しないで下さい。
それらは後述するプルリクエストの説明で追加できます。
{{% /notice %}}

- 次の画面は新しいブランチ(**head fork** と **compare**の 選択ボックス)と
    **base fork** と**base** ブランチ(デフォルトでは
    `gorgonia/gorgonia.github.io` リポジトリ の `develop`)の現在の状態とを比較し
    てあなたが行った変更を要約しています。いずれの選択ボックスも変更できますが、
    今は変更しないでください。 画面の下部にある差分ビューアを見て、全てが正しいと
    思ったら **Create pull request** をクリックして下さい。

{{% notice info %}}
今すぐプルリクエストを作成したくない場合でも、Gorgonia のウェブサイトリポジトリ
またはフォークのリポジトリのメインURLを参照する事で後からでも作成できます。
GitHub ウェブサイトは fork に新しいブランチを push したことを検出するとプルリク
エストを作成するように求めてきます。
{{% /notice %}}

- **Open a pull request** 画面が表示されます。プルリクエストの件名はコミットサ
    マリーと同じですが必要に応じて変更できます。本文には拡張コミットメッセージ
    (存在する場合)といくつかのテンプレートテキストが入力されます。テンプレート
    テキストを読み、必要な詳細を入力してから余分なテンプレートテキストを削除し
    ます。説明に `fixes #<000000>` または `closes #<000000>` を追加すると、
    `#<000000>` は関連する issue の番号となり、GitHub は PR がマージされると同時に
    に issue を自動的に閉じます。
    **Allow edits from maintainers** チェックボックスは選択したまま **Create
    pull request** をクリックします。

    おめでとうございます。あなたの pull request が
    [Pull requests](https://github.com/gorgonia/gorgonia.github.io/pulls) に表
    示されています。

{{% notice info %}}
プルリクエストは PR ごとに1つの言語となる様に制限してください。たとえば複数の言語で同じコードサンプルに同じ変更を加える必要がある場合は、言語ごとに個別の PR を開きます。
{{% /notice %}}

-  レビューを待つ
    レビュー担当者から変更を求められた場合は **Files changed** のタブに移動し、
    プルリクエストによって変更されたファイルの鉛筆アイコンをクリックできます。
    変更したファイルを保存するとプルリクエストによって監視されているブランチに
    新しいコミットが作成されます。レビュー担当者が変更を確認するのを待っている
    場合、7日に1回、レビュー担当者に連絡してください。
    [gopherslack](https://invite.slack.golangbridge.org/) の `#gorgonia` チャネ
    ルにアクセスすることもできます。これは PR レビューに関する助言を求めるの
    に適した場所です。

- 変更が承認されると、レビュー担当者がプルリクエストをマージし、Gorgonia のウェ
  ブサイトに数分後に変更が反映されます。

これがプルリクエストを送信する唯一の方法です。すでに Git と GitHub の上級ユーザである場合は、GitHub UI を使用する代わりにローカルの GUI やコマンドラインの Git クライアントを使用できます。
