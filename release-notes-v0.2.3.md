# Release v0.2.3 - テスト実装とドキュメント整備

このリリースでは、テストインフラの大幅な強化とドキュメント整備を行いました。

## 🎯 主な変更点

### テスト実装

#### Web APIテスト（✅ 全て成功）
- **サーバーステータス取得** (`GET /status`)
- **ダッシュボードデータ取得** (`GET /dashboard`)
- **プロセスライフサイクル**（作成→起動→ログ取得→削除）
- **プロセスフィルタリング**（状態、名前パターン）

実行方法:
```bash
cargo test --test test_web_api --features web
```

#### Chrome MCP DevToolsによるE2Eテスト（✅ 全項目成功）
- ダッシュボード表示確認
- プロセス一覧表示
- プロセス作成・起動・停止操作
- ログ表示確認
- 統計情報更新確認

従来のheadless_chrome方式と比較して：
- ✅ 依存関係不要（MCPサーバー使用）
- ✅ 視覚的確認が容易（スクリーンショット）
- ✅ デバッグが簡単（スナップショット）
- ✅ 保守性が高い

### ドキュメント整備

- **`docs/testing.md`**: テスト戦略全体のドキュメント
- **`docs/testing-chrome-mcp.md`**: Chrome MCP E2Eテストの実行結果と詳細手順
- **`tests/test_e2e_browser.md`**: E2Eテストの実行手順書

### その他の改善

- ✅ ページタイトルを「Ichimi Server」に変更
- ✅ コードフォーマットの統一（rustfmt）
- ✅ CI/CD パイプライン全て成功

## 📦 インストール

```bash
# GitHubから直接インストール
cargo install --git https://github.com/chronista-club/ichimi-server --tag v0.2.3

# または最新のmainブランチから
cargo install --git https://github.com/chronista-club/ichimi-server
```

## 🚀 使い方

```bash
# サーバー起動
ichimi

# Webダッシュボード付きで起動
ichimi --web

# カスタムポートで起動
ichimi --web --web-port 8080
```

## 📝 テストの実行

```bash
# 全テストを実行
cargo test

# APIテストのみ実行
cargo test --test test_web_api --features web

# Chrome MCP E2Eテスト
# 手順書に従ってClaude Codeセッション内で実行
# 詳細: tests/test_e2e_browser.md
```

## 🔗 関連リンク

- [リポジトリ](https://github.com/chronista-club/ichimi-server)
- [テストドキュメント](https://github.com/chronista-club/ichimi-server/blob/main/docs/testing.md)
- [Chrome MCP E2Eテスト結果](https://github.com/chronista-club/ichimi-server/blob/main/docs/testing-chrome-mcp.md)

---

**Full Changelog**: https://github.com/chronista-club/ichimi-server/compare/v0.2.2...v0.2.3
