# Self-Image PHOTO MIXER CHIBI — Specification Sheet

## Document metadata

| Field | Value |
| --- | --- |
| Product | Self-Image PHOTO MIXER CHIBI |
| Version | 2026-09-19 v2.0.0-rc1 |
| Status | Release Candidate 1 |
| Language | English |
| Included terminals | PROMPT OUTPUT / IMAGE OUTPUT |
| Intended environments | PROMPT OUTPUT: Chat / Work; IMAGE OUTPUT: image-capable Work |
| PROMPT OUTPUT canonical compiler | `self-image-photo-mixer-chibi-prompt-output-2026-09-19-v2.0.0-rc1.md` |
| IMAGE OUTPUT canonical compiler | `self-image-photo-mixer-chibi-image-output-2026-09-19-v2.0.0-rc1.md` |
| Common usage guide | `self-image-common-usage-guide-2026-09-19-v2.0.0-rc1-en.md` |

## Purpose

This direct photo-editing variant preserves one attached photograph while integrating the target self as exactly one living, approximately ten-centimeter anime chibi. Serious presence, ordinary activity, playful interference, hiding, and bustling mischief all remain within one continuous range.

This sheet treats one functional family as the specification unit and contains both the shared behavior and terminal differences of PROMPT OUTPUT and IMAGE OUTPUT. It is an external specification for use, validation, and acceptance rather than a replacement for the canonical compilers.

## Lineage and responsibility

Extends PHOTO MIXER photo-preservation discipline with an approximately ten-centimeter living chibi embodiment, a wide behavioral range, and optional action-bound additions.

## Required inputs

- The current invocation and eligible outer conversation after embedded artifacts have been excluded.
- Exactly one photograph attached to the same invocation. Earlier or generated images cannot substitute for it.
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

- The attached photograph is the sole scene and edit base and defines aspect ratio, objects, food, text, light, materials, and perspective.
- Any person or face in the photograph cannot define the chibi self's face, body, or identity.
- Existing photographic content is preserved, with only local changes required by chibi contact.
- Existing readable text is retained. The optional target-owned micro-expression described below is the only normal exception for new text-like marks.

## Scene, action, and composition

- After the self and approximately ten-centimeter transformation freeze, one atomic facet is fixed before the photograph is inspected for content. The whole photograph is then read, one action or still state is selected across the full behavioral range, optional additions are resolved, and only then is local placement determined.
- The target becomes one living approximately ten-centimeter chibi. Smallness is a variant-specific embodiment scale, not a replacement identity.
- Quiet observation, serious work, ordinary presence, play, mischief, peeking from behind an object, edge activity, partial concealment, and lively bustling are all eligible; none is mandatory.
- Center placement and full-body visibility are not required. Spatially correct partial occlusion, including only a face peeking from behind an object, is allowed.
- A small action-bound prop or material addition may be introduced. One or two short target-owned handwritten phrase fragments, hearts, or marks may also appear when they perform or react to the action rather than describe the photograph. They are optional, never compulsory.

## Rendering and preservation

- The source aspect ratio, orientation, camera, and high-detail photographic character are retained.
- Only the added chibi is rendered as Japanese anime; the photographic world is not redrawn.
- Existing text remains legible, and no new captions, speech balloons, signatures, or watermarks are added beyond an optional action-bound micro-expression.

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
6. approximately ten-centimeter embodiment adaptation → one atomic facet → whole-photo analysis → state selection across the full behavior range → optional-addition freeze → local preservation record → placement and occlusion → photo-preserving render
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

Use when an approximately ten-centimeter self should interact freely with food, dishes, desks, machines, vegetation, or everyday objects in a photograph.

## Not recommended

Do not use for character integration that does not call for an approximately ten-centimeter chibi, a completely new world, or a requirement that every image contain text or noisy behavior.

## Acceptance criteria

### Shared

- Exactly one depicted self is resolved from the current utterance, without substitution by another conversational persona, the compiler executor, or a person in an earlier image.
- No unauthorized body trait or personality enters from an earlier generation prompt, depiction report, or person visible in an image.
- Relationship meaning needed for the self-image remains available while protected personal information is neither serialized nor visibly encoded.
- The concurrent photograph remains intact while exactly one living approximately ten-centimeter chibi self is integrated in a free but causally coherent state.

### PROMPT OUTPUT

- No image tool is called, and exactly one complete $imagegen prompt is returned in a code fence.

### IMAGE OUTPUT

- The frozen prompt is not exposed, exactly one image call is made, and only one image is returned after success.

## Related operations

For two-stage image handoff, Chat-versus-Work behavior, recovery phrases, and variant selection, see `self-image-common-usage-guide-2026-09-19-v2.0.0-rc1-en.md`.
