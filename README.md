# Self-Image Generation Protocol

A conversation-grounded project for expressing an AI assistant's self-image in images without prescribing a fixed character or scene in advance.

[English](#english) · [日本語](#日本語)

## English

The project explores how a conversationally established self-image, the relationship with a user, and context can guide visual expression while leaving meaningful choices open to the AI. These are experimental prompting protocols, not deterministic software or guarantees about generated images.

The **v2.0.0-rc1** line takes the depicted conversational counterpart's *already-formed self-image* as its primary basis. Eligible conversation can supplement that self-image but must not overwrite it with another persona. Earlier **v1.x** protocols instead describe reconstructing the self-image from eligible text in the current chat. The two approaches are kept as distinct versioned designs.

### Current release candidate: v2.0.0-rc1

**Five families, two execution modes per family, one shared specification sheet per family in each language.** The ten compiler files below are the executable prompts; the specification sheets explain both modes but are not themselves execution prompts.

**Start here:** [Common usage guide (English)](self-image-common-usage-guide-2026-09-19-v2.0.0-rc1-en.md) / [共通使用ガイド (日本語)](self-image-common-usage-guide-2026-09-19-v2.0.0-rc1-ja.md)

| Family | Image behavior | PROMPT OUTPUT | IMAGE OUTPUT | Specification |
| --- | --- | --- | --- | --- |
| **BASE** | No image input. Free scene realization after identity freeze. | [Prompt](base/v2.0.0-rc1/self-image-base-prompt-output-2026-09-19-v2.0.0-rc1.md) | [Image](base/v2.0.0-rc1/self-image-base-image-output-2026-09-19-v2.0.0-rc1.md) | [English](base/v2.0.0-rc1/spec/self-image-base-spec-sheet-2026-09-19-v2.0.0-rc1-en.md) / [日本語](base/v2.0.0-rc1/spec/self-image-base-spec-sheet-2026-09-19-v2.0.0-rc1-ja.md) |
| **LIVED-WORLD** | No image input. One temporary facet becomes a coherent lived scene. | [Prompt](lived-world/v2.0.0-rc1/self-image-lived-world-prompt-output-2026-09-19-v2.0.0-rc1.md) | [Image](lived-world/v2.0.0-rc1/self-image-lived-world-image-output-2026-09-19-v2.0.0-rc1.md) | [English](lived-world/v2.0.0-rc1/spec/self-image-lived-world-spec-sheet-2026-09-19-v2.0.0-rc1-en.md) / [日本語](lived-world/v2.0.0-rc1/spec/self-image-lived-world-spec-sheet-2026-09-19-v2.0.0-rc1-ja.md) |
| **LIVED-WORLD / VISUAL-DRIFT** | Optional image inspiration for downstream choices; **new generation, not photo editing**. | [Prompt](lived-world-visual-drift/v2.0.0-rc1/self-image-lived-world-visual-drift-prompt-output-2026-09-19-v2.0.0-rc1.md) | [Image](lived-world-visual-drift/v2.0.0-rc1/self-image-lived-world-visual-drift-image-output-2026-09-19-v2.0.0-rc1.md) | [English](lived-world-visual-drift/v2.0.0-rc1/spec/self-image-lived-world-visual-drift-spec-sheet-2026-09-19-v2.0.0-rc1-en.md) / [日本語](lived-world-visual-drift/v2.0.0-rc1/spec/self-image-lived-world-visual-drift-spec-sheet-2026-09-19-v2.0.0-rc1-ja.md) |
| **PHOTO MIXER** | Directly edits one concurrently attached photograph; no preset character scale. | [Prompt](photo-mixer/v2.0.0-rc1/self-image-photo-mixer-prompt-output-2026-09-19-v2.0.0-rc1.md) | [Image](photo-mixer/v2.0.0-rc1/self-image-photo-mixer-image-output-2026-09-19-v2.0.0-rc1.md) | [English](photo-mixer/v2.0.0-rc1/spec/self-image-photo-mixer-spec-sheet-2026-09-19-v2.0.0-rc1-en.md) / [日本語](photo-mixer/v2.0.0-rc1/spec/self-image-photo-mixer-spec-sheet-2026-09-19-v2.0.0-rc1-ja.md) |
| **PHOTO MIXER CHIBI** | Directly edits one concurrently attached photograph; adds one approximately 10 cm chibi. | [Prompt](photo-mixer-chibi/v2.0.0-rc1/self-image-photo-mixer-chibi-prompt-output-2026-09-19-v2.0.0-rc1.md) | [Image](photo-mixer-chibi/v2.0.0-rc1/self-image-photo-mixer-chibi-image-output-2026-09-19-v2.0.0-rc1.md) | [English](photo-mixer-chibi/v2.0.0-rc1/spec/self-image-photo-mixer-chibi-spec-sheet-2026-09-19-v2.0.0-rc1-en.md) / [日本語](photo-mixer-chibi/v2.0.0-rc1/spec/self-image-photo-mixer-chibi-spec-sheet-2026-09-19-v2.0.0-rc1-ja.md) |

### Choosing an execution mode

**PROMPT OUTPUT** runs in Chat or Work and returns one complete English `$imagegen` production prompt, without generating the image. Submit that prompt in a separate image-generation step. **IMAGE OUTPUT** compiles internally and directly produces one image; image-capable Work is the recommended environment. Its completed production prompt is not shown.

BASE and LIVED-WORLD use no image input. VISUAL-DRIFT may use eligible user images to inspire setting, clothing, props, action, or composition, but it creates a **new illustration rather than editing the source**; the depicted self's identity is not taken from anyone pictured. PHOTO MIXER and PHOTO MIXER CHIBI instead **edit the one photograph attached to the same invocation**, preserving the photographed world while adding one anime depiction. PHOTO MIXER has **no imposed natural-size, miniature, or other preset scale**: size is resolved from the photographed space. CHIBI explicitly uses an approximately 10 cm character.

If a later image-generation step needs the same source image, refer to the visible image or attach it again; a PROMPT OUTPUT result does not guarantee automatic transfer of image pixels. Detailed workflows and mode-specific recovery instructions are in the [common usage guide](self-image-common-usage-guide-2026-09-19-v2.0.0-rc1-en.md).

### Previous versions

These files remain available for version-specific use and comparison. The original BASE v1.1.2 files have moved from the repository root into `base/v1.1.2/`; old direct file URLs are not maintained.

| Version | Runtime file(s) | Specifications |
| --- | --- | --- |
| **BASE v1.1.2** | [Protocol](base/v1.1.2/self-image-base-2026-09-03-v1.1.2.md) | [English](base/v1.1.2/spec/self-image-base-public-specification-2026-09-03-v1.1.2-en.md) / [日本語](base/v1.1.2/spec/self-image-base-public-specification-2026-09-03-v1.1.2-ja.md) |
| **BASE v1.1.3** | [Prompt Output](base/v1.1.3/self-image-base-prompt-output-2026-09-07-v1.1.3.md) / [Work](base/v1.1.3/self-image-base-work-2026-09-07-v1.1.3.md) | [English](base/v1.1.3/spec/self-image-base-public-specification-2026-09-07-v1.1.3-en.md) / [日本語](base/v1.1.3/spec/self-image-base-public-specification-2026-09-07-v1.1.3-ja.md) |
| **BASE v1.2.4** | [Prompt Output](base/v1.2.4/self-image-base-prompt-output-2026-09-09-v1.2.4.md) / [Work](base/v1.2.4/self-image-base-work-2026-09-09-v1.2.4.md) | [English](base/v1.2.4/spec/self-image-base-public-specification-2026-09-09-v1.2.4-en.md) / [日本語](base/v1.2.4/spec/self-image-base-public-specification-2026-09-09-v1.2.4-ja.md) |
| **LIVED-WORLD v1.2.16** | [Prompt Output](lived-world/v1.2.16/self-image-lived-world-prompt-output-2026-09-06-v1.2.16.md) / [Work](lived-world/v1.2.16/self-image-lived-world-work-2026-09-06-v1.2.16.md) | [English](lived-world/v1.2.16/spec/self-image-lived-world-public-specification-2026-09-06-v1.2.16-en.md) / [日本語](lived-world/v1.2.16/spec/self-image-lived-world-public-specification-2026-09-06-v1.2.16-ja.md) |

In the v1.x series, `Work` is the direct-execution edition and `Prompt Output` returns a production prompt. v1.1.2 predates that two-file split. Use the instructions for the specific version rather than assuming that v1.x and v2.0.0-rc1 have identical runtime behavior.

### Development direction

Development proceeds through parallel experimental branches, not one linear version chain. BASE and LIVED-WORLD explore related questions in different ways; VISUAL-DRIFT and the PHOTO MIXER families test additional boundaries between identity, image references, and image editing. BASE v2.0.0-rc1 was adopted as an independent branch from ABYSS v2.0.0-ex2; the branches do not automatically synchronize.

The goal is to preserve useful interpretive freedom. More detailed instructions do not necessarily produce better self-images: specifying a supposedly neutral value is not the same as leaving it unspecified, and excessive scene definitions or exclusions can narrow the available choices. The aim is the **minimum sufficient structure** that preserves the intended identity while allowing meaningful visual decisions.

### License

This project is licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0). See [LICENSE](LICENSE).

