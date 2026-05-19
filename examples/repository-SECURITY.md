# Repository Security Policy

これは、リポジトリ固有の security policy を試すためのサンプルです。

Organization 共通の `SECURITY.md` を上書きする挙動を確認したい場合は、このファイルをリポジトリのルートに次の名前でコピーします。

```text
SECURITY.md
```

そのファイルを commit すると、GitHub は `yodo-test-org/.github` の Organization 共通 policy ではなく、このリポジトリ固有の policy を使うはずです。

## 脆弱性報告

この学習用リポジトリでは、実際の脆弱性報告は扱いません。このファイルは、GitHub がリポジトリ固有の security policy をどのように検出・表示するかを確認するためだけに使います。

実際のリポジトリでは、少なくとも次の内容を含めます。

- 非公開の報告窓口
- 返信までの目安
- サポート対象バージョン
- 再現に必要な情報
- coordinated disclosure の方針
