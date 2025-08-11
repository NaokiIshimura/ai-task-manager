# /todo-done コマンド

## 概要
doingリストからタスクを選択してdoneに移動し、完了処理を行う

## 使用方法
```
/todo-done <タスク番号>
```

## 処理内容
1. タスク番号が引数に指定されているか確認
   - 指定されていない場合はユーザーに確認を求める
2. todo.mdのdoingセクションから指定された番号のタスクを取得
3. ./done/todo.md の # done セクションに「- YYYYMMDD_<todo>」を追加
4. ./todo.md の # doing セクションから該当タスクを削除
5. ./doing/YYYYMMDD_<todo> フォルダを ./done/YYYYMMDD_<todo> へ移動

## 例
```
/todo-done 1
```

## 動作例
実行前:
```
# doing
1. 20250809_今日の東京都の天気を確認して

# todo
1. 明日の東京都の天気を確認して
```

実行後 (/todo-done 1):
```
# doing

# todo
1. 明日の東京都の天気を確認して
```

./done/todo.md:
```
# done
- 20250809_今日の東京都の天気を確認して
```
