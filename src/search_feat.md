# search

`search` コマンドは、Lade に登録されているパッケージの中から指定されたパッケージを検索し、見つかった場合は詳細情報を表示します。

## 動作の流れ

1. `search` コマンドを実行すると、Lade はパッケージリスト内で指定されたパッケージを検索します。
2. パッケージが存在する場合、対応する `info.toml` を読み込み、パッケージ情報を取得します。

### パッケージ情報の構造

Lade のパッケージリストは `main.zip` などのファイルに格納されており、以下のようなディレクトリ構造になっています：

```
.
├── hello_lade
│   └── info.toml
├── lamuta
│   └── info.toml
└── rumya
    └── info.toml
```

各パッケージごとにフォルダが作成され、その中に `info.toml` が格納されています。  
Lade は指定されたパッケージのディレクトリを検索し、`info.toml` を読み込みます。

### `info.toml` の内容

`info.toml` には以下のような情報が含まれています：

```toml
name = "hello_lade"
version = "1.0"
description = "Test package for lade"
license = "MIT"
authors = ["Pik6C"]
dependencies = [""]
repository = "https://github.com/lade-package-manager/hello_lade"
```

- **name**: パッケージ名  
- **version**: 最新バージョン  
- **description**: パッケージの概要  
- **license**: パッケージのライセンス  
- **authors**: 作成者  
- **dependencies**: 依存パッケージ  
- **repository**: Git リポジトリ（ビルドインストール時に使用）

## 検索結果の表示

パッケージが見つかった場合、Lade は次のような情報を出力します：

```
>>> Package found in lade package list.
Name: hello_lade
Available Version: 1.0.0
Repository: https://github.com/lade-package-manager/hello_lade
Description: Test package for lade
License: MIT
Authors: Pik6C
```