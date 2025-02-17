# clean

`clean` コマンドは、不要なファイルを削除してディスクスペースを確保するためのコマンドです。具体的には、以下のディレクトリを削除し、再作成します：

- **cache ディレクトリ**
- **logs ディレクトリ**
- **build ディレクトリ**

## 各ディレクトリの説明

#### build ディレクトリ
Lade はビルドやインストールが完了した後も `build` ディレクトリの内容を削除しません。そのため、ビルド時に生成された不要なファイルが残り、ストレージを圧迫する可能性があります。

#### logs ディレクトリ
Lade はエラー発生時に `lade/logs/logs/lade.log` にエラーログを記録します。  
エラーが数回発生する程度では問題ありませんが、開発中の Lade ではエラーが頻発することもあり、ログファイルのサイズが大きくなる可能性があります。

例えば、過去には `.lade/build.rhai` が存在するのに「見つからない」というエラーが発生する不具合がありました（現在は修正済み）。このようなエラーが繰り返されると、ログが蓄積され、ストレージを圧迫します。  
そのため、定期的に `clean` を実行し、不要なログを削除することをおすすめします。

#### cache ディレクトリ
Lade は `cache` ディレクトリにパッケージをダウンロードしますが、使用後に自動で削除しません。  
たとえ ZIP 形式で圧縮されていたとしても、パッケージファイルはサイズが大きくなる可能性があるため、不要になったキャッシュファイルを削除することで、ディスク容量を節約できます。

## clean の実行方法

`clean` コマンドを実行すると、次の確認メッセージが表示されます：

```sh
This operation will clean the log file, build directory, and cache directory. Do you want to accept?

# この操作は、logファイル、buildディレクトリ、cacheディレクトリをクリーンします。実行しますか？
```

`y` または `yes` を入力すると、Lade は `logs`、`build`、`cache` ディレクトリを削除します。

削除後、必要なディレクトリは Lade が自動で再作成するため、手動で作成する必要はありません。  
この操作によって、不要なファイルを一括で削除し、ディスクスペースを確保できます。