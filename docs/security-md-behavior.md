# SECURITY.md の挙動メモ

このメモは、このリポジトリで確認したい `SECURITY.md` の挙動をまとめたものです。

## `SECURITY.md` の役割

`SECURITY.md` は、利用者や外部の報告者に対して「脆弱性をどのように報告すればよいか」を伝えるためのファイルです。

GitHub では、リポジトリの **Security** 領域から security policy として表示されます。また、issue 作成時にも security policy へのリンクが表示されます。

## 認識される配置場所

リポジトリ固有の security policy として、GitHub は以下の場所にある `SECURITY.md` を認識します。

- リポジトリのルート
- `.github/SECURITY.md`
- `docs/SECURITY.md`

## Organization 共通の policy

Organization では、`.github` という名前の public リポジトリを作り、そこに `SECURITY.md` を置くことで、Organization 共通の security policy を提供できます。

この Organization の共通 policy:

https://github.com/yodo-test-org/.github/blob/main/SECURITY.md

GitHub は、対象リポジトリに同種のファイルが存在しない場合だけ、この default file を使用します。

## 優先順位の実験

初期状態:

- このリポジトリには `SECURITY.md` がない。
- 期待される挙動: `yodo-test-org/.github/SECURITY.md` が使われる。

上書き状態:

- `examples/repository-SECURITY.md` を `SECURITY.md` としてコピーする。
- commit して push する。
- 期待される挙動: このリポジトリ自身の `SECURITY.md` が使われる。

戻す場合:

- リポジトリ固有の `SECURITY.md` を削除する。
- 期待される挙動: Organization 共通の security policy に戻る。

## 観察ポイント

- **Security** タブで有効な policy が確認できるか。
- issue 作成画面に、有効な security policy へのリンクが表示されるか。
- リポジトリ固有ファイルが Organization 共通ファイルより優先されるか。
- public リポジトリに default community health files を適用するには、Organization の `.github` リポジトリも public である必要がある。
