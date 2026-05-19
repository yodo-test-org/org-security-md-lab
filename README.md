# GitHub Organization Features Lab

このリポジトリは、`yodo-test-org` で GitHub Organization の機能を学ぶための実験用リポジトリです。

最初のテーマは `SECURITY.md` と、Organization 共通の default community health files です。

## このリポジトリで確認すること

- `SECURITY.md` を持たないリポジトリに、`yodo-test-org/.github/SECURITY.md` が継承されるか。
- GitHub の画面上で security policy がどこに表示されるか。
- リポジトリ固有の `SECURITY.md` を追加すると、表示がどう変わるか。
- Organization 共通ファイルとリポジトリ固有ファイルの優先順位。

## 重要な設計

このリポジトリには、意図的にルートの `SECURITY.md` を置いていません。

理由は、最初の実験で Organization 共通の security policy が継承されることを確認するためです。

継承元:

https://github.com/yodo-test-org/.github/blob/main/SECURITY.md

あとでこのリポジトリに固有の `SECURITY.md` を追加すると、Organization 共通の policy よりもリポジトリ固有の policy が優先されるはずです。

## 実験手順

1. GitHub でこのリポジトリを開く。
2. **Security** タブを開く。
3. サイドバーから **Policy** または **Security policy** を開く。
4. 表示される policy が `yodo-test-org/.github` 由来か確認する。
5. 新しい issue の作成画面を開き、security policy へのリンクが表示されるか確認する。
6. `examples/repository-SECURITY.md` を `SECURITY.md` としてコピーする。
7. commit する。
8. もう一度 **Security** タブを開き、リポジトリ固有の policy が使われるか確認する。

## ファイル構成

- `docs/security-md-behavior.md`: `SECURITY.md` の挙動メモ。
- `docs/default-community-health-files.md`: Organization 共通ファイルの挙動メモ。
- `examples/repository-SECURITY.md`: リポジトリ固有 `SECURITY.md` のサンプル。

## 参考資料

- GitHub Docs: Creating a default community health file
  https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file
- GitHub Docs: Adding a security policy to your repository
  https://docs.github.com/github/managing-security-vulnerabilities/adding-a-security-policy-to-your-repository
