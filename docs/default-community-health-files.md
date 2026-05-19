# Default Community Health Files

GitHub では、Organization 配下の public `.github` リポジトリを使って、Organization 共通の default community health files を提供できます。

`yodo-test-org` では、次のリポジトリがその役割を持ちます。

https://github.com/yodo-test-org/.github

## 現在 Organization が提供しているファイル

- `SECURITY.md`
- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`
- `SUPPORT.md`
- `PULL_REQUEST_TEMPLATE.md`
- `ISSUE_TEMPLATE/config.yml`
- `profile/README.md`

## 重要なルール

default file は、対象リポジトリに同等のファイルが存在しない場合だけ適用されます。

例:

- 対象リポジトリに `SECURITY.md` がない場合、Organization 共通の `SECURITY.md` が使われる。
- 対象リポジトリに独自の `SECURITY.md` がある場合、そのリポジトリのファイルが使われる。

## 実務上の使いどころ

Organization default は、次のような場面で役立ちます。

- 新規リポジトリに最低限の security policy を自動的に持たせたい。
- issue や pull request の案内を Organization 全体で揃えたい。
- contribution や support の期待値を共通化したい。

リポジトリ固有ファイルは、次のような場面で使います。

- プロジェクトごとに support 方針が違う。
- 脆弱性報告の窓口や手順が違う。
- contribution workflow をより厳密に定義したい。