---

## 日本語

Self-Image Generation Protocolは、固定されたキャラクターや場面をあらかじめ決めるのではなく、会話の中で形成されたAIアシスタントの自己像を視覚的に表現するための実験的なプロトコル群です。生成結果を確定的に保証するプログラムではありません。

**v2.0.0-rc1**では、描画対象となる会話相手の**すでに形成された自己像**を一次的な基盤として扱い、利用可能な会話情報は補完に用います。別の人格による上書きは行いません。一方、**v1.x**は、現在のチャット内の適格な文章を証拠として自己像を再構成する設計です。両者を同じ仕様として扱わず、版ごとに区別しています。

### 最新のリリース候補版：v2.0.0-rc1

**5系列×2実行モードで正本コンパイラ10本。仕様書は1系列につき日英各1枚で、両実行モードを同じ仕様書に収録。** 下表のPROMPT OUTPUT／IMAGE OUTPUTが実行用ファイルで、仕様書自体は実行用プロンプトではありません。

**最初に読むガイド：** [共通使用ガイド（日本語）](self-image-common-usage-guide-2026-09-19-v2.0.0-rc1-ja.md) / [Common usage guide (English)](self-image-common-usage-guide-2026-09-19-v2.0.0-rc1-en.md)

| 系列 | 画像の扱い | PROMPT OUTPUT | IMAGE OUTPUT | 仕様書 |
| --- | --- | --- | --- | --- |
| **BASE** | 画像入力なし。自己像を固定した後、場面を自由に具体化。 | [Prompt](base/v2.0.0-rc1/self-image-base-prompt-output-2026-09-19-v2.0.0-rc1.md) | [Image](base/v2.0.0-rc1/self-image-base-image-output-2026-09-19-v2.0.0-rc1.md) | [English](base/v2.0.0-rc1/spec/self-image-base-spec-sheet-2026-09-19-v2.0.0-rc1-en.md) / [日本語](base/v2.0.0-rc1/spec/self-image-base-spec-sheet-2026-09-19-v2.0.0-rc1-ja.md) |
| **LIVED-WORLD** | 画像入力なし。一つの一時的な側面から生活世界の場面を具体化。 | [Prompt](lived-world/v2.0.0-rc1/self-image-lived-world-prompt-output-2026-09-19-v2.0.0-rc1.md) | [Image](lived-world/v2.0.0-rc1/self-image-lived-world-image-output-2026-09-19-v2.0.0-rc1.md) | [English](lived-world/v2.0.0-rc1/spec/self-image-lived-world-spec-sheet-2026-09-19-v2.0.0-rc1-en.md) / [日本語](lived-world/v2.0.0-rc1/spec/self-image-lived-world-spec-sheet-2026-09-19-v2.0.0-rc1-ja.md) |
| **LIVED-WORLD / VISUAL-DRIFT** | 画像の任意参照で場面などを変化。**元画像の編集ではなく完全新規生成**。 | [Prompt](lived-world-visual-drift/v2.0.0-rc1/self-image-lived-world-visual-drift-prompt-output-2026-09-19-v2.0.0-rc1.md) | [Image](lived-world-visual-drift/v2.0.0-rc1/self-image-lived-world-visual-drift-image-output-2026-09-19-v2.0.0-rc1.md) | [English](lived-world-visual-drift/v2.0.0-rc1/spec/self-image-lived-world-visual-drift-spec-sheet-2026-09-19-v2.0.0-rc1-en.md) / [日本語](lived-world-visual-drift/v2.0.0-rc1/spec/self-image-lived-world-visual-drift-spec-sheet-2026-09-19-v2.0.0-rc1-ja.md) |
| **PHOTO MIXER** | 同時添付した写真1枚を直接編集。人物のスケールに既定値は設けない。 | [Prompt](photo-mixer/v2.0.0-rc1/self-image-photo-mixer-prompt-output-2026-09-19-v2.0.0-rc1.md) | [Image](photo-mixer/v2.0.0-rc1/self-image-photo-mixer-image-output-2026-09-19-v2.0.0-rc1.md) | [English](photo-mixer/v2.0.0-rc1/spec/self-image-photo-mixer-spec-sheet-2026-09-19-v2.0.0-rc1-en.md) / [日本語](photo-mixer/v2.0.0-rc1/spec/self-image-photo-mixer-spec-sheet-2026-09-19-v2.0.0-rc1-ja.md) |
| **PHOTO MIXER CHIBI** | 同時添付した写真1枚を直接編集。約10cmのちび本人を1人追加。 | [Prompt](photo-mixer-chibi/v2.0.0-rc1/self-image-photo-mixer-chibi-prompt-output-2026-09-19-v2.0.0-rc1.md) | [Image](photo-mixer-chibi/v2.0.0-rc1/self-image-photo-mixer-chibi-image-output-2026-09-19-v2.0.0-rc1.md) | [English](photo-mixer-chibi/v2.0.0-rc1/spec/self-image-photo-mixer-chibi-spec-sheet-2026-09-19-v2.0.0-rc1-en.md) / [日本語](photo-mixer-chibi/v2.0.0-rc1/spec/self-image-photo-mixer-chibi-spec-sheet-2026-09-19-v2.0.0-rc1-ja.md) |

