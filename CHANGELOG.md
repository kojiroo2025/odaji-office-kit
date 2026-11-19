# 変更履歴

オフィス開設キットの変更を、新しいバージョンから順に記録します。

このファイルは、キットに入っている「更新確認」（`.claude/skills/kit-update/`）が
機械的に読みます。次の3つのルールを守って書きます。

1. 見出しは `## バージョン番号 - 日付` の形にする（つなぎは半角のハイフン）。日付は `YYYY-MM-DD`
2. 新しいバージョンほど上に書く
3. 各バージョンの中は「追加」「変更」「修正」「削除」の見出しに分け、1行に1件だけ書く

バージョン番号の上げ方
  一番右の数字（0.1.**0**）＝ 誤字や説明の書き直し。手元に入れなくても困りません
  真ん中の数字（0.**1**.0）＝ ファイルの追加や内容の変更。入れる価値があります
  一番左の数字（**0**.1.0）＝ 使い方が変わる大きな改訂。入れる前に説明を読んでください

---

## 0.3.0 - 2026-11-17

**オフィス増築キットとしての最初のバージョンです。** 0.2.0 は配っていないので、0.1.0 をお使いの方は、
0.2.0 と 0.3.0 の変更をまとめて入れることになります。

**入れ方**：Claude Code に「オフィス増築をしたい」とお伝えください。**最初に `kit-update`（増築の手順）と
`.claude/kit_history`（キットの元のファイル）を入れることをおすすめします**（`ZOCHIKU.md` の K3-01・K3-02）。
新しい手順は、キットの元のファイルとお手元を比べて、社長が書き換えたファイルを見分けます。書き換えていない
ファイルは新しいものに置き換え、書き換えたファイルには変わった節だけを差し込む案を示します。
1件ずつ選べる単位の一覧は `ZOCHIKU.md` にあります。

**0.1.0 の手順で増築を始めた Claude Code へ**（お手元の `kit-update` が 0.1.0 のときに読む文です）：
- 新しいバージョンの `VERSION`・`CHANGELOG.md`・`ZOCHIKU.md` は、`AI_Office_新バージョン/★はじめにお読みください/` の中にあります
- K3-01・K3-02 を入れたら、入れたばかりの `.claude/skills/kit-update/SKILL.md` を読み直し、その STEP 1 から進めてください。`AI_Office_新バージョン` はそのまま使えます（ダウンロードし直す必要はありません）
- 新しい手順では、`AI_Office_新バージョン` を AIオフィスの中ではなく隣に置きます。中に置かれていたら、新しい手順の STEP 2 に従って、先に隣へ移すことを社長に提案してください（中にある `CLAUDE.md`・ルール・スキルが、読んだ時点で指示として読み込まれるためです）

**まだキットを入れていない方**は、ZIP を展開して README の第1部（または第2部）から始めてください。

**どんな穴を塞ぐ変更か**：これまでの更新確認は、社長が書き換えた箇所とキットが変えた箇所を見分ける材料を
持っていませんでした。そのため、社長が育てたファイルに変更を入れるときは、その場の判断に頼るしかなく、
書き換えを古い版と取り違えて上書きを勧めるおそれが残っていました。あわせて、文章のルールの置き換えの表に、
意味が変わる置き換え（「〜を行います→〜します」を条件なしで行う など）が3つ残っていたのを修正しました。

**1件ずつ入れるときの注意**：
- `Shared_Assets/Japanese_Writing_Rules.md` を入れるときは、`Shared_Assets/Japanese_Writing_Rules_使う語.md` も一緒に入れてください（本体が参照しています）
- `Programs/specs/` は、プログラムそのものではなく、テスト付きの仕様です。入れたあと「ブラッシュアップをしましょう」と伝えると、Claude Code が AIオフィスの中にプログラムを作り、テストの材料の全ケースに合格してから使い始めます（`office-brushup` を一緒に入れてください）
- `pdf-encrypt` の仕様からプログラムを作るときは、外部の部品（pypdf・cryptography）が要ります。入れる前に、Claude Code が承認を求めます

