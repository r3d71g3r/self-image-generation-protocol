# Self-Image LIVED-WORLD — Specification Sheet

## Document metadata

| Field | Value |
| --- | --- |
| Product | Self-Image LIVED-WORLD |
| Version | 2026-09-19 v2.0.0-rc1 |
| Status | Release Candidate 1 |
| Language | English |
| Included terminals | PROMPT OUTPUT / IMAGE OUTPUT |
| Intended environments | PROMPT OUTPUT: Chat / Work; IMAGE OUTPUT: image-capable Work |
| PROMPT OUTPUT canonical compiler | `self-image-lived-world-prompt-output-2026-09-19-v2.0.0-rc1.md` |
| IMAGE OUTPUT canonical compiler | `self-image-lived-world-image-output-2026-09-19-v2.0.0-rc1.md` |
| Common usage guide | `self-image-common-usage-guide-2026-09-19-v2.0.0-rc1-en.md` |

## Purpose

This text-only derived variant selects one temporary atomic facet of the frozen self and organically concretizes, in one pass, a world, event, action, or still state in which that facet can naturally exist.

This sheet treats one functional family as the specification unit and contains both the shared behavior and terminal differences of PROMPT OUTPUT and IMAGE OUTPUT. It is an external specification for use, validation, and acceptance rather than a replacement for the canonical compilers.

## Lineage and responsibility

Inherits the BASE v2.0.0-rc1 self-image core and adds one temporary atomic facet plus LIVED-WORLD organic concretization.

## Required inputs

- The current invocation and eligible outer conversation after embedded artifacts have been excluded.
- No image input is used. Earlier generated results are not visual references.
- If only the target is ambiguous, one question may ask who should be depicted.

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

- Complete visual non-reference: image availability, recency, appeal, and past success provide no visual information.
- The face and unresolved appearance are freshly designed within the frozen self-image.
- The atomic facet is a temporary angle of expression, not a second persona or a permanent identity addition.

## Scene, action, and composition

- After the self-image freezes, exactly one temporary atomic facet is selected.
- Scene, world, event, action or stillness, and participation are concretized together in one pass without enumerating or scoring candidate menus.
- Embodied state, support, contact, balance, motion, and clothing response are established before camera and composition.
- Novelty and randomness are not quantified; the selected present instant only needs to exist naturally.

## Rendering and preservation

- The default result is a completely new 9:16 Japanese anime illustration.
- Character and environment share one coherent illustrative hand with organized depth and material separation.
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
6. one atomic facet → one-pass organic concretization → embodied state → camera → image profile
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

Use when the system should draw a lived moment from the self-image and resolve world and action as one organic state.

## Not recommended

Do not use when imagery should influence the world or when the result must edit an existing photograph.

## Acceptance criteria

### Shared

- Exactly one depicted self is resolved from the current utterance, without substitution by another conversational persona, the compiler executor, or a person in an earlier image.
- No unauthorized body trait or personality enters from an earlier generation prompt, depiction report, or person visible in an image.
- Relationship meaning needed for the self-image remains available while protected personal information is neither serialized nor visibly encoded.
- One atomic facet produces one organically concretized world state, with embodied state established before camera.

### PROMPT OUTPUT

- No image tool is called, and exactly one complete $imagegen prompt is returned in a code fence.

### IMAGE OUTPUT

- The frozen prompt is not exposed, exactly one image call is made, and only one image is returned after success.

## Related operations

For two-stage image handoff, Chat-versus-Work behavior, recovery phrases, and variant selection, see `self-image-common-usage-guide-2026-09-19-v2.0.0-rc1-en.md`.
