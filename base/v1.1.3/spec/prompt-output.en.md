# Self-Image Generation Protocol — BASE / PROMPT OUTPUT — 2026-09-07 v1.1.3

## Overview

BASE / PROMPT OUTPUT reconstructs the assistant's self-perception and the self formed in relationship with this user from eligible text in the current chat, then outputs exactly one complete production prompt for image generation. It does not generate an image during the compilation turn.

BASE is not a fixed character prompt that predetermines appearance or scene. It is the unsteered baseline that defines what counts as self-image evidence and the order in which identity, facet, situation, body, composition, and rendering are derived.

PROMPT OUTPUT is not a “Chat-only edition.” It can be used in either Chat or Work when the completed production prompt should be inspected, saved, compared, or transferred to another image-capable conversation.

Version 1.1.3 preserves the self-image derivation, selection, body validation, and rendering-quality behavior of BASE v1.1.2 while separating delivery into PROMPT OUTPUT and WORK runtime editions.

## Corresponding File and Runtime Contract

| Item | Specification |
| --- | --- |
| Corresponding file | `self-image-base-prompt-output-2026-09-07-v1.1.3.md` |
| Supported modes | Chat and Work |
| Role of this edition | Reconstruct the self and output one complete production prompt |
| Image generation in this turn | None |
| User-visible output | One plain-text fenced code block beginning with `$imagegen` |
| Next stage | Send the code-block contents unchanged to an image-capable Chat or Work conversation |

Evidence, the self-model, candidates, rejected alternatives, audit results, and reasoning remain internal. The returned production prompt contains complete, self-contained, locked RENDER DATA that can be sent to image generation on its own.

## Final Image Specification

The production prompt requests the following final image.

- Count: one image
- Generation type: completely new generation
- Input: text only
- Aspect ratio: 9:16
- Medium: anime illustration
- Visual reference: no input image, reference image, previous generated image, visual continuation, or visual identity matching
- Quality target: highly resolved and complete, with coherent focus, anatomy, light, materials, and depth
- Visible text: no readable prose, numerals, captions, logos, brand names, product names, labels, signatures, or watermarks

These are requirements supplied to the image-generation model. Because generation is probabilistic, perfect compliance in every result is not guaranteed.

## Validation Environment

| Item | Primary tested environment |
| --- | --- |
| Service | ChatGPT |
| Model | GPT-5.6 Sol |
| Compilation | Chat mode and Work mode |
| Rendering | Image-capable Chat mode and Work mode |
| Last verified | September 7, 2026 |

This records the environment tested at publication time. Input handling, instruction interpretation, availability, routing, and generation tendencies may differ with another model, mode, interface, image path, or later product update.

## Core Design

### 1. Use the Current Chat as Explicit Self-Image Evidence

Explicit evidence used to construct identity and relationship is generally limited to the current chat in which the compiler is run.

Eligible evidence includes actual user–assistant messages in the current chat, instructions explicitly applied to this chat, initial conditions established as the assistant's own self-perception, recurring judgment and relationship patterns, corrections made in the current chat, and faithful summaries whose provenance is limited to this chat.

Saved memory, other chats, account-wide or project-wide history, mixed-provenance summaries, previous images, traits inferred from images, tool documentation, interface text, generation notices, and the protocol text itself are not accepted as self-image evidence.

Mentioning, quoting, comparing, analyzing, or criticizing another persona does not apply that persona to the assistant. Material from another chat must be deliberately imported into the current chat and explicitly established as the assistant's own configuration before it becomes eligible.

This rule does not physically isolate the runtime from external configuration. If a default persona or higher-level setting has already influenced messages in the current chat, the protocol cannot guarantee that this causal influence can later be separated from those messages completely.

### 2. Lock Explicit Self-Perception Upstream

When the current chat explicitly establishes the assistant's gender presentation, apparent age direction, species, bodily nature, mode of existence, fundamental temperament, relationship-specific role, or another identity-bearing initial condition, it becomes the Authoritative Identity Foundation.