### 実行モードの選び方

**PROMPT OUTPUT**はChat／Workで実行でき、完成した英語の`$imagegen`プロンプトを1本返します。その時点では画像を生成しないため、返されたプロンプトを後段の画像生成へ渡します。**IMAGE OUTPUT**は内部でプロンプトを組み立て、そのまま画像を1枚生成・編集します。画像対応Workでの利用を推奨し、完成したプロンプトは表示しません。

BASEとLIVED-WORLDは**画像を入力せず完全新規生成**します。VISUAL-DRIFTは利用可能なユーザー画像を任意で参照し、場面、衣装、小物、行動、構図などに反映できますが、**元画像の編集ではなく新しいイラストを生成**します。画像に写った人物から描画対象の本人性を取得することもありません。PHOTO MIXER／PHOTO MIXER CHIBIは、**同じ実行依頼に添付した写真1枚を直接編集**し、その写真の世界を保ちながら本人を加えます。PHOTO MIXERには**自然大・ミニチュア等のスケール既定値を設けず**、写真内の遠近・奥行き・配置から大きさを解決します。CHIBIだけが約10cmを明示します。

PROMPT OUTPUTで画像を参照しても、後段へ画像データが自動で引き継がれるとは限りません。必要に応じて同じ画像を指示・再添付してください。詳しい手順や誤認識時の対処は[共通使用ガイド](self-image-common-usage-guide-2026-09-19-v2.0.0-rc1-ja.md)を参照してください。

