# ASD Roadmap

- Version: 17
- Last Reviewed: 2026-07-29
- Status: Active

---

# Purpose

ASD全体の将来計画を扱う。過去の経緯は `docs/ASD_HISTORY.md`、現在の状態は `docs/asd-state.md` を参照。

Documentation Architecture v1.0（[#12](https://github.com/ga7ming3249/asd/issues/12)）に基づき、構成は **Now / Next / Future / Icebox** のみ。

この文書はASDプロセス（ガバナンス・ドキュメント整備）とfigma-osプロダクトの優先順位の両方を扱う。プロダクト側の詳細な状態（Plugin State・Product Health等）は引き続き `docs/figma-os-state.md` を正本とし、この文書には統合された優先順位のみを記す。両者の集約方法（並存か置き換えか）はDocumentation Migration完了時にArchitecture Reviewで確定する。

---

# Now

**Issue #30 — Japanese Vertical — Standard Implementation**（Architecture-gated scoped exception）— Completed

Gate 4 — Safe Local Fix MVP: Completed / Formally Closed

Gate 5 — Desktop Acceptance: Primary Issue [figma-os#6](https://github.com/ga7ming3249/figma-os/issues/6) is **Accepted / Completed / Closed** (`2026-07-29T11:45:25Z` / 2026-07-29 20:45:25 JST). PR [figma-os#8](https://github.com/ga7ming3249/figma-os/pull/8) **Merged** to `figma-os/main` (base `main`, 7 commits, merged `2026-07-29T11:44:32Z`) — accepted implementation commit `9253ce8ce46dbd02225f9bfa73019f4662f575de`, merge commit `d3abd4f46ce89240a22a467bbbf712f4c5e10628`. Verified: Type Adjuster full suite 278/278 PASS, Scale UI tests 109/109 PASS, Gate 4 Local Fix tests 163/163 PASS, G5-DEF-002 generated marker tests 6/6 PASS, Type Polish full suite 165/165 PASS, both builds PASS, Rebased-head Desktop Acceptance 7/7 PASS.

Accepted baseline: `dc6361157345ebb8b17264f63aef8fa0e265c5eb` on `feature/issue-30-gate4-safe-local-fix`, now merged to `figma-os/main` via the Gate 5 accepted implementation commit above.

**Integration risk resolved**: figma-os#2's merged `main` lineage and the Gate 4/5 feature lineage (`dc636115...`) were combined via PR figma-os#8 (base `main`, merged 2026-07-29).

Japanese Vertical — Standard / Safe Local Fix MVP Gate 0 through Gate 5 are complete. [asd#30](https://github.com/ga7ming3249/asd/issues/30) is **Closed / Completed** as of this Canonical State Synchronization. Generic Vertical Split Reset and Reset button visual state are not Gate 5 defects or unfinished items; they remain Post-Gate-5 Follow-up Candidates only, not created as new Issues by this synchronization and not automatically promoted to the Committed Roadmap.

**Component Package: production trial & polish**

PR #1マージ（2026-07-16）済み。実運用を通じて成熟させ、改善点は新規Issueとして収集する段階。

**Reference Assistant: Daily Preview operation**（[reference-assistant#1](https://github.com/ga7ming3249/reference-assistant/issues/1)、P1、Product Repositoryにて実施）

2026-07-23、Vision Owner承認によりasd#4からSuccessor Issue方式で移管。実プロジェクトでの継続利用を通じて摩擦を発見し、証跡ベースの改善バックログを構築する。最初の実践目標は、実際の `collect → select → deliverable` サイクルを1件完了すること。[reference-assistant#5](https://github.com/ga7ming3249/reference-assistant/issues/5) は2026-07-25にCompleted / Accepted / Closedとなり、Daily Preview再開の主要なSafety Blockerは解消済み。ただしDaily Preview再開自体はこの同期で自動確定しておらず、別途Owner-controlledな運用判断に従う。

**Reference Assistant: Japan-first Collection Gate and Always-on Content Safety**（[reference-assistant#5](https://github.com/ga7ming3249/reference-assistant/issues/5)）— Delivered

2026-07-25、**Completed / Delivered**。PR [reference-assistant#6](https://github.com/ga7ming3249/reference-assistant/pull/6) はMerged / Closed（accepted implementation commit `dee933fd2f934314b628f3213025ff8e6efd5bfa`、merge commit `672cada474240909729d876a882eb455ad44e103`）。Japan-first Collection Gate（JPを既定Remote SEARCH市場とする）、Shared Fail Closed Content Safety Boundary（Dedup前評価・Always-on・無効化不可）、Human-reviewed Promotion Workflow（eligibleな`indeterminate_safety`限定、Existing Ingest Pipelineへ差し戻し）の3点をDeliveredとして記録する。violence/gore/weapons等を含むComprehensive Safety Classification ExpansionはFuture Workであり、Issue #5の未完了scopeではない（別Issue化およびArchitecture Reviewなしに着手しない）。

**Reference Assistant: Post-migration Cleanup**（[reference-assistant#7](https://github.com/ga7ming3249/reference-assistant/issues/7)、Maintenance backlog）

Dropboxベースの開発ディレクトリへの移行後のクリーンアップ（旧`~/Developer/reference-assistant`のアーカイブ、ドキュメント・IDE設定・shell設定・ローカル自動化の参照更新）。reference-assistant#5（Completed）とは独立した低優先度Maintenance Issueであり、Issue #5の未完了作業ではない。

---

# Next

Architect-Accepted execution order (2026-07-29 Nightly Canonical State Synchronization): 1) Type Polish / Type Adjuster User Guide, 2) figma-os#3, 3) Japanese Horizontal Typography Analysis Track (see Future).

**Type Polish / Type Adjuster User Guide**

* Issue: `ga7ming3249/figma-os#10`
* Priority: P1
* Type: Documentation / UX Enablement
* Canonical source: Markdown in the figma-os repository
* Scope: User Guide, workflow, glossary, FAQ
* Out of scope: Architecture Guide, Developer Guide, UI redesign

Architect-Accepted (2026-07-29). Reason: current functionality exists but lacks canonical user-facing documentation. Not incomplete Gate 5 work — Gate 5 (Desktop Acceptance) for Japanese Vertical — Standard is Completed (see Now above).

**Type Polish Utility ownership consolidation decision**（[figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3)、Medium）

Product Architecture Decision（実装ではない）。figma-os#2完了後にUtility削除を検討する前提。Issue #30 Gate 4への依存なし。

**Color Inventory: Generate Inventory Page**

v1 core（Generate / Raw Colors Workbench / Promote）は実運用検証中。Inventoryページ生成がProduction昇格に向けた次の増分。

**Reference Assistant: Library Location Selection and Safe Relocation architecture design**（[reference-assistant#3](https://github.com/ga7ming3249/reference-assistant/issues/3)、P2）

GUIやリロケーション実装に先立ち、Library識別・選択・安全な移動モデルを定義するArchitecture Issue。

---

# Future

**Japanese Horizontal Typography Analysis Track**

* Issue: `ga7ming3249/asd#31`
* Priority: P2
* Type: Parent Coordination Issue
* Begins with Gate 0 Knowledge Collection
* Production capability only after Gate 5 Acceptance
* Utility ownership-changing implementation is blocked until figma-os#3 is resolved

Architect-Accepted (2026-07-29). New Gate 0–Gate 5 capability track for Type Polish, distinct from and not incomplete work of the completed Japanese Vertical — Standard Gate 5 (see Now above). Gate 0 Knowledge Collection may begin before figma-os#3 is resolved; it is not the current first implementation priority (see Next above for the Architect-Accepted execution order).

**Type Inventory: 多行テキスト対応**（[figma-os#4](https://github.com/ga7ming3249/figma-os/issues/4)、P3・Backlog）

明確なワークアラウンドが存在し優先度は低い。Guide Stamp Canvas Guides完了により前提条件は解消済み。2026-07-22、Repository Issue Ownership Reorganizationによりasd#3からfigma-osへ移管。

**Composer / Design Style Sheet v2 再設計**

Foundation（Color Inventory / Component Package）が実運用で十分に成熟してから着手。DSS ColorsセクションとColor Inventoryの紙面生成の役割分担再定義が前提の宿題として残っている。

**Reference Assistant: Future Candidates（証跡駆動）**

常時稼働のContent Safety Gate自体は[reference-assistant#5](https://github.com/ga7ming3249/reference-assistant/issues/5)として2026-07-25にDelivered済み（Completed / Accepted / Closed）。Futureに残るComprehensive Safety Classification Expansionは、violence / gore / weapons coverage、contextual harm、safe classification evaluation、reviewer authentication and permissions、authenticity and provenanceなど、Issue #5の範囲を超える発展項目に限定する。これらはIssue #5のIncomplete Scopeではなく、別Issue化およびArchitecture Reviewなしに実装開始しない。GUI、Tag、Flow、Export/Figma、Presentationは、Daily Preview評価による証跡と前提となるArchitecture決定が揃うまでコミットしない。

---

# Icebox

現時点で該当なし。

---

# Notes

- 各項目の詳細な理由・前提条件は、プロダクト側は `docs/figma-os-state.md` の Recommended Next Priorities、ASDプロセス側は各Issueを参照。
- 優先順位はProduct Stateの更新に応じて変わり得る（コミットメントではなく推奨）。
