# moum player

**手持ちの曲をきれいに並べて、すぐ再生できる音楽プレイヤー（Windows 用）。**

![moum player のメイン画面](docs/images/main.png)

- 曲・アルバム・アーティスト・プレイリストで一覧して、ギャップレスで再生
- 曲の情報（タグ）の編集、iTunes ライブラリの取り込み
- DJ ソフト [moum deck](https://github.com/mome0311/moum_deck) と一緒に使うと、さらに便利（単体でも使えます）

**[⬇ 最新のインストーラー（Releases）](../../releases/latest)**　・　**[📖 詳しい使い方](docs/guide.md)**

## moum player ならではの機能

**① moum deck の解析結果をそのまま表示**
DJ ソフト moum deck で解析した BPM・キーが曲の一覧に並び、キューポイントはシークバーに色付きの印で出ます。moum deck のプレイリストもサイドバーに出ます（読み取り専用）。

**② 買った記録を曲に残せる**
レーベル・カタログ番号に加えて、購入日・価格・購入元（Bandcamp / Beatport / iTunes Store / CD）を記録できます。サイドバーで購入元ごとに絞り込めます。

**③ DJ ソフト用に書き出し**
moum deck 用の USB、この PC の moum deck、rekordbox XML、Traktor NML へ書き出せます。

**④ タグの書き込みは元に戻せる**
曲の情報を直すと音楽ファイルのタグにも書き込めます。書き込みは記録され、あとから元に戻せます（約 180 日分）。

| ① moum deck のプレイリスト | ② 曲の情報を編集 |
|---|---|
| ![moum deck のプレイリストを開いた画面。BPM とキーが並ぶ](docs/images/playlist.png) | ![Edit properties ダイアログ。購入日・価格・購入元の欄がある](docs/images/edit_properties.png) |

| ③ 書き出し | アルバム表示 |
|---|---|
| ![Export library 画面](docs/images/export.png) | ![Albums ビュー](docs/images/albums.png) |

## はじめかた

1. [Releases](../../releases/latest) からインストーラー（`moum_player-x.x.x-Setup.exe`）をダウンロードして実行
2. **File › Add folder…**（Ctrl O）で音楽フォルダーを選ぶ（moum deck を使っている場合は、そのライブラリが自動で出ます）
3. 曲をダブルクリックして再生

対応形式は FLAC / MP3 / WAV / AIFF です。M4A（AAC / ALAC）だけ ffmpeg が必要です。

取り込み・タグの書き込み・書き出し・設定・トラブル対処は、[詳しい使い方](docs/guide.md) にまとめています。

<sub>スクリーンショットは v1.0.1。写っている曲は撮影用のサンプルです。</sub>