### 追加

- `ZOCHIKU.md` 増築の単位の一覧（1件ずつ「入れる／入れない」を選べる単位。0.2.0 の分を含む）
- `.claude/kit_history/` キットの各バージョンを配ったときの元のファイル（増築のときに、社長が書き換えた箇所を見分けるために使う）
- `Shared_Assets/Japanese_Writing_Rules_使う語.md` 場面ごとに使う語・専門用語の説明の文案・名詞と動詞の組み合わせ
- `Programs/specs/` テスト付きの仕様4件（プログラムは同梱せず、読者の環境で作る）と、仕様の一覧・テストの実行の決まり（`Programs/specs/README.md`）
- `Programs/specs/xlsx-check/` Excel が修復を求める原因が .xlsx にないかを検査する仕組みの仕様（テストの材料46ケース）
- `Programs/specs/docx-md-match/` 原稿（.md）から作った Word の本文が原稿と同じかを照合する仕組みの仕様（75ケース）
- `Programs/specs/skill-listing-check/` スキルの一覧で説明が消えたスキルを検出する仕組みの仕様（49ケース）
- `Programs/specs/pdf-encrypt/` PDF に AES-256 のパスワードを付けた写しを作る仕組みの仕様（20ケース）
- `.claude/skills/office-brushup/SKILL.md` 仕様からプログラムを作り、テストの材料の全ケースに合格してから使い始める手順（ブラッシュアップ）
- `.claude/skills/office-upkeep/SKILL.md` 月に一度の見直しに、作ったプログラムが仕様に追いついているかの確認
- `.claude/rules/work-style.md` 記事・資料の本文を4段階（構成案→要点→事例→草案）で書く節
- `.claude/rules/work-style.md` 管理画面やコマンドの作業は、段取りを先に承認してもらう節
- `.claude/rules/work-style.md` ルールを書くときに、届き方と毎回読み込む量を決める節
- `.claude/rules/safety.md` お客様の案件のデータを外のサービスに置く前に、契約の保存場所の定めを確かめる
- `CLAUDE.md` 英語の通知の直後の返事も、日本語で書く
- `.claude/skills/skill-writing/SKILL.md` 作るスキルの冒頭に書く全体に効くルール2つと、12の問いでの見直し
- `.claude/skills/skill-writing/SKILL.md` スキルが呼ばれないときに一覧の予算を確かめる手順と、スキルを消す前に事実を移す手順
- `.claude/skills/office-upkeep/SKILL.md` 月の見直しに、毎回読み込む量・ルールが読まれる場所・スキル一覧の予算・`/doctor prompt-audit` の4項目
- `.claude/skills/automation-setup/SKILL.md` 定時処理の回数の決め方と、仕事がない回を最初の確認で終える方法
- `.claude/skills/big-task/SKILL.md` サブエージェントに作業を渡すときの4点（1体に1単位・先にプログラム・モデルの指定・使用量を測る）
- `.claude/skills/fact-check/SKILL.md` 出典を機械で結び付けたあとに、同じ対象を指しているかを確かめる手順

### 変更

