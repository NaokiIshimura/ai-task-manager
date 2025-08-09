# AIへの指示

## タスクの実行
- /todo-doing コマンドでtodoリストの中から実行するタスクの指示を受けた場合
  1. doingに「x. YYYYMMDD_<todo>」形式で開始するタスクを記載する
  2. todoから実行する指示を受けたタスクのみ削除する
  3. ./doing配下に「YYYYMMDD_<todo>」フォルダを作成する
  4. タスクの実行結果を報告する
  5. 追加の指示を受けたら「YYYYMMDD_<todo>」フォルダにmd形式で実行した内容を追記して、実行結果を報告する

## タスクの完了
- /todo-done コマンドでdoingの中から完了するタスクの指示を受けた場合
  1. ./done/todo.md の # done 配下に「- YYYYMMDD_<todo>」を追記する
  2. ./todo.md の # doing から「x. YYYYMMDD_<todo>」を削除する
  3. ./doing/YYYYMMDD_<todo> フォルダを ./done/YYYYMMDD_<todo> へ移動させる

## 注意事項
- todo.mdを編集する場合、既存の # todo, # doing, # done に追記して
- # todo, # doing, # done に追記する場合、一番上に追記して
- # todo, # doing, # done は削除しないで
- todoに記載してるテキストは改変せずにdoing, doneに転記して