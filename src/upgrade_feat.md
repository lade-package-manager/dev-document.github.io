# upgrade

`upgrade` コマンドは、Lade 自体を最新バージョンに保つために使用します。

`upgrade` を実行すると、まず Lade はパッケージリストを最新の状態に更新します。これにより、Lade がアップグレードされた後、新しいバージョンに対応したパッケージリストを使用できるようになります。

次に、Lade は [upgrade_info.json](https://github.com/lade-package-manager/lade/releases/download/upgrade_info/upgrade_info.json) をダウンロードします。この JSON ファイルには、Lade の最新バージョンに関する情報が含まれています。

もし現在の Lade のバージョンと最新バージョンが異なる場合、Lade は `self-upgrade` を実行します。

## self-upgrade

`self-upgrade` は、Lade が自分自身をアップグレードする処理です。以下の手順で行います：

1. Lade はまず [自分自身](https://github.com/lade-package-manager/lade) をクローンします。
2. クローンが完了すると、Lade は自分をビルドするために必要なツールを探します。

必要なツールは以下の通りです：

- **sh**  
  - Lade は内部でシェル (`sh`) を呼び出してインストールスクリプトを処理します。将来的に不要になる予定ですが、現在は依存しています。
  
- **cargo**  
  - Lade は Rust で書かれているため、ビルドに必要なツールです。

- **rustc**  
  - Rust コンパイラもビルドに必須です。

- **pkg-config + openssl 開発環境（Linux のみ）**  
  - Lade は Git リポジトリをクローンするために `git2` クレートを使用します。Linux 環境では `openssl` 開発環境と `pkg-config` が必要です。

これらのツールが全てインストールされていると、Lade はビルドを開始します。エラーがなければ、ビルド後に `target/release/lade` を `lade/bin/` に移動し、古いバージョンの Lade を新しいバージョンで置き換えます。

`self-upgrade` が成功すると、Lade は終了します。
