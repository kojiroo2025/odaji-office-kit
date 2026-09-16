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

## 0.1.0 - 未リリース

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
