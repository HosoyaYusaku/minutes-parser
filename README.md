# Minutes Parser

An interactive Google Colab tool to parse meeting minutes from various file formats (`.txt`, `.docx`, `.pdf`) into structured JSON data.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## ✨ Features

- **Multi-Format Support**: Reads `.txt`, `.docx`, and `.pdf` files.
- **Customizable Delimiters**: Easily set the characters that mark the beginning of a new speech (e.g., `▲`, `○`).
- **Smart Speaker Extraction**: Automatically identifies the speaker and their utterance.
- **Structured JSON Output**: Converts unstructured text into a clean, structured JSON format perfect for further analysis or use in RAG systems.
- **Batch Processing**: Process multiple minutes files at once.
- **Convenient ZIP-file Output**: All generated JSON files are bundled into a single downloadable ZIP archive.
- **Interactive UI**: An easy-to-use interface built with `ipywidgets` right in Google Colab.

## 🚀 How to Use

The easiest way to use this tool is to open it directly in Google Colab.

<a href="https://colab.research.google.com/github/あなたのユーザー名/minutes-parser/blob/main/minutes_parser.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

1.  **Set Delimiters**: At the top of the notebook, modify the `delimiters_input` variable to match the characters used in your documents.
2.  **Upload Files**: Click the "ファイル選択 (Choose Files)" button and select one or more minutes files. **You can download and use the sample file in the `sample_data` folder to try it out immediately.**
3.  **Process**: Click the "処理開始 (Start Processing)" button. The tool will parse each file and show a preview of the extracted data.
4.  **Download**: Once processing is complete, a "ダウンロードする (Download)" button will appear. Click it to save the ZIP file containing your structured JSON data.

## 📋 Input File Format

For the best results, your files should follow these conventions:

-   **Filename Convention**: Files should be named in the format `YYYYMMDD_MeetingName.ext` (e.g., `20240521_ProjectKickoff.docx`). This allows the tool to automatically extract the date and session name.
-   **Content Structure**: Each speech should start with one of the specified delimiters.
    ```
    ▲Speaker A (Team X)
    Good morning, everyone. Today we will discuss the project schedule.

    ○Speaker B (Team Y)
    I have a question about the budget.
    ```

## 📦 Output Format

The tool generates a ZIP archive containing one JSON file for each successfully processed input file. Each JSON file contains a list of "chunk" objects, structured as follows:

```json
[
    {
        "metadata": {
            "date": "2024-05-21",
            "session": "ProjectKickoff",
            "speaker": "▲Speaker A (Team X)",
            "number": "a1b2c3d4-00001"
        },
        "content": "Good morning, everyone. Today we will discuss the project schedule."
    },
    // ... more chunks
]
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Markdown
IGNORE_WHEN_COPYING_END
📄 License

This project is licensed under the MIT License. See the LICENSE file for details.

<br>

議事録パーサー (Minutes Parser)

議事録ファイル（.txt, .docx, .pdf）を読み込み、発言者ごとの構造化されたJSONデータに変換する、インタラクティブなGoogle Colabツールです。

![alt text](https://img.shields.io/badge/License-MIT-yellow.svg)

✨ 主な機能

複数フォーマット対応: .txt, .docx, .pdf の各ファイル形式を読み込めます。

区切り文字のカスタマイズ: 発言の開始を示す記号（例: ▲, ○）を自由に変更できます。

発言者の自動抽出: 発言者と発言内容を自動的に分離します。

構造化JSON出力: 整形されていないテキストを、RAGシステムでの利用やデータ分析に適したクリーンなJSON形式に変換します。

バッチ処理: 複数の議事録ファイルを一度に処理できます。

便利なZIP出力: 生成された全てのJSONファイルは、一つのZIPファイルにまとめてダウンロードできます。

インタラクティブUI: ipywidgetsを使い、Google Colab上で直感的に操作できます。

🚀 使い方

このツールは、Google Colabで直接開いて使うのが最も簡単です。

<a href="https://colab.research.google.com/github/あなたのユーザー名/minutes-parser/blob/main/minutes_parser.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

区切り文字の設定: ノートブックの先頭にある delimiters_input の値を、あなたの議事録で使われている記号に合わせて編集します。

ファイルのアップロード: 「ファイル選択」ボタンを押し、議事録ファイルを1つ以上選択します。すぐに試したい場合は、sample_dataフォルダにあるサンプルファイルをダウンロードしてご利用ください。

処理開始: 「処理開始」ボタンをクリックします。各ファイルが解析され、抽出されたデータのプレビューが表示されます。

ダウンロード: 処理が完了すると「ダウンロードする」ボタンが表示されます。これをクリックすると、構造化されたJSONデータが入ったZIPファイルが保存されます。

📋 入力ファイルの形式

最適な結果を得るために、以下の規約に沿ったファイルを用意してください。

ファイル名の規約: YYYYMMDD_会議名.拡張子 という形式でファイル名を付けてください（例: 20240521_プロジェクト定例.docx）。これにより、日付と会議名を自動でメタデータとして抽出できます。

内容の構造: 各発言は、指定した区切り文字から始まるようにしてください。

Generated code
▲Aさん（Xチーム）
おはようございます。本日はプロジェクトのスケジュールについて議論します。

○Bさん（Yチーム）
予算について質問があります。
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
IGNORE_WHEN_COPYING_END
📦 出力データの形式

ツールは、処理に成功した入力ファイルごとに1つのJSONファイルを作成し、それらをZIPファイルにまとめて出力します。各JSONファイルには、以下のような構造の「チャンク」オブジェクトのリストが含まれます。

Generated json
[
    {
        "metadata": {
            "date": "2024-05-21",
            "session": "プロジェクト定例",
            "speaker": "▲Aさん（Xチーム）",
            "number": "a1b2c3d4-00001"
        },
        "content": "おはようございます。本日はプロジェクトのスケジュールについて議論します。"
    },
    // ... more chunks
]
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Json
IGNORE_WHEN_COPYING_END
📄 ライセンス

このプロジェクトはMITライセンスです。詳細はLICENSEファイルをご覧ください。