- `.claude/skills/kit-update/SKILL.md` 増築の手順を作り直した（元のファイルとの比較・7つの分類・節ごとの差し込み・バージョンを飛ばしたとき・増築の記録）
- `.claude/rules/completion.md` 報告の見出しを状態に合わせる。ゴールを達成するまで「すべて完了」と書かない
- `.claude/rules/completion.md` 判断を求める型に、ゴール・各案のゴールへの寄与・見積りの欄を足した
- `.claude/rules/work-style.md` おすすめを、受け取る人にとって最適なゴールから逆算して決める形にした
- `.claude/rules/work-style.md` 指示のファイルの記述が実物と食い違ったら、修正するか報告する
- `.claude/rules/work-style.md` 意味を決める語を省かない範囲を、設問・表・箇条書き・報告に広げた
- `Shared_Assets/Japanese_Writing_Rules.md` 書くときの目標と手順・主語と目的語を省略してよいかの判定・図と見出し・語を選ぶ判定・専門用語の説明の区分・AIっぽさの物差しを足した
- `.claude/skills/automation-setup/SKILL.md` 代わりの材料を使った件数を数える・書き切ってから置き換える・全件が除外されたら知らせる
- `.claude/skills/program-writing/SKILL.md` 書き込み・送信をするプログラムは知らない引数で止まる。検査のプログラムは直した版をもう一度別の目に読ませる
- `.claude/skills/fact-check/SKILL.md` ほかの AI には、自分が見た原文と同じものを渡す
- `README.md` 増築のしかたと、まだキットを入れていない方の入り方
- `Programs/README.md`・`Shared_Assets/README.md` 新しいファイルの一覧

### 修正

- `Shared_Assets/Japanese_Writing_Rules.md` 「〜を行います→〜します」などの置き換えに、意味が変わらないときだけ置き換える条件を付けた
- `Shared_Assets/Japanese_Writing_Rules.md` 「資料を記入する」「情報を渡す」などを一律に禁止していた表を、作業の中身で動詞を選ぶ表に直した
- `Shared_Assets/Japanese_Writing_Rules.md` 漢語を一律に言い換える表を廃止し、文脈で選ぶ形にした
- `.claude/skills/skill-writing/SKILL.md` 12の問いの3番を、期限からではなく、受け取る人に必要な精度から逆算する形にした

## 0.2.0 - 2026-09-19

**AIオフィスのバックアップ（進捗の表の17・18）を必須にしました。** Windows では、パソコンに最初から入っている
OneDrive へ1時間ごとに写す方法を既定にしました（Google Cloud での鍵の発行が要りません）。

**入れたあとに行うこと**：0.1.0 で17と18を見送った方（進捗の表の17・18が「保留」の方）は、
「オフィス開設の続きをやりましょう」とお伝えください。17から始まります。
17と18がすでに「済」の方（第9号の方法など）は、そのままお使いいただけます。止まったことを知らせる仕組み
（下の「追加」の1行目）は、Claude Code に「バックアップの見張りを足して」とお伝えいただくと作れます
（成功した日時を記録する処理を、先にバックアップのプログラムへ足します）。

**1件ずつ入れるときの注意**：`.claude/skills/office-setup/SKILL.md` と `.claude/rules/safety.md` は、一緒に入れてください。
片方だけ入れると、バックアップを勧めるかどうかの指示が食い違います。

**どんな穴を塞ぐ変更か**：Claude Code には、確認を求めずに実行する削除があります（`auto` モードで
頼まれた削除、「編集を受け入れる」モードでの作業フォルダ内の削除）。Windows の PowerShell で消したものは
ごみ箱を通りません。変更履歴（Git）の記録は AIオフィスのフォルダの中にあるので、フォルダごと消えたとき
やパソコンが故障したときには戻せません。パソコンの外の写しが、その穴を塞ぎます。

### 追加

- `.claude/skills/office-setup/SKILL.md` バックアップが24時間以上止まったら、セッションの最初に Claude Code が知らせる仕組み（見張り）の作り方
- `.claude/skills/office-upkeep/SKILL.md` 月に一度の見直しに、バックアップが動いているかの確認

### 変更

