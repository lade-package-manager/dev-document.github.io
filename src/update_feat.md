# update

`update` コマンドは、Lade のパッケージリストを最新の状態に更新します。

Lade には、2種類のパッケージリストがあります：

1. **main.zip**  
   - Lade オリジナルのパッケージを管理するリストです。
   
2. **extra.zip**  
   - Vim や Curl など、さまざまな一般的なパッケージを管理するリストです（現在は未実装ですが、今後追加予定です）。

`update` コマンドは、これらのリストをダウンロードし、`lade/packagelists/lade/` フォルダに格納します。

**特徴**：
- `main.zip` は頻繁に更新されます。
- `extra.zip` はあまり更新されません（今後の実装予定）。

現在、Lade はパッケージリストが更新されていなくても `update` を実行しますが、将来的にはこの挙動が改善される予定です。ですが、Lade はまだ開発段階なので、その実装はもう少し先になります。
