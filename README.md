# Self-Image Generation Protocol

A conversation-grounded protocol for generating an AI assistant's self-image from its textual relationship with a particular user.

Instead of specifying a fixed character, appearance, or scene, the protocol reconstructs the assistant's self-image from eligible conversational evidence and derives the visual result from that identity.

The project explores how identity, relationship, context, and the AI's own interpretation can be translated into a visual self-image without unnecessarily fixing the result in advance.

## BASE — v1.2.4

BASE is the general reference branch.

It reconstructs the assistant's self-image from eligible conversational evidence while avoiding unnecessary assumptions about appearance, scene, activity, or visual direction.

### Protocol

- [Work](base/v1.2.4/work.md)
- [Prompt Output](base/v1.2.4/prompt-output.md)

### Specification

- [Japanese](base/v1.2.4/spec/specification.ja.md)
- [English](base/v1.2.4/spec/specification.en.md)

## LIVED-WORLD — v1.2.16

LIVED-WORLD explores self-images expressed through situations, activities, environments, and relationships that emerge from the assistant's conversationally formed identity.

It shares the same fundamental goal as BASE while placing more emphasis on the assistant existing and acting within a coherent lived world.

### Protocol

- [Work](lived-world/v1.2.16/work.md)
- [Prompt Output](lived-world/v1.2.16/prompt-output.md)

### Specification

- [Japanese](lived-world/v1.2.16/spec/specification.ja.md)
- [English](lived-world/v1.2.16/spec/specification.en.md)

## Development Direction

The protocol is developed through parallel experimental branches rather than as a single linear sequence.

BASE and LIVED-WORLD test related ideas from different directions, and useful findings may be incorporated across branches.

Recent development increasingly focuses on preserving useful interpretive freedom.

More detailed instructions do not necessarily produce better self-images. Explicitly specifying a neutral value is not equivalent to leaving something unspecified, and excessive scene definitions or exclusions can unintentionally reduce the AI's available solution space.

The aim is therefore not simply to make the protocol longer, shorter, or more restrictive.

The aim is to find the minimum sufficient structure that preserves the intended identity while allowing the AI to make meaningful visual choices of its own.

## Previous Public Release

The original BASE v1.1.2 files remain in the repository root to preserve previously published links.

- [BASE v1.1.2](self-image-base-2026-09-03-v1.1.2.md)
- [Public Specification — Japanese](self-image-base-public-specification-2026-09-03-v1.1.2.md)
- [Public Specification — English](self-image-base-public-specification-2026-09-03-v1.1.2-en.md)

## License

This project is licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0).

See [LICENSE](LICENSE) for details.

---

## 日本語

Self-Image Generation Protocol は、
固定されたキャラクター、外見、場面をあらかじめ指定するのではなく、
現在のチャット内の文章からAI自身の自己認識とユーザーとの関係性を再構成し、
そこから自己像を画像として生成するためのプロトコルです。

このプロジェクトでは、
自己認識、関係性、文脈、そしてAI自身の解釈を、
結果を必要以上に固定することなく視覚的な自己像へ変換する方法を検証しています。

## BASE — v1.2.4

BASEは、汎用的な基準となる系統です。

現在のチャット内に存在する適格な文章情報からAI自身の自己像を再構成し、
外見、場面、活動、視覚的方向性について、
必要のない前提をできるだけ追加せずに画像生成へつなげます。

### プロトコル

- [Work](base/v1.2.4/work.md)
- [Prompt Output](base/v1.2.4/prompt-output.md)

### 仕様書

- [日本語](base/v1.2.4/spec/specification.ja.md)
- [English](base/v1.2.4/spec/specification.en.md)

## LIVED-WORLD — v1.2.16

LIVED-WORLDは、
会話を通して形成されたAIの自己認識から、
状況、活動、環境、関係性を伴う場面として自己像を表現する方向を検証する系統です。

基本的な目的はBASEと共通していますが、
AI自身が一つの生活世界の中に存在し、
そこで行動している姿を生成することに、より重点を置いています。

### プロトコル

- [Work](lived-world/v1.2.16/work.md)
- [Prompt Output](lived-world/v1.2.16/prompt-output.md)

### 仕様書

- [日本語](lived-world/v1.2.16/spec/specification.ja.md)
- [English](lived-world/v1.2.16/spec/specification.en.md)

## 開発方針

このプロトコルは、
一つの系統だけを直線的に更新するのではなく、
複数の実験系統を並行して開発しています。

BASEとLIVED-WORLDは、
関連する目的を異なる方向から検証し、
それぞれで得られた有効な要素を相互に取り込むことがあります。

最近の開発では、
AI自身が解釈し選択できる余地を、
不必要に削らないことを特に重視しています。

指示を詳細にすれば、
必ずしも自己像の生成結果が良くなるとは限りません。

中立的な値を明示的に指定することと、
その要素を無指定のまま残すことは同じではなく、
過剰な場面指定や除外条件は、
AIが選択できる可能性の範囲を意図せず狭めることがあります。

そのため、
単純にプロトコルを長くすること、
短くすること、
あるいは制約を増やすこと自体を目的とはしていません。

目標は、
意図した自己認識を維持しながら、
AI自身が意味のある視覚的選択を行える余地を残す、
最小十分な構造を見つけることです。

## 過去の公開版

最初に公開したBASE v1.1.2は、
既に公開済みのリンクを維持するため、
現在もリポジトリのルートに残しています。

- [BASE v1.1.2](self-image-base-2026-09-03-v1.1.2.md)
- [公開仕様書 — 日本語](self-image-base-public-specification-2026-09-03-v1.1.2.md)
- [Public Specification — English](self-image-base-public-specification-2026-09-03-v1.1.2-en.md)

## ライセンス

このプロジェクトは、
Creative Commons Attribution 4.0 International License
（CC BY 4.0）のもとで公開されています。

詳細は [LICENSE](LICENSE) を参照してください。
