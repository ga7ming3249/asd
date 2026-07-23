# ASD Roadmap

- Version: 11
- Last Reviewed: 2026-07-23
- Status: Active

---

# Purpose

ASD全体の将来計画を扱う。過去の経緯は `docs/ASD_HISTORY.md`、現在の状態は `docs/asd-state.md` を参照。

Documentation Architecture v1.0（[#12](https://github.com/ga7ming3249/asd/issues/12)）に基づき、構成は **Now / Next / Future / Icebox** のみ。

この文書はASDプロセス（ガバナンス・ドキュメント整備）とfigma-osプロダクトの優先順位の両方を扱う。プロダクト側の詳細な状態（Plugin State・Product Health等）は引き続き `docs/figma-os-state.md` を正本とし、この文書には統合された優先順位のみを記す。両者の集約方法（並存か置き換えか）はDocumentation Migration完了時にArchitecture Reviewで確定する。

---

# Now

**figma-os#2 — Type Adjuster Scale UI synchronization**（Priority 1）

Vision Owner priority decision (2026-07-23): prioritized ahead of Gate 5 Desktop Acceptance.

Phase A (Current Scale Contract and Integration Review): Accepted — corrected report resolved prior blocking findings (2026-07-23).

Scoped implementation authorized, using an isolated worktree outside Dropbox (`/Users/atsushitogami/Developer/figma-os-issue-2-scale-sync`, branch `feature/issue-2-scale-state-sync`).

Baseline: `main@c9def9785e86272c8d21d61f14a500cd8b45793c`. Do not use the unmerged Gate 4 head.

Implementation report must receive Architect Review before any commit, push, PR, or main merge.

**Issue #30 — Japanese Vertical — Standard Implementation**（Architecture-gated scoped exception）

Gate 4 — Safe Local Fix MVP: Completed / Formally Closed

Gate 5 — Desktop Acceptance: Primary Issue [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6) authorized by Architect verification. Desktop Acceptance has not started and is on **Owner Priority Hold** (2026-07-23), pending completion of figma-os#2. Resumes only after an explicit Owner priority decision.

Required baseline: `dc6361157345ebb8b17264f63aef8fa0e265c5eb` on `feature/issue-30-gate4-safe-local-fix`

Merge status: not merged to `figma-os/main`; verified main remains `c9def9785e86272c8d21d61f14a500cd8b45793c`

**Integration risk**: figma-os#2's `main` lineage and the Gate 4/5 feature lineage (`dc636115...`) overlap in Type Adjuster. An explicit reconciliation scope is required before combining them; no rebase, cherry-pick, or merge between the lineages is authorized yet.

**Component Package: production trial & polish**

PR #1マージ（2026-07-16）済み。実運用を通じて成熟させ、改善点は新規Issueとして収集する段階。

**Reference Assistant: Daily Preview operation**（[reference-assistant#1](https://github.com/ga7ming3249/reference-assistant/issues/1)、P1、Product Repositoryにて実施）

2026-07-23、Vision Owner承認によりasd#4からSuccessor Issue方式で移管。実プロジェクトでの継続利用を通じて摩擦を発見し、証跡ベースの改善バックログを構築する。最初の実践目標は、実際の `collect → select → deliverable` サイクルを1件完了すること。

---

# Next

**Color Inventory: Generate Inventory Page**

v1 core（Generate / Raw Colors Workbench / Promote）は実運用検証中。Inventoryページ生成がProduction昇格に向けた次の増分。

**Type Polish Utility ownership consolidation decision**（[figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3)、Medium）

Product Architecture Decision（実装ではない）。figma-os#2完了後にUtility削除を検討する前提。Issue #30 Gate 4への依存なし。

**Reference Assistant: Daily Operation Guide**（[reference-assistant#2](https://github.com/ga7ming3249/reference-assistant/issues/2)、P2）

2026-07-23、Vision Owner承認によりasd#6からSuccessor Issue方式で移管。`docs/daily-operation-guide.md` を作成し、日常運用手順を標準化する。

**Reference Assistant: Library Location Selection and Safe Relocation architecture design**（[reference-assistant#3](https://github.com/ga7ming3249/reference-assistant/issues/3)、P2）

GUIやリロケーション実装に先立ち、Library識別・選択・安全な移動モデルを定義するArchitecture Issue。

---

# Future

**Type Inventory: 多行テキスト対応**（[figma-os#4](https://github.com/ga7ming3249/figma-os/issues/4)、P3・Backlog）

明確なワークアラウンドが存在し優先度は低い。Guide Stamp Canvas Guides完了により前提条件は解消済み。2026-07-22、Repository Issue Ownership Reorganizationによりasd#3からfigma-osへ移管。

**Composer / Design Style Sheet v2 再設計**

Foundation（Color Inventory / Component Package）が実運用で十分に成熟してから着手。DSS ColorsセクションとColor Inventoryの紙面生成の役割分担再定義が前提の宿題として残っている。

**Reference Assistant: Future Candidates（証跡駆動）**

GUI、Relevance/Safety、Tag、Flow、Export/Figma、Presentationは、Daily Preview評価による証跡と前提となるArchitecture決定が揃うまでコミットしない。

---

# Icebox

現時点で該当なし。

---

# Notes

- 各項目の詳細な理由・前提条件は、プロダクト側は `docs/figma-os-state.md` の Recommended Next Priorities、ASDプロセス側は各Issueを参照。
- 優先順位はProduct Stateの更新に応じて変わり得る（コミットメントではなく推奨）。
