# moum player — 曲の管理

[🏠 ホーム](../README.md) ｜ [▶️ 基本の使い方](basics.md) ｜ **🎵 曲の管理** ｜ [💾 書き出しと設定](export-settings.md) ｜ [❓ 困ったとき](faq.md)

---

## 5. 曲を取り込む

### 5-1. フォルダー・ファイルを取り込む

1. **File › Add folder…**（Ctrl O）でフォルダーを、**File › Add files…** でファイルを選びます。ウィンドウへのドラッグ＆ドロップでも始められます。
2. 曲を調べる画面になります（再生は続けられます）。調べ終わると、確認の画面が出ます。
3. 確認の画面で、次を決めて **Import** を押します。

| 項目 | 内容 |
|---|---|
| Save to (library folder) | 曲のコピー先。初期値は、ミュージックフォルダー内の `moum player` です。**Change…** で変えられます |
| Folder layout | コピー先でのファイル名の付け方。`Artist / Album / 01 Title`、`Artist / Album / Title`、`Artist - Album / 01 Title` から選びます |
| Duplicates | 重複していた曲を **Skip**（取り込まない）か **Import** にします（重複の見つけ方は下記） |
| Garbled tags | 文字化けして見えるタグを直して取り込みます（直した内容は moum player に保存され、ファイルは変えません） |
| Add to moum deck | 取り込み先のフォルダーを、moum deck の取り込み元に追加します（§1） |

- **取り込んだ曲は、いつも「ライブラリフォルダー」にコピーされます。元のファイルは変更しません。**
- 取り込めなかったファイル（ffmpeg がない M4A、取り込まない種類、読めないファイル）は、確認の画面の「NOT IMPORTED」に出ます。
- 重複は、次の 3 つで見つけます：すでにライブラリにある / 内容が同一 / タイトル・アーティスト・アルバム・長さが同じ。
- 途中で Cancel しても、取り込み済みの曲は残ります（途中のコピーは消えます）。
- 取り込む種類は **Settings › Library › File types** で選べます（FLAC / MP3 / M4A / WAV / AIFF。M4A は ffmpeg が必要。OGG は選べません）。
- moum deck が起動中でデータベースが使えないときは、フォルダーの登録が「待ち」になり、あとで自動で再試行します。
  **Settings › moum deck** の **Retry now** で、すぐにやり直せます。

### 5-2. iTunes / Music ライブラリを取り込む

1. iTunes（または Music）で、ライブラリを書き出して `Library.xml` を作ります（iTunes: ファイル › ライブラリ › ライブラリを書き出す…）。
2. **File › Import iTunes library…** で、その XML ファイルを選びます。
3. あとは §5-1 と同じ確認の画面です。曲のファイルが見つからないものは、「NOT IMPORTED」に数が出ます。

XML ファイルは読むだけで、変更しません。曲は、ライブラリフォルダーにコピーされます。

### 5-3. 以前の「その場のまま」の曲

以前の版で、コピーせずに追加した曲は、元の場所のまま再生されます。
**Settings › Library › Songs outside the library folder** に、そのフォルダーが出ます。
フォルダーの右の × で、そのフォルダーの曲を moum player から外せます（**ファイルは消えません**）。

### 5-4. ライブラリの読み直し

- **Settings › Library › Rescan now**：ライブラリの曲を、もう一度調べます。
- **Ctrl R**（Refresh library）：moum deck のデータを読み直します。
- moum deck が更新されたときは、数秒以内に自動で読み直されます（**Settings › moum deck › Refresh when moum deck closes**）。

---

## 6. 曲の情報を編集する・ファイルのタグに書き込む

### 6-1. 曲の情報を編集する

曲を選んで **Edit › Edit properties…**（Ctrl I）、または右クリックの **Edit properties…**。
アルバムごとは **Edit album info…**、複数の曲を選んだときは、共通の項目をまとめて変えられます
（曲によって違う項目は「Mixed」と出て、空のままなら変わりません）。

| 項目 | 内容 |
|---|---|
| Title / Artist / Album artist / Album / Genre / Track # / Year | 基本の情報 |
| Label / Catalog # | レーベルとカタログ番号 |
| Purchased / Price | 購入日（例：2024-03-05）と価格（例：¥1,500 / $9.99）。**moum player の中だけに保存され、ファイルにも moum deck にも書きません** |
| Source | 購入元。Bandcamp / Beatport / iTunes Store / CD / Other から選びます（もう一度押すと解除） |

- アルバムの **Change artwork…** で、カバー画像（JPEG / PNG）を差し替えられます。**Remove** で、ファイルのカバーに戻ります。
- BPM とキーは moum deck の解析結果で、ここでは変えられません。
- 文字化けして見えるタグがあると、修復案が出ます。**Use suggestions** で入力欄に入れられます。
- 編集内容は、まず moum player のデータ（`player.db`）に保存されます。**moum deck は変わりません。**

### 6-2. ファイルのタグに書き込む（初期設定でオン）

**この機能は、初期設定でオンです。** 編集画面の「Also write tags to file」にチェックが入った状態で始まり、Save を押すと、
音楽ファイルの中のタグ（タイトル・アーティスト・アルバム・ジャンル・年・トラック番号・カバーなど）も書き換えます。
こうすると、iTunes など他のプレーヤーでも、同じ情報が見えます。