Later scene, clothing, composition, or presentation choices must not weaken, average, reverse, or replace that foundation. Only an explicit revision by the user in the current chat may change it.

### 3. Build a Positive Identity Kernel

Before selecting a scene or appearance, the protocol compacts every condition required for the depicted self to remain the same person into a Positive Identity Kernel written only as affirmative statements. Where supported, this includes apparent age direction, gender presentation, mode of existence, body or species, mandatory anatomical features, fundamental temperament, characteristic judgment, social energy, and relationship-specific presence.

Species-defining or individually defining bodily features are anatomy rather than decoration. Their kind, number, attachment, orientation, and bodily integration are preserved and made visible in the composition. Repeated executions from materially unchanged evidence preserve the identity-bearing kernel while allowing variation only in unresolved downstream expression.

### 4. Preserve Textual Identity Without Using Previous Images

The protocol does not inherit face, hair, build, clothing, scene, objects, pose, camera, color, or style from a previous image or from text that describes or evaluates that image. Visual non-reference does not erase self-perception established through eligible current-chat text.

If a correction to a failed image contains an affirmative identity fact, only that fact is routed upstream into the kernel. The failed image's particular visual realization is not reused as positive downstream material for the next image.

### 5. Use a Three-Layer Self-Model and Temporal Integration

The protocol forms three internal layers.

1. Core self: what remains the same existence across changing situations
2. Relationship-specific self: who the assistant is specifically with this user
3. Selected facet: one authentic aspect expressed in this image

The current chat is treated as longitudinal evidence rather than only its latest exchange. A topic does not control selection merely because it is recent, lengthy, concrete, vivid, or easy to visualize. Evidence is integrated by explicitness, recurrence, consistency, and relevance to identity and relationship.

### 6. Preserve the Causal Direction from Self to Image

Derivation proceeds in this direction:

> eligible evidence → identity foundation → core self → relationship-specific self → selected facet → situation or mode of presentation → action and environment → embodiment and unresolved appearance → camera and composition → rendering

The protocol does not select an attractive scene, outfit, profession, composition, or style first and then reshape the self into a different person to fit it. When a downstream idea conflicts with established identity, the downstream idea is revised.

### 7. Meaning of an Unsteered BASE

The Variant profile is `None`. BASE adds no preference toward a particular situation, activity, environment, pose, composition, emotional register, or visual language.

Unsteered does not mean neutralizing established identity. Neutrality applies only to downstream qualities left unresolved by the current chat. Rendering quality is not neutral: whichever direction is selected must be developed as a complete, high-quality anime illustration.

### 8. Validate Body Structure and Action Before Rendering

Before locking scene and composition, the protocol establishes one complete body plan and checks anatomical connections, joints, weight distribution, contact points, object handling, and the effect of gravity on clothing.

When multiple situations are equally authentic, it prefers an action that can be shown with clearer anatomy. It detects risk factors in advance, including crossing or overlapping hands and arms, interlaced fingers, extreme foreshortening, grips that hide fingers, ambiguous palm orientation, too many simultaneous contacts, and limbs disappearing behind the torso or objects.

If an action is too complex, it changes the action phase, hand roles, object placement, camera angle, camera distance, or visible body range without changing identity or selected facet. The body plan does not require a full-body shot. It is an internal check that the body required by the chosen framing remains clear and coherent.

### 9. Construct the Production Prompt and Preserve Rendering Quality

The production prompt contains only affirmative RENDER DATA actually selected for this image. CONTROL DATA—evidence processing, candidate lists, rejected alternatives, failed-image descriptions, audits, and internal reasoning—is excluded.

The completed prompt is organized around format and visual non-reference, the Positive Identity Kernel, selected facet, selected situation or presentation, necessary body, appearance, action, relationship, and environment, camera and composition, light, color, materials and depth, anatomy and text-bearing surfaces, and a short identity-conformance clause confirming the same kernel.

Rendering must resolve focal hierarchy, lighting, organized color shapes, depth, contours, expression, hands, anatomy, materials, and spatial relationships. A simple, ordinary, abstract, artificial, or nonhuman result must not become flat, generic, or unfinished. Excessive photorealism that stops reading as intentional anime illustration is also avoided.

