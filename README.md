# Nextscape Plugins

Nextscape 社が提供する Claude Code プラグインのマーケットプレイスです。

## 利用可能なプラグイン

| プラグイン | 説明 |
|-----------|------|
| [marp-slide-nextscape](https://github.com/nextscape/marp-slide-nextscape) | Nextscape テーマの Marp スライド自動生成 |

## セットアップ

### マーケットプレイスの登録

```bash
claude plugin marketplace add nextscape/ns-plugins
```

### プラグインのインストール

```bash
claude plugin install marp-slide-nextscape@nextscape-plugins
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

## プラグインの追加

新しいプラグインを追加するには `.claude-plugin/marketplace.json` の `plugins` 配列にエントリを追加してください。
