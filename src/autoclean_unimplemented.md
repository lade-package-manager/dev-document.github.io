# autoclean (unimplemented)

`autoclean` コマンドは、不要になった依存パッケージを自動で削除する機能として実装予定です。

### 背景

Lade はパッケージをインストールする際に依存関係を解決しますが、`remove` コマンドでパッケージを削除しても、その依存関係までは削除しません。  
そのため、不要になったパッケージがシステムに残り続ける可能性があります。

### 実装予定の機能

- `autoclean` は、不要になった依存パッケージを自動的に検出し、削除する機能を持ちます。
- `apt` の `autoremove` に似た動作を想定しています。

### 現状

Lade には `autoclean` 以外にも実装予定の機能が多く、まだ開発には着手できていません。  
今後のアップデートで追加される予定です。

