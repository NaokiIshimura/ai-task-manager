# /todo-reopen コマンド

## 概要
doneリストから完了済みタスクを選択してdoingに戻し、再開処理を行う

## 使用方法
```
/todo-reopen <タスク番号>
```

## 処理内容
1. タスク番号が引数に指定されているか確認
   - 指定されていない場合はユーザーに確認を求める
2. ./done/todo.mdのdoneセクションから指定された番号のタスクを取得
3. ./todo.md の # doing セクションに「x. YYYYMMDD_<todo>」を追加（xは新しい番号）
4. ./done/todo.md の # done セクションから該当タスクを削除
5. ./done/YYYYMMDD_<todo> フォルダを ./doing/YYYYMMDD_<todo> へ移動

## 例
```
/todo-reopen 1
```

## 動作例
実行前:
./done/todo.md:
```
# done
1. 20250809_今日の東京都の天気を確認して
2. 20250810_議事録を作成して
```

./todo.md:
```
# doing

# todo
1. 明日の東京都の天気を確認して
```

実行後 (/todo-reopen 1):
./done/todo.md:
```
# done
1. 20250810_議事録を作成して
```

./todo.md:
```
# doing
1. 20250809_今日の東京都の天気を確認して

# todo
1. 明日の東京都の天気を確認して
```
