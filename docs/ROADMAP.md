# ASD Roadmap

- Version: 1
- Last Reviewed: 2026-07-17
- Status: Active

---

# Purpose

ASD全体の将来計画を扱う。過去の経緯は `docs/ASD_HISTORY.md`、現在の状態は `docs/asd-state.md` を参照。

Documentation Architecture v1.0（[#12](https://github.com/ga7ming3249/asd/issues/12)）に基づき、構成は **Now / Next / Future / Icebox** のみ。

この文書はASDプロセス（ガバナンス・ドキュメント整備）とfigma-osプロダクトの優先順位の両方を扱う。プロダクト側の詳細な状態（Plugin State・Product Health等）は引き続き `docs/figma-os-state.md` を正本とし、この文書には統合された優先順位のみを記す。両者の集約方法（並存か置き換えか）はDocumentation Migration完了時にArchitecture Reviewで確定する。

---

# Now

**Documentation Migration**（[Epic #13](https://github.com/ga7ming3249/asd/issues/13)）

進行中。Migration Order:

1. ✅ `docs/ASD_HISTORY.md`（[#14](https://github.com/ga7ming3249/asd/issues/14)、完了）
2. ✅ `docs/ROADMAP.md`（[#15](https://github.com/ga7ming3249/asd/issues/15)、本ファイル）
3. Type Adjuster Documentation（モデルケース、[#16](https://github.com/ga7ming3249/asd/issues/16)）
4. 残り10プラグイン（[#17](https://github.com/ga7ming3249/asd/issues/17)〜[#26](https://github.com/ga7ming3249/asd/issues/26)）

**Component Package: production trial & polish**

PR #1マージ（2026-07-16）済み。実運用を通じて成熟させ、改善点は新規Issueとして収集する段階。

---

# Next

**Type Adjuster Documentation を除く、残り10プラグインのDocumentation Migration**

Guide Stamp / Instance Checker / Margin Preflight / Pocket Preview / Type Inventory / Status Stamp / Color Inventory / Component Package / Type Polish / Design Style Sheet（Composer）。詳細は各Issue（#17〜#26）参照。

**Color Inventory: Generate Inventory Page**

v1 core（Generate / Raw Colors Workbench / Promote）は実運用検証中。Inventoryページ生成がProduction昇格に向けた次の増分。

---

# Future

**Type Inventory: 多行テキスト対応**（[#3](https://github.com/ga7ming3249/asd/issues/3)、P3・Backlog）

明確なワークアラウンドが存在し優先度は低い。Guide Stamp Canvas Guides完了により前提条件は解消済み。

**Composer / Design Style Sheet v2 再設計**

Foundation（Color Inventory / Component Package）が実運用で十分に成熟してから着手。DSS ColorsセクションとColor Inventoryの紙面生成の役割分担再定義が前提の宿題として残っている。

---

# Icebox

現時点で該当なし。

---

# Notes

- 各項目の詳細な理由・前提条件は、プロダクト側は `docs/figma-os-state.md` の Recommended Next Priorities、ASDプロセス側は各Issueを参照。
- 優先順位はProduct Stateの更新に応じて変わり得る（コミットメントではなく推奨）。
