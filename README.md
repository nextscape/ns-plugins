# Nextscape Plugins

Nextscape 社が提供する Claude Code プラグインのマーケットプレイスです。

## 利用可能なプラグイン

| プラグイン | 説明 |
|-----------|------|
| [marp-slide-nextscape](https://github.com/nextscape/marp-slide-nextscape) | Nextscape テーマの Marp スライド自動生成 |
| [ui-design-grounding](https://github.com/nextscape/ui-design-grounding) | UI/UX 設計・実装の判断軸と知識ベース |

## セットアップ

### マーケットプレイスの登録

```bash
claude plugin marketplace add nextscape/ns-plugins
```

### プラグインのインストール

```bash
claude plugin install ui-design-grounding@nextscape-plugins
```

### チームへの展開

プロジェクトの `.claude/settings.json` に以下を追加すると、メンバーがマーケットプレイスを自動認識できます：

```json
{
  "extraKnownMarketplaces": {
    "nextscape-plugins": {
      "source": {
        "source": "github",
        "repo": "nextscape/ns-plugins"
      }
    }
  }
}
```

## プラグインの管理

プラグインの管理は Claude Code セッション内で `/plugin` と入力して開くインタラクティブ UI から行えます。

### `/plugin` でできること

| タブ | 操作 |
|------|------|
| **Installed** | インストール済みプラグインの一覧表示・有効化・無効化・アンインストール・更新 |
| **Discover** | 登録済みマーケットプレイスからプラグインを検索・インストール |
| **Marketplaces** | マーケットプレイスの追加・削除 |
| **Errors** | プラグインの読み込みエラーや LSP サーバーの問題を確認 |

### プラグインの自動更新

Claude Code はセッション開始時にインストール済みプラグインの更新を自動チェックし、新しいバージョンがあればプロンプトで通知します。`/plugin` の Installed タブからも手動で更新できます。

### インストールスコープ

プラグインのインストール時にスコープを選択できます。

| スコープ | 設定ファイル | 用途 |
|---------|-----------|------|
| `user` (デフォルト) | `~/.claude/settings.json` | 個人のすべてのプロジェクトで利用 |
| `project` | `.claude/settings.json` | チームで共有（Git 管理） |
| `local` | `.claude/settings.local.json` | プロジェクト固有・Git 対象外 |

### CLI からの操作

スクリプトや自動化で使う場合は、ターミナルから `claude plugin` コマンドも利用できます。

```bash
claude plugin install <plugin>@<marketplace> [--scope user|project|local]
claude plugin update <plugin>@<marketplace>
claude plugin uninstall <plugin>@<marketplace> [--keep-data]
claude plugin enable <plugin>@<marketplace>
claude plugin disable <plugin>@<marketplace>
claude plugin marketplace add <owner>/<repo>
```

### トラブルシューティング

- `/plugin` の **Errors** タブでプラグインの読み込みエラーを確認できます
- `claude --debug` でプラグイン読み込みの詳細ログを表示できます

## プラグインの追加

新しいプラグインを追加するには `.claude-plugin/marketplace.json` の `plugins` 配列にエントリを追加してください。
