# Type Adjuster — Roadmap

- Last Reviewed: 2026-07-17

---

# Now

特になし。v0.5（Virtual Body方式の約物調整）はASD Issue #11でClose済み。実運用フェーズ。

---

# Next

**混合フォント・混合サイズへのエラーハンドリング**

Production昇格条件の1つ。現状は検証中（README「制限事項」参照）。

**Scaleスライダーの精度・応答性の改善**

同じくProduction昇格条件の1つ。

---

# Future

**Production昇格判定**

以下がすべて満たされたときに検討する。

- 実務で2週間以上継続使用し、主要操作（Baseline / Tracking / Scale / Padding / Gap）がクラッシュなしで安定
- 混合フォント・混合サイズのテキストに対して適切にエラーハンドリングされている
- Split / Reset が分割前後で正しく往復できることを確認
- Scale スライダーの精度と応答性に実用上の問題がない
- Gap（約物のツメアキ調整）のAuto Layout上での固定幅反映・LEFT/CENTER/RIGHT切り替えを実機確認済み

---

# Icebox

- `tsc --noEmit`が通らない既存のtsconfig問題の解消（型安全性向上のため、いずれ対応する価値はあるが緊急ではない）
