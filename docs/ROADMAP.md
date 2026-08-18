# ASD Roadmap

- Version: 22
- Last Reviewed: 2026-08-18
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

**ASD Operations: Daily Initialization Workflow v2**（[asd#32](https://github.com/ga7ming3249/asd/issues/32)）— **Completed / Closed**（`2026-08-01T06:31:41Z`）

Global Architect初期化フローをSession Lifecycle（Session Creation → Workspace Validation → Architecture Initialization → Execution → Finalization）として標準化。GitHub Repositoryを`docs/asd-state.md` / `docs/figma-os-state.md` / `docs/ROADMAP.md`のCanonical Primary Sourceとし、Vision Ownerによる毎朝のCanonical Documentsアップロード運用を廃止。GitHub AuditはGlobal Architectの責務、Local Synchronization Audit（読み取り専用、自動修正なし）はClaude Codeの責務として分離。Daily SessionはASD Project内で`ASD-YYMMDD`命名のチャットとして開始する。`asd-prompt-library.html`（Canonical管理: [`ga7ming3249/asd-operations`](https://github.com/ga7ming3249/asd-operations) `main`ブランチ、2026-08-07時点でP0/P1/P2 **Completed / Accepted**、検証済みCommit `f3837c992bb7dea82c859c67454e1372683a3279`）はIssue-scoped Architectレビューで既にAccepted。2026-08-01、Canonical Documentation Synchronizationにより`docs/asd-state.md`・`docs/ROADMAP.md`へ反映し、同日Issue-scoped Architectレビューで`Accepted`、Publisherにより`Close`済み。後続Issueの新規作成は不要。

**Type Polish Utility Ownership Canonical Decision**（[figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3)）— **Completed / Accepted / Closed**（`2026-08-18T05:03:24Z`）

Issue-scoped Architect final result: Accepted。Canonical manual-adjustment owner: **Type Adjuster**（Scale / Baseline / Tracking）。Type Polish既存Utilityは**Legacy Compatibility Capability Pending Migration/Removal**へ再分類——即時削除は引き続き禁止。Type Polish Freezeの例外は、以下Migration Trackで扱うUtility deprecation/removal migrationに限定し、他のType Polish変更を許可しない。**本Closeはimplementation authorizationではない**——figma-os#3のClose単独ではType Polish Utility削除を許可しない。Follow-up chainおよびNext Architecture Dependency（figma-os#12）はNext節「Type Polish Utility Ownership — Migration Track」を参照。Architecture Decision comment: [figma-os#3#issuecomment-5323799447](https://github.com/ga7ming3249/figma-os/issues/3#issuecomment-5323799447)。

**Type Polish / Type Adjuster User Guide**（[figma-os#10](https://github.com/ga7ming3249/figma-os/issues/10)）— **Completed / Accepted / Closed**（2026-08-18）

Issue-scoped Architect final result: Accepted。Completion comment: [figma-os#10#issuecomment-5327103969](https://github.com/ga7ming3249/figma-os/issues/10#issuecomment-5327103969)。Canonical User Guideを`docs/user-guides/`配下のMarkdown（`type-polish.md` / `type-adjuster.md` / `type-polish-type-adjuster-workflow.md` / `glossary.md` / `faq.md`）として`ga7ming3249/figma-os`へ納品。`README.md` / `PLUGINS.md` / 両プラグインの`README.md`からNavigation追加。Documentation-onlyのdiff（Source/tests/`docs/shared/handoff-schema.md`は無変更）。Accepted commit `423e6054b8c20a8c6e4b81cde38c34fb6bca3daf`（初版）→ `d3ebb1c33ea3d4c4824504309ffe349693556a92`（Accepted修正: Type Polishのzero-mutation範囲はDocument Contentのみであり、Local Fix Handoffの共有メタデータ書き込みを除外することを明確化）——`d3ebb1c...`が最終Accepted `figma-os/main` HEAD。figma-os#3のCanonical Ownership Decisionを反映: Scale/Baseline/TrackingのCanonical OwnerはType Adjuster、Type Polish自身のUtilityパネルはLegacy Compatibility Capability Pending Migration/Removalとして記述し、現Ownerとしては説明しない。Follow-up candidate（`docs/shared/handoff-schema.md`のGate 4/5記述drift、`type-adjuster/HISTORY.md`のGate 3/4/5履歴欠落、Type Adjusterのtest runner整備）はfigma-os#10のscopeでは未実装のまま記録。Presentation/Distribution層（Dropbox向けoffline HTML化）の別Issueが`ga7ming3249/figma-os`に登録済みだが、今回のState Update DecisionによりそのIssue登録自体はこの同期の対象外。

**ASD Operations: Standardize Issue Completion Authority and Operation Directives**（[asd#33](https://github.com/ga7ming3249/asd/issues/33)）— Open / Architecture Improvement

Review Decision、Completion、GitHub Operationの分離を標準化するIssue。背景: asd#31のKB-0005 Architecture Reviewコメント投稿直後（5秒後）に親Issue（asd#31）がGitHub上でCloseされ、この操作はPublisher未検証だった（GitHub Timeline/Events APIで確認済み、Reopenイベントは存在しない）。2026-08-05のNightly Canonical Synchronizationで、asd#31のKnowledge Track成果物（KB-0004/KB-0005）がRepository未登録であること、および`figma-os/main`上の未分類コミット（`5464a78`、PRなし、Architecture Review記録未確認）が追加で判明し、本Issueが扱う問題の実例として記録された（詳細: [asd#31 Publisher Verification](https://github.com/ga7ming3249/asd/issues/31#issuecomment-5190980016)、[asd#33 Correction Comment](https://github.com/ga7ming3249/asd/issues/33#issuecomment-5190983450)）。Deliverables: Completion Authority Matrix、Issue Lifecycle Definition、Review Vocabulary Standard、Operation Directive Template、Handoff Template更新、Prompt Library更新案。

---

# Next

Architect-Accepted execution order (2026-07-29 Nightly Canonical State Synchronization): 1) Type Polish / Type Adjuster User Guide, 2) figma-os#3, 3) Japanese Horizontal Typography Analysis Track (see Future).

**Status update (2026-08-05)**: Item 1 (figma-os#10) and item 2 (figma-os#3) are unaffected and remain the current order. Item 3 (asd#31) is Closed as of 2026-08-05 — see Future for its status update; any further Horizontal Typography work (Gate 1 and beyond) requires a new Issue and explicit Architecture Authorization.

**Status update (2026-08-07)**: Repository Evidence Classification of commit `5464a78` (recorded on asd#31 and asd#33) is resolved via [asd#34](https://github.com/ga7ming3249/asd/issues/34) — **Experimental**, **Accepted Commit: No**; see Future for detail.

**Status update (2026-08-18)**: Item 2 (figma-os#3) is **Completed / Accepted / Closed** — see Now above. It is superseded in this execution order by [figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12) (Plain-node Manual Adjustment Strategy), the Next Architecture Dependency; see "Type Polish Utility Ownership — Migration Track" below. Item 1 (figma-os#10) is unaffected but its scope must now incorporate the figma-os#3 canonical ownership decision, coordinated with figma-os#14 to avoid overlap. Item 3 (asd#31) remains Closed as recorded 2026-08-05.

**Status update (2026-08-18, second sync)**: Item 1 (figma-os#10, Type Polish / Type Adjuster User Guide) is now **Completed / Accepted / Closed** — see "Now" above. It no longer occupies a Next-section execution-order slot; [figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12) (Plain-node Manual Adjustment Strategy, "Type Polish Utility Ownership — Migration Track" below) is the current Recommended First Action / Next Architecture Dependency. A separate Presentation/Distribution-layer Issue (offline HTML copy of the accepted User Guide for Dropbox viewing) was registered in `ga7ming3249/figma-os`; per explicit State Update Decision, that Issue's registration is not itself tracked in this Next section.

**Type Polish Utility Ownership — Migration Track**（[figma-os#3](https://github.com/ga7ming3249/figma-os/issues/3) Completed 2026-08-18 の follow-up chain）

figma-os#3のCanonical Ownership Decision（Type Adjusterがmanual adjustment [Scale/Baseline/Tracking] のcanonical owner、Type Polish Utilityはlegacy compatibility capability pending migration/removal、即時削除禁止）を受けた4件のfollow-up Issue。すべて`ga7ming3249/figma-os`にOpenで登録済み。

- [figma-os#12](https://github.com/ga7ming3249/figma-os/issues/12) — Plain-node Manual Adjustment Strategy。**Next Architecture Dependency**。plain/ungenerated TextNodeへのmanual adjustment（Scale/Baseline/Tracking）をMaintain/Replace/Discontinueのいずれにするか決定する。実装ではない。
- [figma-os#13](https://github.com/ga7ming3249/figma-os/issues/13) — Manual Adjustment Migration。**Contingent**——#12が「Type Adjuster側の対応が必要」と判断した場合にのみ必要になるimplementation Issue。無条件の実装予定として扱わない。
- [figma-os#14](https://github.com/ga7ming3249/figma-os/issues/14) — Utility Ownership Documentation Migration。`type-polish/README.md` / `type-adjuster/README.md` / ROADMAP等を更新。figma-os#10（User Guide）は2026-08-18にCompleted（commit `d3ebb1c...`）——#14はこれをsync inputとして扱い、内容を再定義しない。
- [figma-os#15](https://github.com/ga7ming3249/figma-os/issues/15) — Utility Deprecation / Removal。**Blocked**——#12・#13（該当する場合）・#14、およびregression/Desktop verification完了まで着手しない。**前倒ししない。**

Dependency order: #12 → #13（該当する場合） → #14 → #15。Type Polish Freezeの例外はこのMigration Trackに限定され、他のType Polish変更を許可しない。本Trackの登録自体はimplementation authorizationではない。

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
* Utility ownership-changing implementation is blocked until the figma-os#3 follow-up migration chain (figma-os#12 → #13 if applicable → #14 → #15) completes

Architect-Accepted (2026-07-29). New Gate 0–Gate 5 capability track for Type Polish, distinct from and not incomplete work of the completed Japanese Vertical — Standard Gate 5 (see Now above). Gate 0 Knowledge Collection may begin before figma-os#3 is resolved; it is not the current first implementation priority (see Next above for the Architect-Accepted execution order).

**Status update (2026-08-18)**: figma-os#3 is now Completed / Accepted / Closed (see Now above). The blocking condition above is superseded — it is no longer gated on figma-os#3 itself, but on the figma-os#3 follow-up migration chain (figma-os#12 → #13 if applicable → #14 → #15, see Next → "Type Polish Utility Ownership — Migration Track"). asd#31 remains Closed (2026-08-05); any future Horizontal Typography work still requires a new Issue and explicit Architecture Authorization, independent of this update.

**Status update (2026-08-05 Nightly Canonical Synchronization)**: asd#31 is **Closed** (`2026-08-05T10:08:05Z` — GitHub's issue timeline shows exactly one close event and no reopen event; the original close was not Publisher-verified). This entry is no longer an active in-progress Future Parent Issue. Repository verification found: KB-0001–KB-0003 registered in `figma-os`; **KB-0004 and KB-0005 are Remote Registration Pending** (no artifact found for either — no repository file, no git history, and for KB-0004 no Issue comment either); no Accepted Commit SHA exists for either. Separately, commit `5464a78` on `figma-os/main` (2026-08-01, pushed directly with no PR) implements a read-only Horizontal Analysis Profile per its own commit message; no Architecture Review record for it has been identified — recorded as **Repository Evidence Identified, Architecture Classification Pending**, not inferred to satisfy Gate 2 or Gate 3, and escalated for Global Architect review. Gate 1 and beyond are **Future Candidates requiring a new Issue**, contingent on that classification. Full detail: [asd#31 Publisher Verification](https://github.com/ga7ming3249/asd/issues/31#issuecomment-5190980016), [asd#33 correction](https://github.com/ga7ming3249/asd/issues/33#issuecomment-5190983450). The original Architect-Accepted description above is preserved as the historical record as of 2026-07-29 and is not rewritten.

**Status update (2026-08-07)**: [asd#34](https://github.com/ga7ming3249/asd/issues/34) (Review and Classify Repository Evidence Commit 5464a78) is **Closed / Completed**. Commit `5464a78`'s Architecture Classification is resolved: **Experimental**, **Accepted Commit: No**, Canonical Gate Acceptance **Gate 0 only** (Gate 1 / Gate 2 / Gate 3 Acceptance: **Not established**), no Rule Promotion, no Utility Ownership change, Freeze Compliance **Not established**. Gate 1 and beyond remain **Future Candidates requiring a new Issue and explicit Architecture Authorization** — this classification does not itself open or authorize further Horizontal Typography implementation work. **KB-0004 / KB-0005 Remote Registration Pending is unaffected and remains outstanding.** Publication commit: [`031887cbf1b65336682212f13df3d609ce46267a`](https://github.com/ga7ming3249/figma-os/commit/031887cbf1b65336682212f13df3d609ce46267a).

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
