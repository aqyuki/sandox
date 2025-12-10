# Go Linker Check

Goの実行ファイルがどの用に成り立っているのかを調べたプロジェクト。

## Prepare

`make`を実行することで以下のファイルが生成される。

1. 実行ファイル
2. `go tool objdump`の出力結果
3. `otool` の出力結果