# Self-Image BASE — Specification Sheet

## Document metadata

| Field | Value |
| --- | --- |
| Product | Self-Image BASE |
| Version | 2026-09-19 v2.0.0-rc1 |
| Status | Release Candidate 1 |
| Language | English |
| Included terminals | PROMPT OUTPUT / IMAGE OUTPUT |
| Intended environments | PROMPT OUTPUT: Chat / Work; IMAGE OUTPUT: image-capable Work |
| PROMPT OUTPUT canonical compiler | `self-image-base-prompt-output-2026-09-19-v2.0.0-rc1.md` |
| IMAGE OUTPUT canonical compiler | `self-image-base-image-output-2026-09-19-v2.0.0-rc1.md` |
| Common usage guide | `self-image-common-usage-guide-2026-09-19-v2.0.0-rc1-en.md` |

## Purpose

The baseline variant freezes the conversational counterpart's already-formed self-image as a minimal positive identity packet, then freely realizes one coherent image without losing that self.

This sheet treats one functional family as the specification unit and contains both the shared behavior and terminal differences of PROMPT OUTPUT and IMAGE OUTPUT. It is an external specification for use, validation, and acceptance rather than a replacement for the canonical compilers.

## Lineage and responsibility

An independent release line adopted from ABYSS v2.0.0-ex2 at the branch point. ABYSS and BASE do not update one another automatically; any later transfer must be deliberate.

## Required inputs

- The current invocation and eligible outer conversation after embedded artifacts have been excluded.
- No image input. Attachments, earlier images, generated images, and remembered images are not consulted.
- If the target alone is ambiguous, one question may ask only who should be depicted.

## Shared self-image core

- Resolve exactly one depicted self from the current dialogue act. `you`, `yourself`, あなた, 君自身, and equivalents refer to the conversational counterpart actually addressed by that utterance.
- Acquire the target's already-active self-image as primary authority. Conversation may supplement it but cannot average it with or replace it by another persona.
- Excise earlier $imagegen and renderer-facing prompt payloads as opaque data before conversation supplementation; do not inspect or reuse their contents.
- Quarantine praise, criticism, diagnosis, and correction of prior depictions as depiction reports. A rendered trait does not become identity unless the target explicitly adopts it.
- Abstract protected personal information into relationship-preserving roles. Do not serialize real names, addresses, workplaces, contact details, credentials, or private schedules.
- Build a minimal positive self packet and marked-anatomy allowlist, then freeze target, embodiment, and identity before scene realization.
- After the freeze, no scene, image, style, clothing decision, or renderer prior may substitute another identity.

If more than one target remains possible, the compiler asks one concise question only about who should be depicted. It must not force the user to restate name, age direction, gender presentation, and embodiment fields already available. A short answer fills only the missing field within the same invocation.

## Image authority

- Visual-reference authority is zero. No image may determine the face, body, clothing, setting, or composition.
- The face and unresolved appearance are freshly authored within the frozen self-image.
- Semantic identity continuity is preserved without pixel matching, face matching, or continuation from an earlier output.

## Scene, action, and composition

- Scene, place, time, action or stillness, pose, gaze, clothing, props, composition, camera, lighting, palette, and atmosphere remain open except for identity and single-image coherence.
- The core imposes no natural, miniature, giant, or other body-to-world scale policy. An unspecified scale resolves normally within the selected scene.
- The image does not have to prove intelligence or relationship through inspecting, explaining, pointing, or looking at the viewer.

## Rendering and preservation

- The default result is a completely new 9:16 Japanese anime illustration.
- A premium line-and-color-shape-led finish keeps the character anime-native rather than photographic or 3D-asset-like.
- By default, no new readable text, logo, signature, or watermark is introduced.

## Terminal structure

| Item | PROMPT OUTPUT | IMAGE OUTPUT |
| --- | --- | --- |
| Returns | One completed English `$imagegen` prompt | One completely newly generated image |
| Prompt | Visible in one code fence | Kept internal and hidden |
| Image tool | Not called | Called exactly once |
| Recommended environment | Chat / Work | Image-capable Work |
| Image handoff | No image input or handoff | No image input or handoff |
| Repeated Chat use | Suitable for comparative tests | Later runs may appear to reuse the first content |