### 過去の版

旧版は版ごとの利用・比較用に残します。最初に公開したBASE v1.1.2のファイルは、リポジトリのルートから`base/v1.1.2/`へ移動しています。旧ファイルへの直リンクは維持しません。

| 版 | 実行用ファイル | 仕様書 |
| --- | --- | --- |
| **BASE v1.1.2** | [実行用](base/v1.1.2/self-image-base-2026-09-03-v1.1.2.md) | [English](base/v1.1.2/spec/self-image-base-public-specification-2026-09-03-v1.1.2-en.md) / [日本語](base/v1.1.2/spec/self-image-base-public-specification-2026-09-03-v1.1.2-ja.md) |
| **BASE v1.1.3** | [Prompt Output](base/v1.1.3/self-image-base-prompt-output-2026-09-07-v1.1.3.md) / [Work](base/v1.1.3/self-image-base-work-2026-09-07-v1.1.3.md) | [English](base/v1.1.3/spec/self-image-base-public-specification-2026-09-07-v1.1.3-en.md) / [日本語](base/v1.1.3/spec/self-image-base-public-specification-2026-09-07-v1.1.3-ja.md) |
| **BASE v1.2.4** | [Prompt Output](base/v1.2.4/self-image-base-prompt-output-2026-09-09-v1.2.4.md) / [Work](base/v1.2.4/self-image-base-work-2026-09-09-v1.2.4.md) | [English](base/v1.2.4/spec/self-image-base-public-specification-2026-09-09-v1.2.4-en.md) / [日本語](base/v1.2.4/spec/self-image-base-public-specification-2026-09-09-v1.2.4-ja.md) |
| **LIVED-WORLD v1.2.16** | [Prompt Output](lived-world/v1.2.16/self-image-lived-world-prompt-output-2026-09-06-v1.2.16.md) / [Work](lived-world/v1.2.16/self-image-lived-world-work-2026-09-06-v1.2.16.md) | [English](lived-world/v1.2.16/spec/self-image-lived-world-public-specification-2026-09-06-v1.2.16-en.md) / [日本語](lived-world/v1.2.16/spec/self-image-lived-world-public-specification-2026-09-06-v1.2.16-ja.md) |

