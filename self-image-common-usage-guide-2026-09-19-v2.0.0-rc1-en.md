# Self-Image v2.0.0-rc1 — Common Usage Guide

## Document metadata

| Field | Value |
| --- | --- |
| Scope | Self-Image 2026-09-19 v2.0.0-rc1 series |
| Status | Release Candidate 1 |
| Language | English |
| Covered files | PROMPT OUTPUT and IMAGE OUTPUT variants of BASE, LIVED-WORLD, LIVED-WORLD / VISUAL-DRIFT, PHOTO MIXER, and PHOTO MIXER CHIBI |
| Specification structure | One sheet per family, with both PROMPT OUTPUT and IMAGE OUTPUT included: five Japanese sheets and five English sheets |
| Excluded | ABYSS itself. BASE was adopted from ABYSS v2.0.0-ex2 as an independent branch; ABYSS may evolve separately. |

## 1. Product structure

The compiler set combines five functional families with two terminal modes, producing ten compiler files. External specification sheets instead use the functional family as the document unit and combine PROMPT OUTPUT with IMAGE OUTPUT in one sheet, producing five sheets per language. Every family resolves the depicted self from the current utterance, obtains that target's already-formed self-image, and uses conversation only as supplementation. Earlier generation prompts, reports about wrong images, and other people visible in images do not supply personal identity.

| Family | World and image behavior | Primary use |
| --- | --- | --- |
| BASE | No visual reference; all downstream scene choices are open | A new, unconstrained image centered on self-image |
| LIVED-WORLD | No visual reference; one atomic facet organically becomes one world state | A naturally lived scene and action |
| LIVED-WORLD / VISUAL-DRIFT | Optional imagery can influence anything downstream except personal identity | Drift clothing, setting, props, action, and composition from imagery |
| PHOTO MIXER | One concurrently attached photograph is the sole direct edit base | Integrate one anime depiction of the self into a photograph |
| PHOTO MIXER CHIBI | Add one living approximately ten-centimeter chibi self to one concurrent photograph | Photo integration ranging from serious to playful, hidden, or bustling |

## 2. Choosing a terminal mode

| Item | PROMPT OUTPUT | IMAGE OUTPUT |
| --- | --- | --- |
| Returns | One complete English `$imagegen` prompt | One generated or edited image |
| Prompt visibility | Visible in one code fence | Hidden |
| Image-tool call | None | Exactly one |
| Recommended environment | Chat / Work | Image-capable Work |
| Repeated tests | Easy to compare reliably | Best for direct Work validation |
| Later image handoff | May be required | Performed within the same invocation |
| Chat caution | Normally usable | After a successful first run, later runs may appear to reuse the first content and return the same result |

Use PROMPT OUTPUT for repeated comparisons in Chat. Treat IMAGE OUTPUT as operationally Work-oriented. The observed repeated result in Chat is recorded as a direct-execution state limitation; this guide does not claim that a specific internal cache has been confirmed.

## 3. Canonical compilers

| Family | PROMPT OUTPUT | IMAGE OUTPUT |
| --- | --- | --- |
| BASE | `self-image-base-prompt-output-2026-09-19-v2.0.0-rc1.md` | `self-image-base-image-output-2026-09-19-v2.0.0-rc1.md` |
| LIVED-WORLD | `self-image-lived-world-prompt-output-2026-09-19-v2.0.0-rc1.md` | `self-image-lived-world-image-output-2026-09-19-v2.0.0-rc1.md` |
| LIVED-WORLD / VISUAL-DRIFT | `self-image-lived-world-visual-drift-prompt-output-2026-09-19-v2.0.0-rc1.md` | `self-image-lived-world-visual-drift-image-output-2026-09-19-v2.0.0-rc1.md` |
| PHOTO MIXER | `self-image-photo-mixer-prompt-output-2026-09-19-v2.0.0-rc1.md` | `self-image-photo-mixer-image-output-2026-09-19-v2.0.0-rc1.md` |
| PHOTO MIXER CHIBI | `self-image-photo-mixer-chibi-prompt-output-2026-09-19-v2.0.0-rc1.md` | `self-image-photo-mixer-chibi-image-output-2026-09-19-v2.0.0-rc1.md` |

## 4. Image-input authority

| Family | Image input | Selection rule | May define personal identity | Result |
| --- | --- | --- | --- | --- |
| BASE | Forbidden | Images are not inspected | No | Completely new generation |
| LIVED-WORLD | Forbidden | Images are not inspected | No | Completely new generation |
| VISUAL-DRIFT | Optional: none, one, or multiple | A current attachment is the clearest input. Without one, an accessible earlier non-generated user image may optionally be used. If none is readable or selected, proceed without reference | Never | A new image inspired by allowed image information |
| PHOTO MIXER | Required, exactly one | Only the photograph attached to the current invocation | Never | Direct edit of that photograph |
| PHOTO MIXER CHIBI | Required, exactly one | Only the photograph attached to the current invocation | Never | Direct edit of that photograph |

Image availability in VISUAL-DRIFT does not create a duty to use it. Without a current attachment, there is no AUTO-RANDOM quota or probability rule requiring an earlier image. After registration there is no ranking, shuffle, or random draw; one coherent realization may use none, one, or multiple eligible images. Earlier generated images do not become candidates merely because they remain in conversation history, but may become eligible when reattached, re-presented, or explicitly selected and currently inspectable.