## PROMPT OUTPUT terminal contract

- Return exactly one complete English $imagegen prompt inside one code fence.
- Do not add a heading, explanation, alternatives, or generated image before or after the prompt.
- Keep target resolution, self-image acquisition, candidates, audits, and repairs internal.

## IMAGE OUTPUT terminal contract

- On success, return exactly one image and stop. No preparation, title, caption, or post-generation commentary is added.
- A technical retry is allowed only when the preceding attempt produced no image at all, never to seek a preferred variation.
- After completion, invocation-scoped prompt and execution state are disposed of as non-reusable.

## Canonical execution flow

1. Bind the terminal mode and receive the current invocation plus eligible conversation.
2. Separate outer enacted dialogue from embedded artifacts and excise prior production-prompt payloads without residue.
3. Resolve the target from the actual address relation.
4. Quarantine depiction reports and abstract private information before acquiring the target's established self-image and applying bounded conversation supplementation.
5. Freeze the minimal positive self packet, mandatory embodiment, and marked anatomy.
6. free single-scene realization → image profile
7. Audit identity, privacy, physical coherence, image authority, and output format; repair only the nearest failing stage.
8. Follow the selected terminal: PROMPT OUTPUT returns exactly one completed prompt, while IMAGE OUTPUT makes one image call and returns exactly one image.

## Quick use

### PROMPT OUTPUT

1. Run the compiler without attaching an image.
2. If a clarification asks who should be depicted, answer only that missing field.
3. Submit the returned $imagegen prompt from the code fence to the later image step.
4. No visual-input handoff is needed.

### IMAGE OUTPUT

1. In Work, run the compiler without attaching an image.
2. If a clarification asks who should be depicted, answer only that missing field.
3. Wait for internal compilation and the single image call.
4. Treat the returned image as the result; do not request another variation from the same invocation.

## Constraints and known behavior

### PROMPT OUTPUT

- For image-dependent variants, the pixels inspected while compiling the prompt are not guaranteed to travel automatically with the prompt into the later rendering step.
- If the later step asks for the same image and it is still visible, answer `Use the image above.`; otherwise reattach it.
- Only when a text-only new generation is mistakenly treated as an edit, use `Completely new generation. No reference image.` Never use that recovery for PHOTO MIXER variants.

### IMAGE OUTPUT

- This mode is operationally Work-oriented. In Chat, the first run may work but later runs can appear to reuse the first prompt or image and produce the same result.
- The internal cause is not claimed to be a confirmed cache; treat it as a known Chat direct-execution state limitation. Use PROMPT OUTPUT for repeated Chat tests.
- A clarification may still ask for an ambiguous target or required image; the answer continues the same invocation.

## Recommended use

Use when the self-image should be the only fixed semantic core and the model may freely choose the world and event.

## Not recommended

Do not use for direct photo editing, visual drift from an image, approximately ten-centimeter chibi integration, or LIVED-WORLD atomic-facet control.

## Acceptance criteria

### Shared

- Exactly one depicted self is resolved from the current utterance, without substitution by another conversational persona, the compiler executor, or a person in an earlier image.
- No unauthorized body trait or personality enters from an earlier generation prompt, depiction report, or person visible in an image.
- Relationship meaning needed for the self-image remains available while protected personal information is neither serialized nor visibly encoded.
- The result is a visually unreferenced, completely new 9:16 illustration whose freely chosen moment remains physically coherent with the frozen self.

### PROMPT OUTPUT

- No image tool is called, and exactly one complete $imagegen prompt is returned in a code fence.

### IMAGE OUTPUT

- The frozen prompt is not exposed, exactly one image call is made, and only one image is returned after success.

## Related operations

For two-stage image handoff, Chat-versus-Work behavior, recovery phrases, and variant selection, see `self-image-common-usage-guide-2026-09-19-v2.0.0-rc1-en.md`.
