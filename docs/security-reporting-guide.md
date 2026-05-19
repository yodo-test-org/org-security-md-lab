# Security 報告のやり方

この資料は、GitHub でセキュリティ上の問題を報告する方法を確認するためのものです。

GitHub には大きく分けて、次の 2 つの経路があります。

1. `SECURITY.md` に書かれた手順に従って報告する。
2. Private vulnerability reporting が有効なリポジトリで、GitHub のフォームから非公開で報告する。

## まず確認する場所

対象リポジトリを開いたら、まず次を確認します。

- リポジトリの `SECURITY.md`
- **Security** タブ
- **Security** タブ内の **Policy** または **Security policy**
- **Security** タブ内の **Advisories**

`SECURITY.md` は、脆弱性をどう報告すべきかを公開するためのファイルです。

Private vulnerability reporting は、GitHub 上の非公開フォームから直接メンテナへ報告する機能です。

この 2 つは別の機能です。`SECURITY.md` が存在していても、Private vulnerability reporting が有効とは限りません。

## 報告者側: Private vulnerability reporting が有効な場合

対象リポジトリで Private vulnerability reporting が有効な場合は、GitHub の画面から非公開で報告できます。

手順:

1. 対象リポジトリを開く。
2. **Security** タブを開く。
3. **Advisories** を開く。
4. **Report a vulnerability** を押す。
5. フォームに内容を入力する。
6. **Submit report** を押す。

フォームでは、少なくとも title と description が必要です。

可能であれば、次の情報も書きます。

- 影響を受けるバージョン
- 影響を受ける機能やファイル
- 再現手順
- 想定される影響
- 攻撃に必要な条件
- 回避策
- proof of concept
- 修正案

報告が送信されると、GitHub はリポジトリの管理者や security manager に通知します。

## 報告者側: Private vulnerability reporting が無効な場合

Private vulnerability reporting が無効なリポジトリでは、**Report a vulnerability** ボタンが表示されない場合があります。

その場合は、次の順で対応します。

1. `SECURITY.md` を確認する。
2. `SECURITY.md` に書かれた連絡先や手順に従う。
3. `SECURITY.md` がない、または連絡手段がない場合は、公開 issue に詳細を書かない。
4. 公開 issue では「セキュリティ連絡先を教えてほしい」とだけ依頼する。

公開 issue に脆弱性の詳細、再現手順、攻撃コードを書かないでください。

## メンテナ側: 報告を受け取ったあと

Private vulnerability reporting で報告を受けた場合、メンテナは報告を確認して次のいずれかを選びます。

- accept して draft security advisory として扱う。
- 追加情報を依頼する。
- 対象外として reject する。

accept した場合は、GitHub の security advisory 上で非公開に議論し、必要に応じて temporary private fork で修正できます。

修正後、メンテナは security advisory を公開して、利用者に脆弱性情報と対応方法を知らせることができます。

## メンテナ側: Private vulnerability reporting を有効化する

リポジトリ単位で有効化する手順:

1. 対象リポジトリを開く。
2. **Settings** を開く。
3. サイドバーの **Security** セクションから **Advanced Security** を開く。
4. **Private vulnerability reporting** を **Enable** にする。

Organization 単位では、GitHub の security configuration を使って、新しく作成される public repository に対して有効化できます。

## この学習リポジトリで確認すること

このリポジトリでは、次を確認します。

- ルートに `SECURITY.md` がない場合、`yodo-test-org/.github/SECURITY.md` が表示されるか。
- **Security** タブに security policy が表示されるか。
- Private vulnerability reporting を有効にしたとき、**Report a vulnerability** ボタンが表示されるか。
- `examples/repository-SECURITY.md` を `SECURITY.md` にコピーしたとき、リポジトリ固有の policy が優先されるか。

## 報告テンプレート

報告する場合は、次のテンプレートを使うと確認しやすくなります。

```text
タイトル:
  例: 認証なしで管理者向け API にアクセスできる

概要:
  何が問題かを短く説明する。

影響:
  誰が、何を、どの条件でできてしまうかを書く。

影響範囲:
  影響を受けるバージョン、ブランチ、機能、URL、パッケージなど。

再現手順:
  1.
  2.
  3.

期待される挙動:
  本来どうあるべきか。

実際の挙動:
  実際に何が起きるか。

証跡:
  ログ、スクリーンショット、リクエスト、レスポンスなど。

回避策:
  既知の回避策があれば書く。

補足:
  修正案、関連 issue、関連 commit など。
```

## 注意点

- public issue に脆弱性の詳細を書かない。
- exploit code や攻撃手順は、公開前に public にしない。
- 報告先が分からない場合は、詳細を伏せて連絡先だけ確認する。
- `SECURITY.md` は報告手順の案内であり、Private vulnerability reporting の有効化とは別物。

## 参考資料

- Privately reporting a security vulnerability
  https://docs.github.com/en/code-security/how-tos/report-and-fix-vulnerabilities/report-a-vulnerability
- Configuring private vulnerability reporting for a repository
  https://docs.github.com/en/code-security/security-advisories/working-with-repository-security-advisories/configuring-private-vulnerability-reporting-for-a-repository
- About repository security advisories
  https://docs.github.com/code-security/security-advisories/working-with-repository-security-advisories/about-repository-security-advisories
