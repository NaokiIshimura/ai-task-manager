# AI Task Manager

AIを活用したタスク管理マネージャーです。

## 概要

このプロジェクトは、Claude Codeと連携してタスク管理を効率化するシステムです。
タスクの状態を「todo」「doing」「done」の3つのステージで管理し、各タスクの実行履歴をフォルダで整理します。

## ファイル構成

```
ai-task-manager/
├── todo.md                 # タスクリスト（todo/doing/done）
├── ai-instructions.md      # AIへの詳細な指示
├── doing/                  # 実行中のタスクフォルダ
│   └── YYYYMMDD_<task>/   # タスクごとの作業フォルダ
├── done/                   # 完了したタスクフォルダ
│   ├── todo.md            # 完了タスクリスト
│   └── YYYYMMDD_<task>/   # 完了タスクの作業フォルダ
└── .claude/
    └── slash_commands/     # カスタムコマンド定義
        ├── todo.md
        ├── todo-doing.md
        ├── todo-done.md
        └── todo-resume.md
```

## Claude Code コマンド

### /todo
todoリストからタスクを取得して表示します。

```
/todo
```

### /todo-doing
todoリストからタスクを選択してdoingに移動し、実行を開始します。

```
/todo-doing <タスク番号>
```

### /todo-done
doingリストからタスクを選択してdoneに移動し、完了処理を行います。

```
/todo-done <タスク番号>
```

### /todo-resume
doingリストの既存タスクを再開して、作業を継続します。

```
/todo-resume <タスク番号>
```

## AIへの指示

AIへの指示は [ai-instructions.md](./ai-instructions.md) を参照してください。
