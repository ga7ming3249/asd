# ASD Roadmap

- Version: 14
- Last Reviewed: 2026-07-25
- Status: Active

---

# Purpose

ASD全体の将来計画を扱う。過去の経緯は `docs/ASD_HISTORY.md`、現在の状態は `docs/asd-state.md` を参照。

Documentation Architecture v1.0（[#12](https://github.com/ga7ming3249/asd/issues/12)）に基づき、構成は **Now / Next / Future / Icebox** のみ。

この文書はASDプロセス（ガバナンス・ドキュメント整備）とfigma-osプロダクトの優先順位の両方を扱う。プロダクト側の詳細な状態（Plugin State・Product Health等）は引き続き `docs/figma-os-state.md` を正本とし、この文書には統合された優先順位のみを記す。両者の集約方法（並存か置き換えか）はDocumentation Migration完了時にArchitecture Reviewで確定する。

---

# Now

**Issue #30 — Japanese Vertical — Standard Implementation**（Architecture-gated scoped exception）— next implementation target

Gate 4 — Safe Local Fix MVP: Completed / Formally Closed

Gate 5 — Desktop Acceptance: Primary Issue [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6) authorized by Architect verification. Desktop Acceptance has not started. The Owner Priority Hold (2026-07-23) was conditioned on figma-os#2, which is now Completed / Accepted / Closed (2026-07-24) — but per existing policy Gate 5 resumes only after an explicit Owner priority decision, which is not yet given. Gate 5 remains Open / Owner Priority Hold.

Required baseline: `dc6361157345ebb8b17264f63aef8fa0e265c5eb` on `feature/issue-30-gate4-safe-local-fix`

Merge status: not merged to `figma-os/main`; verified main is now `2838450c91429e9bc9c312103e0741c64e0068d2` (figma-os#2 merged 2026-07-24) and still does not contain Gate 4

**Integration risk**: figma-os#2's merged `main` lineage and the Gate 4/5 feature lineage (`dc636115...`) still overlap in Type Adjuster. An explicit reconciliation scope is required before combining them; no rebase, cherry-pick, or merge between the lineages is authorized yet.

**Component Package: production trial & polish**

PR #1マージ（2026-07-16）済み。実運用を通じて成熟させ、改善点は新規Issueとして収集する段階。

**Reference Assistant: Daily Preview operation**（[reference-assistant#1](https://github.com/ga7ming3249/reference-assistant/issues/1)、P1、Product Repositoryにて実施）

2026-07-23、Vision Owner承認によりasd#4からSuccessor Issue方式で移管。実プロジェクトでの継続利用を通じて摩擦を発見し、証跡ベースの改善バックログを構築する。最初の実践目標は、実際の `collect → select → deliverable` サイクルを1件完了すること。Daily Previewは、[reference-assistant#5](https://github.com/ga7ming3249/reference-assistant/issues/5) の安全なpromotion経路が確立するまで停止継続。

**Reference Assistant: Japan-first Collection Gate and Always-on Content Safety**（[reference-assistant#5](https://github.com/ga7ming3249/reference-assistant/issues/5)、P1、Daily Preview再開のための安全運用blocker）

Status: Open / In Progress — Review / Validation transition（Accepted・Closedいずれでもない）。Draft PR [reference-assistant#6](https://github.com/ga7ming3249/reference-assistant/pull/6) は引き続きDraft/Open、reviewed commit `541a74e113d8ebe96175228c4627151f3f007e50`。残作業: Acceptance Criteria audit、Manual Live Validation、Independent Technical Review、Architect Review、Vision Owner restart approval。Daily Previewは引き続き停止。Human-reviewed Safety Promotionは推奨案のみでVision Owner未承認、Accepted Architectureとして記録しない。

**Reference Assistant: Post-migration Cleanup**（[reference-assistant#7](https://github.com/ga7ming3249/reference-assistant/issues/7)、Maintenance backlog）

Dropboxベースの開発ディレクトリへの移行後のクリーンアップ（旧`~/Developer/reference-assistant`のアーカイブ、ドキュメント・IDE設定・shell設定・ローカル自動化の参照更新）。reference-assistant#5とは独立したMaintenance Issueであり、**reference-assistant#5の完了をブロックしない**。

---

# Next

**Color Inventory: Generate Inventory Page**

v1 core（Generate / Raw Colors Workbench / Promote）は実運用検証中。Inventoryページ生成がProduction昇格に向けた次の増分。

**Type Polish Utility ownership consolidation decision**（[figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3)、Medium）

Product Architecture Decision（実装ではない）。figma-os#2完了後にUtility削除を検討する前提。Issue #30 Gate 4への依存なし。

**Reference Assistant: Library Location Selection and Safe Relocation architecture design**（[reference-assistant#3](https://github.com/ga7ming3249/reference-assistant/issues/3)、P2）

GUIやリロケーション実装に先立ち、Library識別・選択・安全な移動モデルを定義するArchitecture Issue。

---

# Future

**Type Inventory: 多行テキスト対応**（[figma-os#4](https://github.com/ga7ming3249/figma-os/issues/4)、P3・Backlog）

明確なワークアラウンドが存在し優先度は低い。Guide Stamp Canvas Guides完了により前提条件は解消済み。2026-07-22、Repository Issue Ownership Reorganizationによりasd#3からfigma-osへ移管。

**Composer / Design Style Sheet v2 再設計**

Foundation（Color Inventory / Component Package）が実運用で十分に成熟してから着手。DSS ColorsセクションとColor Inventoryの紙面生成の役割分担再定義が前提の宿題として残っている。

**Reference Assistant: Future Candidates（証跡駆動）**

常時稼働のContent Safety Gate自体は[reference-assistant#5](https://github.com/ga7ming3249/reference-assistant/issues/5)として現在進行中であり、Future候補ではない。Futureに残るSafety関連候補は、外部moderation engineの採用、GUIでの安全性表示、既存Libraryへの遡及scan、汎用的なreview workflowの高度化など、Issue #5の範囲を超える発展項目に限定する。GUI、Tag、Flow、Export/Figma、Presentationは、Daily Preview評価による証跡と前提となるArchitecture決定が揃うまでコミットしない。

---

# Icebox

現時点で該当なし。

---

# Notes

- 各項目の詳細な理由・前提条件は、プロダクト側は `docs/figma-os-state.md` の Recommended Next Priorities、ASDプロセス側は各Issueを参照。
- 優先順位はProduct Stateの更新に応じて変わり得る（コミットメントではなく推奨）。