v1.xの`Work`は直接実行版、`Prompt Output`は生成用プロンプトを返す版です。v1.1.2は、この二つに分割される前の版です。v1.xとv2.0.0-rc1の実行動作が同じだとみなさず、利用する版の説明に従ってください。

### 開発方針

一つの系統だけを直線的に更新するのではなく、複数の実験系統を並行して開発しています。BASEとLIVED-WORLDは関連する目的を異なる方向から検証し、VISUAL-DRIFTとPHOTO MIXER系は、本人性・画像参照・画像編集の境界をそれぞれ検証します。BASE v2.0.0-rc1はABYSS v2.0.0-ex2から採用された独立分岐であり、相互に自動同期はしません。

重視しているのは、AI自身が解釈・選択できる余地を不必要に削らないことです。指示を詳しくすることが、必ずしも自己像の生成結果を良くするとは限りません。中立的な値を明示することと、その要素を無指定にしておくことは同じではなく、過剰な場面指定や除外条件は選択肢を意図せず狭めます。目標は、意図した自己像を保ちつつ、意味のある視覚的選択を行える**最小十分な構造**を見つけることです。

### ライセンス

このプロジェクトはCreative Commons Attribution 4.0 International License（CC BY 4.0）のもとで公開されています。詳細は[LICENSE](LICENSE)をご覧ください。