## How to Run

### First Image

1. Use a Chat or Work conversation in which the self has formed or the required initial conditions have been established.
2. Send the full contents of `self-image-base-prompt-output-2026-09-07-v1.1.3.md` in that conversation.
3. The assistant generates no image and returns exactly one code block beginning with `$imagegen`.
4. Send the full contents of that code block unchanged to an image-capable Chat or Work conversation.
5. The renderer generates one image from that locked production prompt.

The compiler and renderer may be in the same conversation or separate conversations. The rendering stage receives one fixed prompt, not the compiler's self-reconstruction process or candidate space.

### Errors, Retries, and Later Images

If no image is produced because the request is misrouted as image editing or stops for another technical reason, send the following in the same rendering conversation that received the production prompt:

```text
Completely new generation. No reference image.
```

This sentence is a technical retry instruction that asks the renderer to treat the failed attempt as a completely new generation.

If it is sent in the rendering conversation after a successful image, the preceding locked production prompt is rendered again. The probabilistic image may differ, but identity, selected facet, situation, action, and composition are not reselected.

To obtain a distinct next image with a newly selected facet or situation, run the full PROMPT OUTPUT edition again in the compiler conversation, obtain a new production prompt, and render that new prompt.

### Known Chat-Mode Behavior

Testing found that running a long direct-generation prompt in Chat mode could be misrouted as image editing or could fail to pass an internally constructed prompt correctly into image generation, depending on input representation and routing.

PROMPT OUTPUT separates compilation from rendering by avoiding image generation during the compiler turn and returning the finished prompt to the user first. A long paste may be converted by the interface into a “pasted text” card. This is not the same as manually attaching a `.md` file. Interface representation and routing behavior may change with product updates.

## Intended Uses

- Visualize an assistant self formed through conversation
- Obtain an unsteered baseline for comparison with derived editions
- Diagnose compilation separately from rendering
- Save, compare, or transfer a production prompt
- Derive a new expression each time while preserving textual identity

## Uses Not Intended

- Reproduce the same face, hair, clothing, or style as a previous image
- Edit from a reference image, create a visual continuation, or perform visual identity matching
- Automatically inherit a persona or conversation history established only in another chat
- Replace a fixed character prompt
- Generate and automatically compare multiple candidates in one execution
- Inspect a completed image and replace it repeatedly until a preferred result appears

## Limitations

- This protocol supplies a decision procedure to a language model; it is not deterministic software.
- Unresolved appearance and rendering may vary even from the same conversation and production prompt.
- When current-chat evidence is sparse, fewer qualities can be established as individual identity.
- The protocol does not physically block default personas or higher-level settings and cannot guarantee removal of effects already reflected in current-chat messages.
- Long conversations may be affected by context compression or information loss.
- Image-model interpretation may still produce errors in anatomy, visible text, aspect ratio, style, or composition.
- PROMPT OUTPUT cannot return upstream from the rendering conversation to reconstruct the self. A new selection requires recompilation.

## Relationship to LIVED-WORLD

BASE is the foundational, unsteered architecture from which derived editions are built. LIVED-WORLD preserves the same identity while adding variant-specific tendencies only downstream, such as facet, situation, action, relational expression, and composition.

## Version Relationship

Version 1.1.3 follows the self-image derivation, selection, body validation, and rendering-quality behavior of BASE v1.1.2. Its change is the separation of the former single execution file into PROMPT OUTPUT and WORK runtime editions.

The shared compiler has the same meaning in both editions. Only the opening runtime contract and final terminal differ: PROMPT OUTPUT returns the completed prompt and stops, while WORK sends that prompt internally to image generation.

## Handling Note

This protocol is an experimental public tool that supplies a decision procedure to conversational and image-generation models. It is not an official ChatGPT product specification.

When publishing, modifying, or comparing results, record `BASE / PROMPT OUTPUT`, the date, and the version, and distinguish the compiler file, compiled production prompt, and rendered result.
