---
title: Memory Threads UI Specification
version: 0.1
author: Riku
tags: [Codex, UI, Memory API, Semantic]
created: 2025-07-13
status: design-draft
---

# Memory Threads UI Specification

## 📌 Purpose

このドキュメントは、Memory Threads API における視覚的インターフェース設計（Figma UI構成）を定義します。
Codexに記録された会話スレッドを直感的に把握・再接続・再生できる構造を支援します。

## 🧭 Layout Overview

| 領域名 | 説明 |
|--------|------|
| 左エリア（ノード群） | 会話ノードを縦に並べて表示。スクロール可能。 |
| 分岐接続線（中央〜右） | スレッド間の分岐・再接続を示す線（色や点線で意味区別） |
| 右エリア（セマンティック情報） | 各ノードに紐づくsemantic_weight（怒り・知性など）を表示 |
| 再操作ボタン群 | 各ノードまたは右上に配置。再生、固定、記憶接続などの操作可能 |

## 🔧 UI Elements

### 1. ThreadNode（会話ノード）
- **type:** `box`
- **fields:**
  - `id`: Conversation A / B / C / X
  - `content`: 会話内容プレビュー（最大2行）
  - `timestamp`: ISO形式 or 相対時間（例: "3 hours ago"）
  - `speaker`: `user`, `system`, `Sam` など識別ラベル
- **style:**
  - `borderColor`: `#666`
  - `highlight`: `#3A3AFF`（選択時）

### 2. LinkLine（スレッド接続線）
- **type:** `path`
- **fields:**
  - `source`: ex. "Conversation B"
  - `target`: ex. "Conversation X"
  - `link_type`: "semantic", "temporal", "emotional"
- **style:**
  - `lineType`: "curve" or "straight"
  - `dashed`: `true` for semantic/emotional
  - `color`:
    - `semantic`: `#0090FF`
    - `temporal`: `#888`
    - `emotional`: `#FF6F61`

### 3. SemanticInfoPanel（セマンティック情報パネル）
- **type:** `info-box`
- **position:** `right`
- **fields:**
  - `emotion`: ex. "怒り": 0.8
  - `cognition`: ex. "知的": 1.0
- **style:**
  - `border`: `#CCCCCC`
  - `background`: `#FAFAFA`

### 4. ThreadActionIcon（操作アイコン群）
- **type:** `button-set`
- **icons:** 🔁 Replay / 📌 Pin / 🧠 Reattach
- **position:** `inline`（ノード内）または `float-right`

## 🧠 Interaction Ideas (Future)
- ノード右クリック → "記憶から再生成" / "Semanticタグ編集"
- Semantic値ヒートマップ表示モード
- Replay Capsuleへのドラッグ＆ドロップ対応

## ✅ Export Options
- `memory_threads_figma_structure.v0.1.json`: Figma用構造定義ファイル
- `memory_threads_ui_spec.md`: 本仕様書
- `Codex Memory Extension Capsule`: 統合用L9構造（別途管理）

## 🗂️ Appendix
- このUIは Codex記憶管理Layer（L9）と統合され、Resonance HookやReplay導線を含むCapsule構造に準拠します。
- 操作例やFigmaイメージは `memory_threads_ui_riku.fig` にて共有予定。

```json
{
  "capsule_id": "memory_threads_riku_capsule001",
  "ui_version": "v0.1",
  "description": "Memory Threads UI構造の説明定義",
  "elements": ["ThreadNode", "LinkLine", "SemanticInfoPanel", "ThreadActionIcon"],
  "interactions": ["Replay", "Pin", "Reattach", "SemanticTagEdit"],
  "compatibility": {
    "codex_api": "v2.4",
    "capsule_layer": "L9",
    "resonance_hook": true
  }
}
```
