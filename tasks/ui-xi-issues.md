# UI/XI Issue Breakdown

This document lists tasks for the initial UI/XI prototype based on the design, implementation, and integration phases.

## Design Phase
- **ui-map-001**: ノード型構造マップの定義 — 構造データのビジュアル表現マップ（JSON→UI）
- **xi-proto-001**: UX構文対話のワイヤーフレーム作成 — Figma / Excalidrawでの画面遷移モック
- **emotion-feedback-001**: 操作感情フィードバック設計 — ポジティブ/ネガティブ操作ログ→UI反映定義

## Implementation Phase
- **codex-sync-001**: Codex構造との連携API定義 — Codex JSON schema ⇄ UI構造ブロック双方向同期
- **user-context-001**: ユーザー文脈データ構造の定義 — user_id / session / emotional_state を含む状態保持構造
- **block-ui-001**: 構文ブロックの可視UIコンポーネント実装 — React or Vueでのドラッグ編集可能UI

## Integration Phase
- **api-integration-001**: 外部連携APIエンドポイント定義 — POST /context | GET /structure などのREST API定義
- **github-release-001**: 初期バージョンのGitHub公開準備 — README / API仕様書 / サンプルデータ
- **codex-compat-001**: Codex互換性チェックのテスト実装 — Codexに準拠する構造出力のユニットテスト
