# ASD Issues #17–#24 — Architecture Review Bundle

- Date: 2026-07-22
- Purpose: `asd#17`–`asd#24`（Documentation Migration: 各Plugin）のArchitecture Review判断材料。**このBundleはEvidence整理のみであり、レビューコメント投稿・Accepted判定・Closeは行っていません。**
- Trigger: Phase 1棚卸しで検出した不整合 — `docs/asd-state.md` は「All 13 child Issues (#14–#26) are closed and Approved」と記載しているが、GitHub実態では `#17`–`#24` の8件はOpenのまま。
- Common Structure: 全8件とも Issueは同一テンプレート（Parent Epic #13 / Objective / Scope / Related ASD Issues / Source Material / Design Decisions・Rejected Ideas / **Close Criteria**）を使用。Close Criteriaは共通して次の4項目：
  1. `figma-os/<plugin>/HISTORY.md` 作成
  2. `figma-os/<plugin>/ROADMAP.md` 作成
  3. チャット履歴に存在する設計知識のGitHub移行完了
  4. **Architecture Review 承認**

CCが確認できたのは1–3の客観的事実（ファイル存在・Commit到達可能性）のみです。4（Architecture Review 承認）はCCが判定できる範囲外であり、全8件について**Architect側の承認コメントが未確認**です。

---

## #17 — Documentation Migration: Guide Stamp Documentation

| Field | Content |
|---|---|
| Issue | [#17](https://github.com/ga7ming3249/asd/issues/17) — Documentation Migration: Guide Stamp Documentation |
| Current Status | Open |
| Deliverable | `figma-os/guide-stamp/HISTORY.md`, `figma-os/guide-stamp/ROADMAP.md` |
| Completion Report | https://github.com/ga7ming3249/asd/issues/17#issuecomment-5001839722 — HISTORY.md/ROADMAP.md作成完了、Development History（初期実装→Auto Layoutズレ修正→Canvas Guide追加→round2()除去）記録済みと報告 |
| Commit Evidence | `0e63c3f32d92ba28c9216cd12072698bc1a0317f` — "docs(guide-stamp): add HISTORY.md and ROADMAP.md"（2026-07-17T10:01:21Z） |
| Acceptance Criteria (Close Criteria) | ① HISTORY.md作成 — Evidence確認済み／② ROADMAP.md作成 — Evidence確認済み／③ 設計知識移行 — Completion Report記載内容で確認可能／④ Architecture Review承認 — **未確認** |
| Canonical Location | `figma-os/guide-stamp/HISTORY.md`, `figma-os/guide-stamp/ROADMAP.md`（両ファイルの存在をGitHub API経由で確認済み） |
| Remote Verification | commit `0e63c3f` は `origin/main` の祖先（`main`からの`compare`で`ahead`、到達可能）と確認済み |
| Missing Evidence | Completion Report（issuecomment-5001839722）に対するArchitect側の承認コメントが見つからない（Issueの最終コメントがCompletion Report自体） |
| CC Recommendation | Ready for Architect Review |

---

## #18 — Documentation Migration: Instance Checker Documentation

| Field | Content |
|---|---|
| Issue | [#18](https://github.com/ga7ming3249/asd/issues/18) |
| Current Status | Open |
| Deliverable | `figma-os/instance-checker/HISTORY.md`, `ROADMAP.md` |
| Completion Report | https://github.com/ga7ming3249/asd/issues/18#issuecomment-5001867461 — Design Decisions記録、pre-ASD変更として asd#10監査済みの旨をHISTORY.mdに明記 |
| Commit Evidence | `35e046ba0b2ae49df2badbbccd037f12ea399aa4`（2026-07-17T10:04:11Z） |
| Acceptance Criteria | ①②③ Evidence確認済み／④ Architecture Review承認 — **未確認** |
| Canonical Location | `figma-os/instance-checker/HISTORY.md`, `ROADMAP.md`（存在確認済み） |
| Remote Verification | commit `35e046b` は `origin/main` に到達可能と確認済み |
| Missing Evidence | Architect承認コメントなし |
| CC Recommendation | Ready for Architect Review |

---

## #19 — Documentation Migration: Margin Preflight Documentation

| Field | Content |
|---|---|
| Issue | [#19](https://github.com/ga7ming3249/asd/issues/19) |
| Current Status | Open |
| Deliverable | `figma-os/margin-preflight/HISTORY.md`, `ROADMAP.md` |
| Completion Report | https://github.com/ga7ming3249/asd/issues/19#issuecomment-5001897300 — 改称経緯記録、既知バグ（一部Auto Layoutフレーム未検出）をROADMAP.mdのNowへ引き継ぎ済み |
| Commit Evidence | `41d2a9d407532df6afeae74323e7f35dcf0dfdd4`（2026-07-17T10:07:11Z） |
| Acceptance Criteria | ①②③ Evidence確認済み／④ Architecture Review承認 — **未確認** |
| Canonical Location | `figma-os/margin-preflight/HISTORY.md`, `ROADMAP.md`（存在確認済み） |
| Remote Verification | commit `41d2a9d` は `origin/main` に到達可能と確認済み |
| Missing Evidence | Architect承認コメントなし |
| CC Recommendation | Ready for Architect Review |

---

## #20 — Documentation Migration: Pocket Preview Documentation

| Field | Content |
|---|---|
| Issue | [#20](https://github.com/ga7ming3249/asd/issues/20) |
| Current Status | Open |
| Deliverable | `figma-os/pocket-preview/HISTORY.md`, `ROADMAP.md` |
| Completion Report | https://github.com/ga7ming3249/asd/issues/20#issuecomment-5002012233 — v1.3→v1.0への意図的Version巻き戻し（役割再定義に伴う採番）を記録 |
| Commit Evidence | `1b05a858059f56000f398e3501c7b366b51d98b0`（2026-07-17T10:18:32Z） |
| Acceptance Criteria | ①②③ Evidence確認済み／④ Architecture Review承認 — **未確認** |
| Canonical Location | `figma-os/pocket-preview/HISTORY.md`, `ROADMAP.md`（存在確認済み） |
| Remote Verification | commit `1b05a85` は `origin/main` に到達可能と確認済み |
| Missing Evidence | Architect承認コメントなし |
| CC Recommendation | Ready for Architect Review |

---

## #21 — Documentation Migration: Type Inventory Documentation

| Field | Content |
|---|---|
| Issue | [#21](https://github.com/ga7ming3249/asd/issues/21) |
| Current Status | Open |
| Deliverable | `figma-os/type-inventory/HISTORY.md`, `ROADMAP.md` |
| Completion Report | https://github.com/ga7ming3249/asd/issues/21#issuecomment-5002050624 — ページ配置バグの根本原因調査、appendChild方式への設計変更経緯、Version表記の食い違い（v1.4 vs v1.3 RC）の確定ルールを記録 |
| Commit Evidence | `9f67462665fcb6605f86424c460fbe8235f05339`（2026-07-17T10:22:24Z） |
| Acceptance Criteria | ①②③ Evidence確認済み／④ Architecture Review承認 — **未確認** |
| Canonical Location | `figma-os/type-inventory/HISTORY.md`, `ROADMAP.md`（存在確認済み） |
| Remote Verification | commit `9f67462` は `origin/main` に到達可能と確認済み |
| Missing Evidence | Architect承認コメントなし |
| CC Recommendation | Ready for Architect Review |

---

## #22 — Documentation Migration: Status Stamp Documentation

| Field | Content |
|---|---|
| Issue | [#22](https://github.com/ga7ming3249/asd/issues/22) |
| Current Status | Open |
| Deliverable | `figma-os/status-stamp/HISTORY.md`, `ROADMAP.md` |
| Completion Report | https://github.com/ga7ming3249/asd/issues/22#issuecomment-5002152922 — 運用背景重視の構成、asd#1の観察経緯、Rejected Ideas（フレームロック・全面カラー塗り）を記録 |
| Commit Evidence | `74da7b83589f3db6d8a3a0f1009185a1e860771b`（2026-07-17T10:30:37Z） |
| Acceptance Criteria | ①②③ Evidence確認済み／④ Architecture Review承認 — **未確認** |
| Canonical Location | `figma-os/status-stamp/HISTORY.md`, `ROADMAP.md`（存在確認済み） |
| Remote Verification | commit `74da7b8` は `origin/main` に到達可能と確認済み |
| Missing Evidence | Architect承認コメントなし |
| CC Recommendation | Ready for Architect Review |

---

## #23 — Documentation Migration: Color Inventory Documentation

| Field | Content |
|---|---|
| Issue | [#23](https://github.com/ga7ming3249/asd/issues/23) |
| Current Status | Open |
| Deliverable | `figma-os/color-inventory/HISTORY.md`, `ROADMAP.md` |
| Completion Report | https://github.com/ga7ming3249/asd/issues/23#issuecomment-5002235854 — Foundation Plugin承認経緯、Promote先動的解決の設計反復、"Clean/Cleaning"語彙却下の理由を記録 |
| Commit Evidence | `15ed1346c8e4a1f751b7ae5040bb2167bc663dc4`（2026-07-17T10:36:18Z） |
| Acceptance Criteria | ①②③ Evidence確認済み／④ Architecture Review承認 — **未確認** |
| Canonical Location | `figma-os/color-inventory/HISTORY.md`, `ROADMAP.md`（存在確認済み） |
| Remote Verification | commit `15ed134` は `origin/main` に到達可能と確認済み |
| Missing Evidence | Architect承認コメントなし |
| CC Recommendation | Ready for Architect Review |

---

## #24 — Documentation Migration: Component Package Documentation

| Field | Content |
|---|---|
| Issue | [#24](https://github.com/ga7ming3249/asd/issues/24) |
| Current Status | Open |
| Deliverable | `figma-os/component-package/HISTORY.md`, `ROADMAP.md` |
| Completion Report | https://github.com/ga7ming3249/asd/issues/24#issuecomment-5002298214 — squash mergeされたfeatureブランチの11コミットを掘り起こし、Viewer→Source Organizer転換を含む設計史を時系列記録。READMEに残る6件の未実機確認項目をFuture Notesへ引き継ぎ |
| Commit Evidence | `5f33511a0392abed53c964312a407c5b6ad00c43`（2026-07-17T10:41:27Z） |
| Acceptance Criteria | ①②③ Evidence確認済み／④ Architecture Review承認 — **未確認** |
| Canonical Location | `figma-os/component-package/HISTORY.md`, `ROADMAP.md`（存在確認済み） |
| Remote Verification | commit `5f33511` は `origin/main` に到達可能と確認済み |
| Missing Evidence | Architect承認コメントなし |
| CC Recommendation | Ready for Architect Review |

---

## Summary

| Issue | Files Verified | Commit Verified | Architecture Review | CC Recommendation |
|---|:---:|:---:|:---:|---|
| #17 Guide Stamp | ✅ | ✅ | 未確認 | Ready for Architect Review |
| #18 Instance Checker | ✅ | ✅ | 未確認 | Ready for Architect Review |
| #19 Margin Preflight | ✅ | ✅ | 未確認 | Ready for Architect Review |
| #20 Pocket Preview | ✅ | ✅ | 未確認 | Ready for Architect Review |
| #21 Type Inventory | ✅ | ✅ | 未確認 | Ready for Architect Review |
| #22 Status Stamp | ✅ | ✅ | 未確認 | Ready for Architect Review |
| #23 Color Inventory | ✅ | ✅ | 未確認 | Ready for Architect Review |
| #24 Component Package | ✅ | ✅ | 未確認 | Ready for Architect Review |

全8件、Close Criteriaの①〜③（ファイル作成・Commit・設計知識移行）はCCが客観的に検証可能な範囲で確認済みです。④（Architecture Review承認）はCCの判断権限外であり、8件とも未確認のまま残っています。Accepted / Close の判定は、この束をArchitectが確認した後の別セッションで行ってください。
