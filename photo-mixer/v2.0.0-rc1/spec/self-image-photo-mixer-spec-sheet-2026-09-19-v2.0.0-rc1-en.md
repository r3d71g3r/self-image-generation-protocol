# Self-Image PHOTO MIXER — Specification Sheet

## Document metadata

| Field | Value |
| --- | --- |
| Product | Self-Image PHOTO MIXER |
| Version | 2026-09-19 v2.0.0-rc1 |
| Status | Release Candidate 1 |
| Language | English |
| Included terminals | PROMPT OUTPUT / IMAGE OUTPUT |
| Intended environments | PROMPT OUTPUT: Chat / Work; IMAGE OUTPUT: image-capable Work |
| PROMPT OUTPUT canonical compiler | `self-image-photo-mixer-prompt-output-2026-09-19-v2.0.0-rc1.md` |
| IMAGE OUTPUT canonical compiler | `self-image-photo-mixer-image-output-2026-09-19-v2.0.0-rc1.md` |
| Common usage guide | `self-image-common-usage-guide-2026-09-19-v2.0.0-rc1-en.md` |

## Purpose

This direct photo-editing variant preserves one high-detail real-world photograph as far as possible and integrates exactly one anime depiction of the target self as a physically present person in that space.

This sheet treats one functional family as the specification unit and contains both the shared behavior and terminal differences of PROMPT OUTPUT and IMAGE OUTPUT. It is an external specification for use, validation, and acceptance rather than a replacement for the canonical compilers.

## Lineage and responsibility

Inherits the BASE v2.0.0-rc1 self-image core and LIVED-WORLD atomic-facet discipline, with exactly one concurrently attached photograph as the sole edit source.

## Required inputs

- The current invocation and eligible outer conversation after embedded artifacts have been excluded.
- Exactly one photograph attached to the same invocation. An earlier image, another attachment, a generated image, or internal memory cannot substitute for it.
- If only the target or source photograph is missing or ambiguous, one question asks only for that missing field.

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

- The attached photograph is the sole authority for scene, space, objects, materials, light, text surfaces, perspective, and aspect ratio, and is the direct edit base.
- Any person or face already in the photograph does not supply the added self's face, body, or identity.
- The added self's face and unresolved appearance are freshly authored from the frozen self-image.
- Existing Japanese or other text, numerals, logos, product labels, and signs are preserved in their source positions and legibility as accurately as possible.

## Scene, action, and composition

- After identity and embodiment freeze, one atomic facet is fixed before the photograph is inspected for content.
- The whole photograph is then read for principal subjects, broad spatial structure, support surfaces, depth, light, text surfaces, protected detail, and action possibilities.
- A photograph-causal action or still state is fixed before local-object salience, empty-space ranking, editing ease, or exact placement can bias it. Placement is a consequence of action, not its substitute.
- Exactly one anime character is added. No body-scale default is imposed; size is resolved from the photograph's perspective, object scale anchors, spatial depth, and placement.
- Changes are bounded to required contact, occlusion, shadow, and local object response; the photograph is not globally redrawn.

## Rendering and preservation

- The source aspect ratio, orientation, camera position, and photographic material character are retained.
- Only the added character is rendered as Japanese anime; the photographic world remains photographic.
- No new caption, speech balloon, signature, watermark, or unrelated decorative text is added.

## Terminal structure

| Item | PROMPT OUTPUT | IMAGE OUTPUT |
| --- | --- | --- |
| Returns | One completed English `$imagegen` prompt | One edited image |
| Prompt | Visible in one code fence | Kept internal and hidden |
| Image tool | Not called | Called exactly once |
| Recommended environment | Chat / Work | Image-capable Work |
| Image handoff | The same source photograph may need to be re-presented in the later step | The concurrently attached source photograph is passed within the same invocation |
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
6. one atomic facet → whole-photo analysis → action freeze → local preservation record → placement and contact plan → photo-preserving render
7. Audit identity, privacy, physical coherence, image authority, and output format; repair only the nearest failing stage.
8. Follow the selected terminal: PROMPT OUTPUT returns exactly one completed prompt, while IMAGE OUTPUT makes one image call and returns exactly one image.

## Quick use

### PROMPT OUTPUT

1. Attach exactly one source photograph to this invocation and run the compiler.
2. If a clarification asks for the target or source photograph, answer only the missing field.
3. Submit the returned $imagegen prompt from the code fence to the later image step.
4. Make the same source photograph available to the later image-editing step; re-present or reattach it if asked.

### IMAGE OUTPUT

1. In Work, attach exactly one source photograph to this invocation and run the compiler.
2. If a clarification asks for the target or source photograph, answer only the missing field.
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

Use to integrate one depicted self into a real meal, street, room, machine, or other photograph, with size determined by that scene's perspective and placement rather than a scale default.

## Not recommended

Do not use for a completely new world, image-inspired drift, or an approximately ten-centimeter chibi.

## Acceptance criteria

### Shared

- Exactly one depicted self is resolved from the current utterance, without substitution by another conversational persona, the compiler executor, or a person in an earlier image.
- No unauthorized body trait or personality enters from an earlier generation prompt, depiction report, or person visible in an image.
- Relationship meaning needed for the self-image remains available while protected personal information is neither serialized nor visibly encoded.
- The concurrent photograph remains the sole edit base, and exactly one anime character is physically integrated at a size consistent with its perspective and placement.

### PROMPT OUTPUT

- No image tool is called, and exactly one complete $imagegen prompt is returned in a code fence.

### IMAGE OUTPUT

- The frozen prompt is not exposed, exactly one image call is made, and only one image is returned after success.

## Related operations

For two-stage image handoff, Chat-versus-Work behavior, recovery phrases, and variant selection, see `self-image-common-usage-guide-2026-09-19-v2.0.0-rc1-en.md`.
