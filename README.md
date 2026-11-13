# Bus.Locky｜あすか交通・稲毛線

稲毛駅・幸町中央ロータリーの発車時刻をカウントダウン表示する、スマートフォン向けWebアプリです。

## 対象経路

1. 稲毛駅 → 幸町団地循環（稲毛駅停留所の発車時刻）
2. 幸町中央ロータリー → 稲毛駅（幸町中央ロータリー停留所の発車時刻）

## 時刻表データ

- `data/timetable.json` は公式PDFの「平日」「土休日」欄から停留所別に転記しています。
- 公式PDF: https://askabus.com/wp-content/themes/aska/pdf_bus/route_inage_timetable.pdf
- GitHub Actions が毎日21:00（日本時間）に公式PDFを取得し、前回取得分と比較します。
- PDFの更新を検出した場合はPDFを保存してIssueを作成します。時刻の読み違いを防ぐため、JSONへの反映は差分確認後に行います。
- アプリの「時刻表を更新」は公開済みJSONをキャッシュ回避で再読み込みします。

## 公開方法

GitHub Pages を有効にし、Build and deployment の Source を「Deploy from a branch」、Branch を `main`、Folder を `/ (root)` に設定してください。

## 注意

道路状況により実際の到着・発車が遅れる場合があります。本アプリは公式時刻表を表示するもので、リアルタイムのバス位置・遅延情報ではありません。
