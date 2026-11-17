# moum player — 困ったとき

[🏠 ホーム](../README.md) ｜ [▶️ 基本の使い方](basics.md) ｜ [🎵 曲の管理](library.md) ｜ [💾 書き出しと設定](export-settings.md) ｜ **❓ 困ったとき**

---

## 14. トラブルシューティング・よくある質問

**moum deck の曲が出ない / 「NOT FOUND」と出る**
moum deck を使っていない場合は、そのままで問題ありません。moum deck を使っている場合は、**Settings › moum deck › Locate deck DB** で、`local_library.db` を選んでください。

**「LOCKED」と出る / 一覧が更新されない**
moum deck がデータベースを使っている最中は、一時的に読めないことがあります。前の一覧が表示されたままになり、しばらくすると自動で読み直されます。**Refresh now** でも読み直せます。

**M4A の曲が再生できない・取り込めない**
ffmpeg が必要です。Settings › Library › ffmpeg の **Install…**（または再生できない曲のお知らせの **Install ffmpeg**）で入れてください。入れたあと、取り込みをやり直してください。

**取り込んだ曲が moum deck に出ない**
- Settings › moum deck › **Add imported folders to moum deck** がオンか、確認してください。
- 「N folders wait to be added」と出ているときは、**Retry now** を押してください。moum deck が起動中で、データベースが使えなかった可能性があります。
- 古い版の moum deck は、取り込み元の登録に対応していないことがあります。moum deck 側で、フォルダーを追加してください。

**ファイルのタグを書き換えたくない**
編集画面の「Also write tags to file」のチェックを外してください（Settings › Tags › Write changes into the music files も同じ設定です）。
すでに書き込んだ分は、**Edit › Undo tag writes…** で戻せます。

**タグを書き込んだのに、moum deck の表示が変わらない**
moum deck が、手が空いたときに読み直します。しばらく待つか、moum deck を起動し直してください。古い版の moum deck では、読み直しの依頼が残されません。

**Export › moum deck on this PC が実行できない**
moum deck を終了してから、もう一度実行してください。起動中は、何も書き込まれません。

**moum deck USB の書き出しで、曲が一部コピーされない**
書き出し後の結果に「N files could not be copied」と出たら、ログを確認してください。元のファイルが見つからないときは、「N files were not found and are skipped」と出ます。

**起動が遅い**
Help の **Copy last startup timings** で、直近の起動時間をコピーできます。問題の連絡のときに、貼り付けて送ってください。
**Open startup log folder** で、記録ファイル（`startup_log.jsonl`）のフォルダーが開きます。
記録に入るのは、時間とバージョンの数字だけです。曲名やファイルの場所は入りません。直近 30 回分が残ります。

**スプラッシュを出したくない**
Settings › General › Show splash screen をオフにしてください。

**画面が大きすぎる・小さすぎる**
Ctrl + / Ctrl − / Ctrl 0、または Settings › General › Display size で変えてください。

**メディアキー（キーボードの再生・停止キー）**
対応していますが、実機での確認は十分ではありません。動かないときは、画面のボタンを使ってください。

**新しい版が出たか知りたい**
今のバージョンには、自動確認はありません。Releases のページで確認してください。

---

## 15. ライセンスとクレジット

- moum player は、GNU GPL バージョン 3 以降のフリーソフトウェアです。ライセンスの全文は、同梱の `LICENSE` にあります。
- 使っている第三者のソフトウェアとライセンスは、`THIRD_PARTY_NOTICE.md` にまとめています。アプリの **Help › Third-party notices** からも見られます。
  - Inter Tight フォント（SIL Open Font License 1.1）は、アプリに同梱しています。
  - ffmpeg は、同梱も再配布もしていません。あなたが Install ffmpeg を押したときだけ、公開されているビルドを取得します。
- Traktor は Native Instruments GmbH、rekordbox は AlphaTheta Corporation の商標です。
  moum player は、これらの企業とは関係のない、独立したソフトウェアです。

---

<sub>スクリーンショットは v1.0.1 のものです。画面に写っている曲は、撮影用に作ったサンプルです。</sub>
