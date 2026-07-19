# Owner Rules

Each Issue must have exactly one Owner at any given time. The Owner is whoever currently holds the ball.

## Owners

| Owner | Role |
|---|---|
| **User** | Decision-making, design direction, final approval |
| **ChatGPT** | Project Manager, Technical Director |
| **Claude Code** | Implementation, code changes, file operations |
| **Fable** | Deep research, architecture, long-form analysis |

## Rules

- Set `## Owner` to whoever needs to act next.
- When handing off, update the Owner field and leave a comment explaining the handoff.
- An Issue with no clear Owner is blocked — always assign before closing the thread.

## Independent Review Role

ASDでは、Architectおよび実装担当とは別に、必要に応じて独立した監修・レビュー担当を起用する。

独立レビュー担当の責務は以下とする。

- 仕様および設計に対する第三者レビュー
- 実装方針の技術的妥当性確認
- 見落とし、矛盾、将来リスクの指摘
- 代替案の提示
- Accept Review前の追加検証

独立レビュー担当は最終意思決定者ではない。

最終的な製品判断はOwnerが行い、アーキテクチャおよびASDガバナンス上の判断はArchitect Reviewを経る。

## Reviewer Selection Policy

独立レビューに使用するモデルは固定しない。

以下を考慮してOwnerが選定する。

- 利用可能性
- コスト
- 対象タスクへの適性
- コンテキスト容量
- 技術レビュー能力
- Architectおよび実装担当からの独立性

現在の候補は以下とする。

### Fable5

- 利用可能な場合の優先的な監修候補
- 設計・実装に対する第三者視点を担当
- 利用条件が改善された場合は積極的な再起用を許容する

### GPT-5.6 Sol

- Claude Code上で利用する監修・独立レビュー候補
- Fable5がコストまたは利用条件の都合で使用困難な期間の代替を担う
- 必要に応じてFable5との併用も可能とする

## Availability and Fallback Rule

監修モデルが利用不能または実用上利用困難になった場合、それを理由にIssueの進行を停止しない。

Ownerは、同等の監修責務を担える別モデルへ切り替えられる。

モデルの変更によって以下の役割分担は変更しない。

- Owner：最終判断
- Claude Code：実装およびリポジトリ作業
- Architect：アーキテクチャ、仕様整合性、ASDガバナンス
- Independent Reviewer：第三者監修および技術検証

モデル名ではなく、役割と責務を永続ルールとして管理すること。
