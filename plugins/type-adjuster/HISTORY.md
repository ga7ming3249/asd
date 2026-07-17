# Type Adjuster — History

- Status: Beta
- Version: v0.5
- Last Reviewed: 2026-07-17
- Related Issues: [#11](https://github.com/ga7ming3249/asd/issues/11)

---

# Overview

選択したテキストレイヤーの組版パラメータをスライダーとステッパーで素早く調整する実務ツール。「手を動かす」ことに特化し、知識設計はType Polishが担当する。

コードは `ga7ming3249/figma-os` の `type-adjuster/` にある（Vite → `dist/`）。

---

# Development History

## v0.1（2026-06-24, `24b3731`）

新規追加。Beta。

## Baseline / Split の拡張（2026-06-30〜2026-07-01）

- `e6ced10`（2026-06-30）: Baseline数値入力・日本語対応Split位置指定を追加
- `1a2b895`（2026-07-01）: Baselineデルタ適用バグ修正・Split複数位置対応・UIスクロール解消

## Virtual Body方式の開発（2026-07-08頃〜、ASD運用開始前）

ChatGPT・Fable・Claude Codeとの対話型開発で、約物（句読点等）の送り幅調整機能を検証・実装。現在のASD Issue運用開始（2026-07-12）より先に存在していた作業。

複数のアプローチを実機スパイクで検証（詳細は「Rejected Ideas」参照）し、最終的にVirtual Body方式（約物自身を固定幅TextNodeとして扱う）を採用。2026-07-08から2026-07-17まで実案件で試用し、Baseline調整・約物のツメアキ調整ともに大きな不具合なく運用できていた。

## v0.5 — Virtual Body方式の正式コミット（ASD Issue #11、2026-07-17）

ASD Issue #10の監査でこの未コミットローカル作業が検出され（当初「Gap Editor」という開発コードネームで認識）、設計経緯を整理した結果、ASD Issue #11として正式な実装Issueに再定義。

Pre-commit監査 → Vision Owner決定（Version v0.4→v0.5、Status Beta維持、Split機能の無関係な命名変更を除外）→ 実装（`db6d9fb`）・ドキュメント（`26cc6a5`）の2コミットに分割してpush → 実機確認・Architecture Review承認 → Close、という流れで完了。

---

# Design Decisions

- **Virtual Body方式**: 約物自身を固定幅TextNode（`textAutoResize: NONE` + `layoutSizingHorizontal: FIXED`）として扱い、送り幅を直接操作する。Auto Layoutは、操作順序に関わらずTextNodeの宣言済み幅（natural/ink幅ではなく）でsiblingを配置することを最小スパイクで確認済み。
- **LEFT / CENTER / RIGHT の3方向のみ**: `textAlignHorizontal`をpluginDataに保持し、選択解除後も維持。前後非対称の同時調整（Before/After独立制御）はスコープ外 — 実際のユースケース（後端の約物は後方を、先端の約物は前方を、対称的な約物は両方をツメる）で十分カバーできると判断。
- **自動選択・記憶なし**: 文字種による自動align選択（例: 「、」→LEFT）や直前使用モードの記憶は試して却下。デザイナーが毎回明示的に方向を選択する設計とした。
- **Gap編集はノード生成を行わない**: 既存TextNodeの`resize`とpluginData更新のみで完結させ、再実行時のノード増殖リスクを排除。
- **同期処理によるUndo単位の確保**: `applyGapAdjust`/`applyGapSet`/`applyGapAlign`はいずれも`await`を含まない同期関数とし、1操作＝1 Undoステップを保証。

---

# Rejected Ideas

- **Gap Spacer方式**（開発初期の呼称「Gap Editor」）: 約物の前後に挿入するスペーサーノードで間隔を調整する方式。実機検証により却下。
- **letterSpacingベースの調整**: 単一文字ノードへの末尾letterSpacingは、Figmaのhug幅に影響しないことが実験で判明し却下（`experiments/spike-letterspacing-hug`）。
- **自動per-character align選択・直前モードの記憶**: 上記Design Decisions参照。試したが却下。

---

# Future Notes

- 実機確認（Auto Layout固定幅反映、LEFT/CENTER/RIGHT視覚確認、Undo、Reset往復、既存機能回帰、保存・再オープン耐性）はVision Ownerにより完了済み（重大な問題なし）。
- Production昇格条件（`docs/ROADMAP.md` / 旧`figma-os/ROADMAP.md`参照）は未達成: 混合フォント・混合サイズのエラーハンドリング、Scaleスライダー精度の改善が残タスク。
- `tsc --noEmit`が素通しできない状態が既存のまま残っている（tsconfigの`types`未指定に起因、Issue #11のスコープ外）。ビルド検証はVite実行で代替中。
