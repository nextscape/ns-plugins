# Nextscape Plugins（移行済み・アーカイブ）

> [!IMPORTANT]
> このマーケットプレイスは **[`nextscape/ns-skills`](https://github.com/nextscape/ns-skills)** に統合されました。
> 当リポジトリ（`nextscape/ns-plugins`）は新規のプラグイン追加を行いません。今後は ns-skills 側を参照してください。

## 新しいマーケットプレイス

```bash
claude plugin marketplace add nextscape/ns-skills
```

`ns-skills` には、旧 `ns-plugins` が参照していたプラグイン（`marp-slide-nextscape` / `ui-design-grounding` / 旧 ns-skills バンドル）がすべて含まれ、さらに以下の粒度に分割・拡充されています。

| プラグイン | 説明 |
|-----------|------|
| `ns-docs` | 資料作成スキル集（presentation-design / presentation-slides / html-spec-doc） |
| `ns-qms` | QMS 適合診断（qms-align）・デザインレビュー支援（qms-dr） |
| `ns-innovative-thinking` | 新規事業のアイデア発想・企画立案支援 |
| `ns-css-optimization` | CSS の複雑化・肥大化を整理 |
| `ns-bid-scout` | 受注可否の多角評価（BANT / Shipley / MEDDPICC ＋ BSC） |
| `ns-d365bc` | D365 Business Central 統合 MCP（読み取り専用）＋業務知見ツール |
| `nslib-core` | nslib.Mvc.ApiBuilder による .NET 8 WebAPI 開発キット |
| `ui-design-grounding` | UI/UX 設計・実装の判断軸と知識ベース（18 スキル） |
| `marp-slide-nextscape` | Nextscape テーマの Marp スライド自動生成 |

## 既存利用者の移行手順

旧マーケットプレイス（`nextscape-plugins`）を登録済みの場合は、以下で入れ替えてください。

```bash
# 新しいマーケットプレイスを登録
claude plugin marketplace add nextscape/ns-skills

# 旧マーケットプレイスを削除（任意）
claude plugin marketplace remove nextscape-plugins
```

プラグインの管理は Claude Code セッション内の `/plugin` UI、またはターミナルの `claude plugin` コマンドから行えます。
