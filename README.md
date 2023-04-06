# GitHub Actions Learn

GitHub Actions を色々試す場所

## [createIssue_everyMonth](.github/workflows/createIssue_everyMonth.yml)

月初に `ISSUE_LABEL_FOR_GIHUB_ISSUE` で指定したラベルを持つ Issue を作る。
次の checkIssueStatus と組み合わせることで定期的なタスクの実施を促す感じ。

## [checkIssueStatus](.github/workflows/checkIssueStatus.yml)

毎日 Issue の状態を確認し、`ISSUE_LABEL_FOR_GIHUB_ISSUE` で指定したラベルを持つ Issue があったら Discord に通知する。
Discord への通知部分は [scripts/notifyToDiscord.sh](scripts/notifyToDiscord.sh) にやらせている。

## [pre-merge-build](.github/workflows/pre-merge-build.yml)

Pull Request を出すと `mvn test` を実施してくれるだけ。

## [release](.github/workflows/release.yml)

命名規則に従ったタグを打つと配布用の jar を生成し、それを乗せた release を作成してくれる。
