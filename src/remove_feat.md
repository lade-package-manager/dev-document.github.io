# remove

`remove` コマンドは、指定されたパッケージを削除（アンインストール）するためのコマンドです。

### 動作の流れ

1. `remove` を実行すると、Lade は対象のパッケージの情報を表示し、削除するか確認を求めます。
2. ユーザーが `y` または `yes` を入力すると、アンインストールを実行します。
3. 実行ファイルを削除し、`installed/installed.json` からパッケージ情報を削除します。

### 出力例

削除前に、対象のパッケージの詳細が表示されます：

```
>>> Package details:
  - Name: hello_lade
  - Version: 1.0.0
  - Description: Test package for lade

>>> Are you sure you want to remove this package?
[y/N] y
```

`y` または `yes` を入力すると、Lade はパッケージを削除し、インストール記録からも削除します。
