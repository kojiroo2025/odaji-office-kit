# 変更履歴

オフィス開設キットの変更を、新しいバージョンから順に記録します。

このファイルは、キットに入っている「更新確認」（`.claude/skills/kit-update/`）が
機械的に読みます。次の3つの決まりを守って書きます。

1. 見出しは `## バージョン番号 - 日付` の形にする（つなぎは半角のハイフン）。日付は `YYYY-MM-DD`
2. 新しいバージョンほど上に書く
3. 各バージョンの中は「追加」「変更」「修正」「削除」の見出しに分け、1行に1件だけ書く

バージョン番号の上げ方
  一番右の数字（0.1.**0**）＝ 誤字や説明の書き直し。手元に入れなくても困りません
  真ん中の数字（0.**1**.0）＝ ファイルの追加や内容の変更。入れる価値があります
  一番左の数字（**0**.1.0）＝ 使い方が変わる大きな改訂。入れる前に説明を読んでください

---

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
- `.claude/rules/completion.md` 仕事が終わったときの報告の決まり
- `.claude/rules/work-style.md` 仕事の進め方の決まりと、ルールの保存場所の表
- `.claude/rules/safety.md` 安全の決まりと、外に出す前の確認
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
