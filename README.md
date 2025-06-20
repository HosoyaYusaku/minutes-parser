# Minutes Parser

An interactive Google Colab tool to parse meeting minutes from various file formats (`.txt`, `.docx`, `.pdf`) into structured JSON data.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## ✨ Features

* **Multi-Format Support**
  Reads `.txt`, `.docx`, and `.pdf` files.
* **Customizable Delimiters**
  Easily set the characters that mark the beginning of a new speech (e.g., `▲`, `○`).
* **Smart Speaker Extraction**
  Automatically identifies the speaker and their utterance.
* **Structured JSON Output**
  Converts unstructured text into a clean, structured JSON format perfect for further analysis or use in RAG systems.
* **Batch Processing**
  Process multiple minutes files at once.
* **ZIP Archive Output**
  All generated JSON files are bundled into a single downloadable ZIP archive.
* **Interactive UI**
  An easy-to-use interface built with `ipywidgets` right in Google Colab.

---

## 🚀 How to Use

1. **Open in Colab** <a href="https://colab.research.google.com/github/あなたのユーザー名/minutes-parser/blob/main/minutes_parser.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
2. **Set Delimiters**
   At the top of the notebook, modify the `delimiters_input` variable to match your documents’ markers.
3. **Upload Files**
   Click **「ファイル選択 (Choose Files)」** and select one or more meeting-minutes files.
   *(Optional: try the sample in `sample_data/`.)*
4. **Process**
   Click **「処理開始 (Start Processing)」**. A preview of the extracted data will appear.
5. **Download**
   Once complete, click **「ダウンロードする (Download)」** to save the ZIP archive of your JSON files.

---

## 📋 Input File Format

* **Filename Convention**
  `YYYYMMDD_MeetingName.ext`
  *Example:* `20240521_ProjectKickoff.docx`
  (Tool auto-extracts date and session name.)
* **Content Structure**
  Each speech must begin with one of your chosen delimiters:

  ```text
  ▲Speaker A (Team X)
  Good morning, everyone. Today we will discuss the project schedule.

  ○Speaker B (Team Y)
  I have a question about the budget.
  ```

---

## 📦 Output Format

The tool outputs a ZIP archive with one JSON file per successfully processed input. Each JSON file contains a list of chunks:

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
  }
  // ...
]
```

---

# 議事録パーサー (Minutes Parser)

議事録ファイル（`.txt`, `.docx`, `.pdf`）を読み込み、発言者ごとの構造化されたJSONデータに変換するインタラクティブなGoogle Colabツールです。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## ✨ 主な機能

* **複数フォーマット対応**
  `.txt`, `.docx`, `.pdf` の各ファイル形式を読み込み可能。
* **区切り文字のカスタマイズ**
  発言の開始を示す記号（例: ▲, ○）を自由に設定可能。
* **発言者の自動抽出**
  発言者と内容を自動的に分離。
* **構造化JSON出力**
  RAGシステムやデータ分析に最適なJSON形式で出力。
* **バッチ処理**
  複数ファイルを一度に処理。
* **ZIPアーカイブ出力**
  生成されたJSONファイルをまとめてZIP化。
* **インタラクティブUI**
  `ipywidgets` を使った直感的なUI。

---

## 🚀 使い方

1. **Colabで開く** <a href="https://colab.research.google.com/github/あなたのユーザー名/minutes-parser/blob/main/minutes_parser.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
2. **区切り文字の設定**
   ノートブック冒頭の `delimiters_input` を編集。
3. **ファイルのアップロード**
   **「ファイル選択」** ボタンで議事録ファイルを選択。
   *(sample\_data 内のサンプルも利用可能)*
4. **処理開始**
   **「処理開始」** をクリックし、データプレビューを確認。
5. **ダウンロード**
   **「ダウンロードする」** ボタンでZIPファイルを保存。

---

## 📋 入力ファイル形式

* **ファイル名規約**
  `YYYYMMDD_会議名.ext`
  例: `20240521_プロジェクト定例.docx`
  (日付と会議名を自動抽出)
* **内容構造**
  各発言は指定した区切り文字から開始：

  ```text
  ▲Aさん（Xチーム）
  おはようございます。本日はプロジェクトのスケジュールについて議論します。

  ○Bさん（Yチーム）
  予算について質問があります。
  ```

---

## 📦 出力形式

処理成功ファイルごとに1つのJSONを生成し、ZIPにまとめます。JSONは以下のチャンクリスト形式です：

```json
[
  {
    "metadata": {
      "date": "2024-05-21",
      "session": "プロジェクト定例",
      "speaker": "▲Aさん（Xチーム）",
      "number": "a1b2c3d4-00001"
    },
    "content": "おはようございます。本日はプロジェクトのスケジュールについて議論します。"
  }
  // ...
]
```

---

## 📄 ライセンス

This project is licensed under the MIT License.
詳細は `LICENSE` ファイルをご覧ください。