- `.claude/skills/office-setup/SKILL.md` 17・18を必須に。Windows の既定を OneDrive へ1時間ごとに写す方法に（写しは消さずに足していく・決まった名前の鍵のファイルと変更履歴の記録は写さない・黒い画面を出さない起動のしかた・電池で動いているときも止めない登録のしかた）。AIオフィスがすでに OneDrive の中にあるときの扱いも追加
- `.claude/skills/office-setup/SKILL.md` フックのコマンドのパスを `/` で書く注意（`\` で書くと Git の入ったパソコンで黙って失敗する）
- `.claude/rules/safety.md` バックアップを必須に。見張りの警告が来たら、最初の返事で社長に伝える。バックアップで戻せる範囲の説明を、1時間ごとの方法に合わせて直す
- `README.md` 17・18の説明を、必須・OneDrive の方法に合わせて書き直し
- `SETUP_STATUS.md` 17・18の「済」の条件を書き直し（見送りを廃止）
- `Programs/README.md` バックアップのプログラムの説明を書き直し
- `START_HERE.md` 17・18を見送った場合の記述を削除
- `CLAUDE.md`・`.claude/settings-template.jsonc` 「第9号のバックアップ」を「進捗の表の⑰のバックアップ」に

### 修正

- `.gitignore` 名前が `.env` で終わるファイル（`*.env`）を、変更履歴に残さない対象に追加（鍵が記録される抜けがありました）
- `.gitignore` バックアップが1時間ごとに書き換える記録を、変更履歴に残さない対象に追加

## 0.1.0 - 2026-09-17

最初のバージョン。ニュースレター「一人社長とAI従業員」の準備編（第2号〜第12号）で
作ってきたファイルを、一式まとめたものです。

**配り方**：`AI_Office.zip` を展開してできる `AI_Office` フォルダが、
**そのままAIオフィスです。** 中身を別の場所へ置き直す作業はありません。
すでにご自分で環境を作っている方は、`AI_Office` をご自分のフォルダの中へ入れて、
比較する形で使います（手順はREADMEの「第2部　すでに Claude Code を使っている方」）。

### 追加

- `README.md` 最初に読む1枚
- `START_HERE.md` 開設の進め方（AI従業員に読ませる台本）
- `SETUP_STATUS.md` 開設の進捗を記録する表
- `CLAUDE.md` 就業規則。会社ごとの欄は空いています
- `.gitignore` 変更履歴に残さないものの一覧（第9号）
- `.claude/settings.json` 禁止事項。どの会社でも禁止してよいものだけ、最初から効いています（第8号）
- `.claude/settings-template.jsonc` 会社に合わせた禁止事項を足すときの見本（第8号）
- `.claude/OFFICE_KIT_VERSION` 手元のバージョン番号。更新確認に使います
- `.claude/rules/completion.md` 仕事が終わったときの報告のルール
- `.claude/rules/work-style.md` 仕事の進め方のルールと、ルールの保存場所の表
- `.claude/rules/safety.md` 安全のルールと、外に出す前の確認
- `.claude/skills/office-setup/SKILL.md` 開設の進行役
- `.claude/skills/skill-writing/SKILL.md` AI従業員の増やし方
- `.claude/skills/fact-check/SKILL.md` 数字や仕様の裏の取り方
- `.claude/skills/kit-update/SKILL.md` このキットの更新確認
- `.claude/skills/connect-check/SKILL.md` 外部サービスとつなぐ前の点検
- `.claude/skills/automation-setup/SKILL.md` 自動で動く処理の工程
- `.claude/skills/office-upkeep/SKILL.md` ルールと記録の手入れ
- `.claude/skills/big-task/SKILL.md` 大きな作業の工程
- `.claude/skills/program-writing/SKILL.md` プログラムの書き方
- `Shared_Assets/README.md` 共通資料の使い方とロゴの保存場所
- `Shared_Assets/Company_Info.md` 会社の基本情報（記入用）
- `Shared_Assets/Design_Rules.md` デザイン仕様（記入用）
- `Shared_Assets/Japanese_Writing_Rules.md` 文章の書き方（①読みやすい日本語 ②専門用語の出し方 ③AIっぽさを避ける ④あなたの書き方＝空欄）
- `Shared_Assets/Document_Templates/README.md` 請求書などのテンプレートの保存場所
- `Programs/README.md` プログラムの保存場所（第9号）
- `LICENSE` ライセンスと無保証について
- `VERSION` バージョン番号
- `CHANGELOG.md` このファイル
