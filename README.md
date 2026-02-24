## Daily_Task_Tracker
日報管理を行うスクリプトになります

## ソース概要
Excelで管理された詳細タスクと、ソースコード内に定義された全体進捗を組み合わせ、パワーポイント形式の報告書を自動作成するツールです。


## ディレクトリ構造
.
├── src/                # Source code / ソースコード
├── data/
│   └── 詳細タスク/      # Input Excel files / 各プロジェクトの進捗データ (.xlsx)
├── result/             # Final processed data / 処理済みデータ
├── temp/               # Intermediate files / 中間ファイル
└── 報告/                # PowerPoint outputs / パワーポイント出力


## データ仕様
エクセル作成のルール

シート名: .xlsxを除いたファイル名と一致させてください（例：プロジェクトA.xlsx ならシート名も プロジェクトA）。

カラム構成


エクセルは以下のカラム構造で作成してください。


No.

報告日 (Report Date)

業務内容 (Task Category)

業務内容詳細 (Task Details)

結果 (Result)

進捗度 (Progress)

備考 (Remarks)

※カッコの記載は不要です　カラムの意味です。すべて記載するとエラーになります。

## 特徴と使い方
1. 自動レポート作成

実行日の日付を読み取り、プロジェクト（エクセルファイル）ごとにパワーポイント資料を作成します。

2. 全体と詳細の統合

全体的な進捗状況から詳細なタスク状況まで、細かく記載できる仕様になっています。

全体進捗: 全体的な進行状態（ガントチャート、アクションプラン）は、メインのソースコードにハードコーディングする仕様になっています。全体図を更新する場合はコード内の値を修正してください。

詳細進捗: 各タスクの細かい進捗は、エクセルデータから動的に読み込まれます。


## 実行方法

Place your data in data/詳細タスク/.

Review/Update the Gantt chart data in the source code (src/).

Execute the script:

bash

python src/main.py
Check the 報告/ folder for the generated .pptx files.

data/詳細タスク/ にエクセルを配置します。

src/ 内のコードでガントチャート等の値を必要に応じて更新します。

スクリプトを実行します。

報告/ フォルダに出力されたパワーポイントを確認してください。


