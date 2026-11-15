# データ仕様 v001

- `question_id`: `R08-AM-Q01` / `R08-PM-Q01` 形式の固定ID。年度追加後も既存IDを変更しない。
- `AM_questions.csv`: 午前択一35問の問題単位全文。
- `PM_multiple_choice.csv`: 午後択一35問の問題単位全文。
- `PM_written.csv`: 午後記述2問。設例・別紙等を含むページ範囲の全文。
- `answer_key.csv`: 予備校解答番号。公式解答と別列で保持。
- `items_draft.csv`: 肢ア〜オの自動分割候補。PDF原本との照合前であり、確定肢データではない。
- `source_pages.csv`: PDFページ単位の抽出全文。照合・再処理用。
- `manifest.json`: 年度、科目範囲、件数、ファイル一覧。

## 品質区分
`extracted_text` はPDFから抽出したテキスト。文字順・段組・表・ルビ・図版の崩れがあり得る。`items_draft` は抽出候補。予備校解答はユーザー提供情報。公式正解、肢別法的正誤、根拠は未検証。

## 年度追加
`data/R07/` 等の年度フォルダを追加し、その中に同じ形式の `manifest.json` とCSVを置く。アプリはGitHub Contents APIで `data/` 配下の `Rxx` フォルダを検出する。公開リポジトリが前提。