- **ファイルそのものを書き換えます。** 書き換えたくないときは、編集画面で「Also write tags to file」のチェックを外します。
  チェックの状態は覚えられます。**Settings › Tags › Write changes into the music files** でも、オン・オフできます。
- 書き込む前の古い値は、`tag_write_log.jsonl`（moum player のデータフォルダー内）に残ります。
  元に戻したいときは、**Edit › Undo tag writes…**（§6-4）。
- moum deck のデータベースは、このとき変わりません。

### 6-3. まとめて書き込む：Edit › Write tags to files…

moum player が表示している内容（編集を含む）と、ファイルのタグが**違う曲だけ**を調べて、一覧にします。

1. **Edit › Write tags to files…** を開く（Settings › Tags › Write tags to files の **Preview…** でも同じ）。
2. 違いのある曲と、変わる項目（例：`Title: 旧 → 新`）が出ます。書き込まない曲は、チェックを外します。
3. **Write** を押すと、書き込みが始まります。途中で止めることもできます。
4. 結果（書き込んだ・すでに同じ・失敗）が出ます。

書き込む項目は、Title / Artist / Album artist / Album / Genre / Year / Track # / Disc # / BPM / Key / Label / Catalog # / Compilation / Cover です。
**購入日・価格・購入元は、ファイルに書きません。**
書き込めるファイルは、MP3 / AIFF / WAV / FLAC / M4A などです。

moum deck の曲にタグを書き込んだときは、moum deck に「このファイルのタグを読み直して」という依頼を残します（moum deck が起動中でも行います）。
moum deck は、手が空いたときに、タグ由来の項目だけを読み直します（BPM・キー・キュー・ループ・グリッドは変わりません）。
古い版の moum deck では、この依頼は残されません。

### 6-4. 元に戻す：Edit › Undo tag writes…

1. **Edit › Undo tag writes…** を開くと、最近の書き込みが、新しい順に並びます（記録は約 180 日分）。
2. 戻したい回を選ぶと、何が戻るかのプレビューが出ます。
3. **Restore** で戻します。

- ファイルのタグが、moum player が書いたときのままの曲だけが戻ります。**その後に変更された曲や、移動・削除された曲は、スキップされます。**
- その書き込みで変わった moum player 側の値（編集内容・差し替えたカバー）も、あなたがその後に変えていなければ、一緒に戻ります。

---

## 7. 整理ツール

いずれも、**Edit** メニューか **Settings › Tags** から開けます。実行の前にプレビューが出ます。

| ツール | 開く場所 | 内容 |
|---|---|---|
| 重複 | Edit › Find duplicates… | ライブラリに何度も入っている曲を見つけて、余分なコピーを隠します |
| 見つからないファイル | Edit › Find missing files… | 移動・名前変更でファイルが見つからなくなった曲の、新しい場所を探して付け替えます（再リンク） |
| アーティスト名の統一 | Edit › Merge artist names… | 大文字小文字・全角文字・スペース・「The」だけが違うアーティスト名を、1 つの書き方にそろえます |
| ファイルの整理 | Edit › Organise files… | moum player が取り込んだ曲を、タグに合わせて、ライブラリフォルダーの中で移動します（フォルダーの付け方は Settings › Library › Folder layout）。空になったフォルダーは消えます |
| 文字化けしたタグの修復 | 右クリック › Fix garbled tags…、Settings › Tags › Find garbled | 文字コードの取り違いで化けた日本語のタグを探して、直します |
| 欠けているタグの補完 | Edit › Complete missing tags… | タグが空の曲に、ファイル名などから、タイトル・アーティスト・アルバム・年・トラック番号の案を出します |

- アーティスト名の統一と、ファイルの整理は、実行したあとに「Undo」が出ます。
- 移動したファイルは、上書きされません。**moum deck の曲は、Organise files では移動しません。**
- アーティスト名の統一では、「Also write the name into the music files」で、ファイルのタグにも書き込めます（moum player が取り込んだ曲が対象です）。
- これらの変更は moum player に保存され、moum deck は変わりません。moum deck にも反映したいときは、§10-2 を使います。

---

## 8. カバー画像・タグのオンライン検索

- **Edit › Find missing covers…**：カバー画像のないアルバムを一覧して、オンラインで探します。
- **Edit › Complete missing tags…**：欠けているタグを、ファイル名から推測します。オンラインでも探せます。

**ボタン（Look up）を押したときだけ**、インターネットに接続します。送るのは、アルバム名・アーティスト名・曲名だけです。
接続先は、iTunes Search API と、MusicBrainz / Cover Art Archive です。
**Settings › Online › Look up covers and tags online** をオフにすると、オンライン検索は使いません。

見つけたカバーやタグは、まず moum player に保存されます。ファイルのタグへの書き込みは、画面でチェックしたときだけです。
moum deck は変わりません。

---

## 9. ライブラリの健康診断

起動の少しあとと、その後は 1 日に 1 回、ライブラリを調べます。**何も変更しません。**
サイドバーの下に、結果が **Library · OK** または **Library · 3 to check** のように出ます。クリックすると、一覧が開きます。

調べる項目：見つからないファイル / 重複 / 文字化けしたタグ / 表記ゆれのアーティスト名 / カバーのないアルバム。
項目ごとの **Open…** で、対応する整理ツール（§7、§8）が開きます。**Check now** で、すぐに調べ直せます。

**Settings › Tags › Check the library regularly** で、定期チェックをオフにできます。
