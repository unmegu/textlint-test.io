# 自動で記事をチェックするGitHub Actions
 Pagesに投稿された技術記事に対して，textlintを利用して日本語の間違いなどを自動で指摘することを試すライブラリです．

## 実装方法
　Textlintというツールを使って，実装する．
[Textlintのチェックのルールは，GitHub - textlint-ja/textlint-rule-preset-ja-technical-writing: 技術文書向けのtextlintルールプリセット ](https://dev.classmethod.jp/articles/markdown-writing-with-textlint-ci/)
を使用して適宜微調整をする． 

今回のチェックの設定は後半に記述する．


### 前提
- リポジトリがすでに存在している
- プルリクへコメントをするためのGitHub Appsを作成済みである（権限でできない場合あり）
    - まだ作成していなかった場合は，[こちらのサイト](https://docs.github.com/ja/enterprise-cloud@latest/apps/creating-github-apps/authenticating-with-a-github-app/making-authenticated-api-requests-with-a-github-app-in-a-github-actions-workflow)を参考に作成

### 方法
1. `.github/workflows`フォルダを作成し，その直下にGitHub Actionsを設定するYAMLファイルを作成する
2. YAMLファイル中のsecretと同名のsecretを作成し，事前に作成したGitHub AppのIDとpemをそれぞれ登録する
3. `.textrc`ファイルを作成し，ファイルの中身を適宜書き換えてルールを調整する
    ルールは基本的にtrueになっているので，必要に応じて明治的にfalseを書き足すことで調整できる．

    デフォルトのルールのセットは[技術文書向けルールプリセット](https://github.com/textlint-ja/textlint-rule-preset-ja-technical-writing)を利用している．

参考
[1] https://dev.classmethod.jp/articles/markdown-writing-with-textlint-ci/
[2] https://blog.beachside.dev/entry/2023/07/18/183000
[3] https://zenn.dev/yuma_prog/articles/actions_trigger-by-githubtoken
[4] https://docs.github.com/ja/enterprise-cloud@latest/apps/creating-github-apps/authenticating-with-a-github-app/making-authenticated-api-requests-with-a-github-app-in-a-github-actions-workflow
[5] https://qiita.com/developer-kikikaikai/items/60b209c065f076dca7a1


