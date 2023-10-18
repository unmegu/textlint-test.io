# 自動で記事をチェックするGitHub Actions
## 実現したかったこと
 Pagesに投稿された技術記事に対して，日本語の間違いなどを自動で指摘する

## 実装方法
　Textlintというツールを使って，実装する．
[Textlintのチェックのルールは，GitHub - textlint-ja/textlint-rule-preset-ja-technical-writing: 技術文書向けのtextlintルールプリセット ](https://dev.classmethod.jp/articles/markdown-writing-with-textlint-ci/)
を使用して適宜微調整をする． 今回のチェックの設定は後半に記述する．
前提
リポジトリがすでに存在している
注意
今回はbotから送信されるべきコメントが，海野の個人アカウントから送信される．
理由：GITHUB_TOKENというSecretがデフォルトであるものなのに，自分のtokenが登録してあるSecretを使ってしまっているため．
方法
参考
[1] https://dev.classmethod.jp/articles/markdown-writing-with-textlint-ci/
[2] https://blog.beachside.dev/entry/2023/07/18/183000
[3] https://zenn.dev/yuma_prog/articles/actions_trigger-by-githubtoken
[4] https://docs.github.com/ja/enterprise-cloud@latest/apps/creating-github-apps/authenticating-with-a-github-app/making-authenticated-api-requests-with-a-github-app-in-a-github-actions-workflow
[5] https://qiita.com/developer-kikikaikai/items/60b209c065f076dca7a1