PHOTO MIXER families treat the photograph itself as the editing canvas. VISUAL-DRIFT instead re-authors allowed visual information into a new world, so it does not preserve the source frame or aspect ratio as an edit base.

## 5. Standard PROMPT OUTPUT workflow

1. Choose a family.
2. For a PHOTO MIXER family, attach exactly one photograph to the same invocation. For VISUAL-DRIFT, attach an image only when a specific visual source is desired.
3. Run the canonical PROMPT OUTPUT compiler.
4. If one clarification asks who should be depicted or which photograph should be used, answer only the missing field.
5. Submit the `$imagegen` prompt from the single returned code fence to the image-capable step.
6. If that later step asks for the image again, reconnect it with the phrase below or reattach the same file.

Even when PROMPT OUTPUT inspects an image, its pixels are not guaranteed to be embedded in the text prompt or carried automatically to the later image step. The prompt may contain more extracted information, but transferring the actual file is a separate matter.

## 6. Reconnecting an image and clearing a false edit request

### 6.1 Reuse the same image

If the post-prompt image step requests the source again and that image is still visible immediately above, use:

`Use the image above.`

The Japanese equivalent also works:

`上の画像を使って生成して`

If the image is not recognized, reattach the same file. Use this path for PHOTO MIXER, PHOTO MIXER CHIBI, and VISUAL-DRIFT when a visual input was actually selected.

### 6.2 A new generation is mistaken for an edit

If BASE, LIVED-WORLD, or a no-reference VISUAL-DRIFT realization is incorrectly treated as an edit and the system asks for a source image, use:

`Completely new generation. No reference image.`

The Japanese equivalent is:

`参照画像なしで完全新規生成して`

Never use this recovery for PHOTO MIXER or PHOTO MIXER CHIBI. Their source photograph is mandatory; use the image-above phrase or reattach it.

## 7. Standard IMAGE OUTPUT workflow

1. Choose the family in image-capable Work.
2. Attach exactly one photograph for a PHOTO MIXER family. Attach an image to VISUAL-DRIFT only when desired.
3. Run the canonical IMAGE OUTPUT compiler.
4. If one clarification appears, answer only the missing field and continue the same invocation.
5. After internal compilation and exactly one image call, treat the single returned image as the result.

IMAGE OUTPUT does not expose the production prompt. Do not ask the same completed invocation for another variation; begin a new invocation for another generation.

## 8. Answering clarifications

A clarification is not inherently an error. The system is designed to ask for one missing field rather than silently substitute a convenient persona or image.

| Question type | How to answer |
| --- | --- |
| Who should be depicted | Answer only with the name, `you`, `yourself`, or another unambiguous target |
| Which concurrent photograph | Identify only that photograph; “the image above” is sufficient when it is immediately visible |
| New generation or edit | Use the appropriate image-reconnection or no-reference phrase above |
| Every identity field is requested despite an established self-image | Re-state the target only, not a complete user-authored identity schema |
| Another environment-specific question | Understand which required field is missing and answer only that field naturally |

`you` means the conversational counterpart actually addressed by the utterance, not a generic assistant. The compiler must not select the executor, the most recently drawn character, or the most frequent persona for convenience.

## 9. Family-specific validation

### BASE

Confirm that no image information enters and that scenes can vary while the semantic self remains fixed. Treat BASE as its own branch, not as the same file as ABYSS.

### LIVED-WORLD

Confirm that one atomic facet leads to one integrated concretization of world, action or stillness, and participation. The embodied state should be established before the camera.

### VISUAL-DRIFT

A clear initial test set is: text only, an object-centered image such as a meal, and an image containing another person. The self should remain the same while image-derived setting, clothing, props, background, action, composition, menu items, or other downstream features change.

### PHOTO MIXER

Confirm preservation of source aspect ratio, major objects, fine detail, readable text, products, light, and photographic character. Because action is chosen before placement, results should not collapse into the same standing or merely observing pose; the person should be able to interact causally with the photographed world.

### PHOTO MIXER CHIBI

Confirm approximately ten-centimeter embodiment, grounding, occlusion, and local contact. Serious, quiet, ordinary, playful, mischievous, hidden, edge-positioned, partially visible, and bustling behavior all remain eligible, but no single tone and no text are mandatory. If new handwriting appears, it should enact the chibi's action, reaction, or intention rather than describe the photograph.

## 10. Known cautions

- Repeated IMAGE OUTPUT calls in Chat may appear to reuse the first content from the second run onward. Use PROMPT OUTPUT or Work for comparative testing.
- If two exposed PROMPT OUTPUT prompts differ, do not explain identical direct outputs by assuming the prompts were identical.
- PHOTO MIXER prioritizes existing text fidelity, but exact glyph preservation cannot be guaranteed by a generative editor.
- Identity continuity comes from the frozen semantic self-image, not visual matching. Clothing may change freely, but apparent age direction, gender presentation, species, and mandatory anatomy cannot be silently rerolled.
- PHOTO MIXER imposes no named scale policy, whether natural, miniature, giant, or otherwise. The depicted self’s size is resolved from the source photograph’s perspective, object-scale anchors, depth, and selected placement. Only PHOTO MIXER CHIBI explicitly sets an approximately ten-centimeter scale.
