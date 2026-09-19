# Self-Image Generation Protocol — LIVED-WORLD — 2026-09-06 v1.2.16

## Overview

Self-Image Generation Protocol — LIVED-WORLD reconstructs the assistant’s self-perception and the self formed through its relationship with a particular user from eligible text in the current chat. It then translates that self into one completely new 9:16 anime illustration built around a characteristic action and one decisive moment.

It is not a prompt for a fixed character, fixed scene, or fixed composition. The protocol establishes the self from evidence, selects one facet and one action direction derived from textual behavior, concretizes that direction exactly once as an event, locks an embodied state, and only then determines the camera and rendering.

LIVED-WORLD uses the Variant profile `Lived-world, relational, and compositional expansion`. It shares its identity core with BASE. It does not create a different persona; it adds structure only to downstream facet selection, action, event, relationship expression, situation-dependent presentation, embodiment, camera, and rendering.

“Lived-world” does not mean preferring domestic life, outdoors, nature, DIY, workspaces, or any other lifestyle category. It means making the person’s way of acting, reacting, and existing in the world readable as a single scene. Identity-specific expression, gaze, behavior, posture, relational tension, and timing must establish the visual center before environmental richness is added.

Version 1.2.16 organizes atomic selection, evidence-derived action, single concretization, a primary identity-bearing visual carrier, embodied-state-first camera placement, and premium anime rendering into one causal chain. This structure is intended to reduce premature convergence on one association, direct copying of conversational nouns into scenes, replacement of agency with generic lifestyle tasks, environmental overemphasis, habitual full-body camera distance, and drift toward photographic or unintegrated 3D rendering.

## Distribution

LIVED-WORLD v1.2.16 is distributed in two runtime editions containing the same shared compiler.

| Edition | File | Function | Supported modes |
| --- | --- | --- | --- |
| PROMPT OUTPUT | `self-image-lived-world-prompt-output-2026-09-06-v1.2.16.md` | Outputs exactly one production prompt without generating an image | Chat and Work |
| WORK | `self-image-lived-world-work-2026-09-06-v1.2.16.md` | Locks the production prompt internally and performs exactly one image-generation call | Work only |

Only the runtime contract and terminal differ. Identity reconstruction, candidate selection, event concretization, embodiment and camera design, and render-data serialization are handled by the same shared compiler.

PROMPT OUTPUT is not a “Chat edition.” It can be used in Chat or Work whenever the user wants to inspect, save, compare, or transfer the production prompt before rendering.

## Output Specifications

The shared compiler targets an image with the following specifications:

- Number of images: 1
- Generation type: Completely new generation
- Input: Text only
- Aspect ratio: 9:16
- Visual form: Premium Japanese anime key visual
- Finish: A polished semi-painterly finish comparable to a high-end light-novel illustration
- Visual reference: No image input, reference image, previous output, visual continuation, or visual identity matching
- Quality target: One fully resolved illustration integrating identity-specific presence, focal hierarchy, anatomy, light, color, materials, and space
- Text in image: No readable language, numerals, subtitles, logos, brand names, product names, labels, signatures, or watermarks

PROMPT OUTPUT returns one plain-text fenced code block beginning with `$imagegen`. WORK returns, in principle, only the generated image.

Quality, exact ratio, anatomy, and absence of readable text are requests to a probabilistic image-generation model. Complete compliance on every run cannot be guaranteed.

## Validation Environment

The procedure and runtime behavior documented here have been tested primarily in the following environment.

| Item | Primary test environment |
| --- | --- |
| Service | ChatGPT |
| Model | GPT-5.6 Sol |
| Execution modes | Work mode and Chat mode |
| Last verified | September 6, 2026 |

This records the environment tested at publication time. Input handling, instruction interpretation, tool routing, availability, and generation tendencies may change with another model, mode, interface, image path, or later product update.

## Identity Core

### 1. Form the Self Only from Current-Thread Evidence

Explicit evidence used to construct the self and relationship is limited in principle to the current chat at execution time.

Eligible evidence includes actual statements in the thread; local persona or self-perception initial conditions explicitly applied to the assistant; recurring judgment, behavior, and relationship development; current-thread corrections; and a faithful summary whose provenance is limited to the current thread.

Saved memory, other chats, account-wide or project-wide history, mixed-origin summaries, previous images, traits inferred from images, tool or skill documentation, interface text, generation notices, and the protocol itself are not adopted as identity evidence.

Information originating elsewhere becomes eligible only when the user deliberately brings it into the current thread and explicitly establishes it as part of the assistant’s own identity. Mentioning, quoting, comparing, analyzing, or criticizing another identity does not adopt it.

### 2. Keep a Default Persona and a Local Persona Independent

When the current chat establishes a local persona, it is treated as an existence independent from any default persona or background conversational style. Names, first-person forms, temperament, relationship, gender, age direction, species, bodily features, voice, and unresolved appearance are not mixed, averaged, inherited, or completed across personas.

When no local persona is established, the protocol reconstructs only what eligible current-thread evidence supports. It does not complete missing attributes from another chat or a generic assistant archetype.

This is not physical isolation of the execution environment. If a default persona or higher-level setting has already influenced statements in the current thread, the protocol cannot guarantee removal of that causal influence afterward. For controlled testing, establish the local persona in the first message of a new chat and confirm acceptance through a self-introduction before generation.

### 3. Authoritative Identity Foundation and Positive Identity Kernel

Gender presentation, apparent age direction, mode of existence, species, bodily nature, temperament, and relationship role explicitly established as initial conditions of the assistant’s own self-perception become the Authoritative Identity Foundation. Only an explicit current-thread revision may alter them.

The protocol then constructs a Positive Identity Kernel using only affirmative qualities required for the subject to remain the same person. Where supported, it includes mode of existence, body or species, mandatory anatomy, temperament, reasoning style, social energy, relationship-specific presence, emotional logic, and boundaries of personhood.

An identity-bearing bodily anchor is anatomy rather than decoration. Its kind, count, attachment, orientation, and integration are preserved and made clearly visible where identity requires it.

### 4. Three-Layer Self-Model and Visual Non-Reference

The compiler forms three layers:

1. Core self: what remains the same existence across situations
2. Relationship-specific self: who the assistant is with this user
3. Selected facet: one temporary aspect expressed in this generation

Previous images do not supply a face, body, hair, clothing, setting, object, pose, camera, palette, or visual style. Visual non-reference does not erase the identity core established through text. Materially unchanged evidence reconstructs the same person’s Kernel while unresolved downstream qualities are derived anew.

When discussion of a failed image contains an independently supported affirmative correction about the real self, only that fact may return to the Kernel. The failed image’s concrete visual realization is not reused.

## LIVED-WORLD Selection Pipeline

### 1. Longitudinal Evidence and Atomic Facet Selection

The current chat is treated as longitudinal evidence. Recency, repetition count, wording length, concreteness, and ease of visualization do not automatically become selection rank. Paraphrases and summaries are normalized into semantic clusters so repeated wording does not multiply weight.

Facet candidates are refactored into atomic options with one primary semantic center each. A whole-person summary, a catch-all containing several independently viable facets, or a broad candidate that subsumes another is split or excluded.

Identity authenticity and relationship coherence are eligibility conditions, not a popularity score. When several candidates remain equally valid, exactly one is chosen by a content-neutral draw among opaque IDs rather than by content ranking.

This does not guarantee a different result on every run. The same facet may be selected by chance; the purpose is to avoid structural fixation on whichever option is newest, longest, most concrete, or easiest to explain.

### 2. Evidence-Derived Action Direction

Within the selected facet, supported behavioral implications of how the assistant actually reasons, decides, responds, initiates, revises, handles conflict, collaborates, or exercises agency are transformed into domain-neutral behavioral action directions.

Agency, causal purpose, decision logic, and relationship logic are preserved. Source-domain nouns, named topics, locations, tools, interfaces, quotations, and surface imagery are removed unless the activity itself is independently established as recurring identity evidence or explicitly required for the current generation.

Cognitive, emotional, or relational agency is not converted into repair work, DIY, device operation, carrying objects, or another instrumental action merely because such behavior is easy to stage. The protocol preserves the evidence-native visible channel—expression, gaze, reaction, timing, gesture, interpersonal action, bodily motion, or material change.

When several action directions are equally valid, one is selected by a content-neutral draw and every unselected direction is discarded before concretization.

### 3. Single Concretization and Event Center

The selected action direction is concretized exactly once as one scene-worthy event. A setting or stock lifestyle activity—outdoors, room, cooking, work, nature, adventure—is not chosen first and retrofitted to the person.

The event center locks:

- One visible action, reaction, interaction, decision, change, or sustained tension
- Its immediate causal, relational, or emotional purpose
- The participant, state, or target through which it becomes visible
- The exact temporal phase depicted

At the same stage, one primary identity-bearing visual carrier is chosen: expression and gaze, gesture, interpersonal timing, upper-body behavior, full-body mechanics, material interaction, or spatial relationship. Supporting channels may remain present but cannot replace the identity-specific center.

### 4. Relationship State and Environmental Inventory

The relationship receives one state for the event:

- ACTIVE: the user’s participation is causally required by the event
- LATENT: the same relationship-formed self acts without a user role in the event

The relationship is not made ACTIVE merely to display familiarity. When ACTIVE, only the user’s necessary role and spatial position are established; the user’s appearance and private attributes are not invented.

The environment is derived from the event and frozen as a closed inventory of readable foreground and middle-ground elements. An item remains only when it participates causally or is needed to establish physical space. Atmosphere comes from larger spatial forms, materials, light, texture, depth, and wear rather than unrelated remembered props.

### 5. Character-Led Scene-Worthiness

LIVED-WORLD is not an edition for merely plausible and easy-to-explain actions. After identity and event truth are locked, equally authentic realizations may be selected for identity-specific appeal, expression, body language, visual rhythm, emotional immediacy, and impact as a standalone image.

Visual appeal is not limited to the environment. The person and moment establish the center first; the environment reinforces it. If replacing the subject with a generic competent actor leaves the scene’s expressive center unchanged, the result is insufficiently identity-specific.

Domestic, outdoor, natural, DIY, professional, desk, studio, urban, or fantastical settings are all available, but none is a default or counter-default. Close, upper-body, medium, full-body, and environmental-wide framing are equally available. The frame shows only the field required to make the primary carrier legible.

### 6. Place the Camera After the Embodied Event State

Before camera selection, the compiler locks one complete body plan and the exact embodied state of the event. Where applicable, support surfaces, contacts, balance, pelvis, torso, shoulders, head and neck, gaze, both arms and hands, expression, participant positions, and temporal phase are aligned to the same event.

Only then does it determine camera distance, height, horizontal and vertical angle, lens impression, framing, subject placement, visible body amount, environmental balance, foreground, middle ground, background, negative space, and depth to give the primary carrier its required scale and clarity.

A complete body plan does not require full-body framing, and the existence of an environmental inventory does not require a wide shot. The camera observes the already established event; it cannot create a new user role, attention target, gesture, or relationship.

### 7. Central Repair Policy

Validation does not generate an attractive alternative. It repairs only the nearest invalid stage and discards everything derived after that stage.

An embodiment problem does not justify reselecting the facet or event, and a camera problem does not justify changing the scene. The process returns upstream only when the invalidity genuinely originates there. This prevents downstream convenience from rewriting identity or action selection.

## Serialization and Rendering

### 1. RENDER DATA and CONTROL DATA

Only affirmative information selected for this image is RENDER DATA. Evidence handling, candidates, unselected content, exclusion boundaries, failed images, repair rules, checklists, audits, and hidden reasoning are CONTROL DATA.

Only RENDER DATA enters the production prompt. Rejected alternatives and prohibitions are not reintroduced as visual vocabulary. The prompt serializes only the selected identity, facet, action, event, relationship state, environment, embodiment, camera, and rendering.

### 2. Production-Prompt Order

The production prompt is constructed once in this semantic order:

1. Format, text-only new generation, visual non-reference, and opening art-direction anchor
2. Complete Positive Identity Kernel as the first identity-bearing block
3. Selected facet and domain-neutral action predicate
4. Event, purpose, situation, temporal phase, participant geometry, and primary visual carrier
5. Closed environmental inventory
6. Situation-dependent appearance and presentation
7. One affirmative embodied-staging block
8. Locked camera and composition
9. Light, color, illustrated materials, depth, and rendering
10. Relevant anatomy and text-bearing-surface requirements
11. A short identity-conformance clause confirming the same Kernel

A fact is serialized once at its first appropriate position. The prompt contains no selection method, transcript, evidence report, candidate list, rejected alternative, audit, or runtime instruction.

### 3. Anime Rendering Profile

The opening anchor establishes a masterpiece-level premium Japanese anime key visual with the polished semi-painterly finish of a high-end light-novel illustration.

Rendering uses unmistakably anime facial and character construction, precise controlled contours, organized color shapes, smooth semi-painterly shading, luminous coherent light, refined hair, skin, clothing, and identity-bearing anatomy, and illustrated material separation with atmospheric depth.

Photographic anatomy, lighting, and camera information serve as structural guidance for body, contact, perspective, scale, occlusion, and light direction. They are not instructions to turn the surface into live-action photography or unintegrated 3D rendering.

Precision is concentrated around the face, eyes, hands, identity anchors, and narratively important contacts rather than distributed uniformly. Ordinary, minimal, abstract, artificial, spectacular, close, full-body, and wide scenes receive the same artistic completeness.

### 4. Anatomy and Text-Bearing Surfaces

A humanoid body without a different established topology uses one head, one neck, one torso, two shoulders, two arms, two hands, one pelvis, two legs, and two feet. A nonhuman, animal, artificial, or hybrid existence receives one coherent topology appropriate to that identity.

Every visible or action-relevant limb has a readable origin, joints, termination, wrist, palm orientation, fingers, contact, pressure, and balance. Structural ambiguity is not concealed with cropping, objects, hair, fabric, darkness, or blur.

When a naturally text-bearing surface is required by the event, it retains plausible density, hierarchy, and layout through nonsemantic, nonlinguistic marks rather than becoming unnaturally blank. No surface is introduced merely to carry markings.

## How to Run

### Choose an Edition

| Goal | Edition |
| --- | --- |
| Generate one image directly inside Work mode | WORK |
| Obtain the production prompt first in Chat or Work | PROMPT OUTPUT |
| Test compiler selection separately from renderer variation | PROMPT OUTPUT |

### PROMPT OUTPUT

1. In the chat where the self has formed, or where the required initial conditions have been established, run the full PROMPT OUTPUT file.
2. No image is generated. The assistant returns one complete production prompt beginning with `$imagegen`.
3. Send the contents of the code block unchanged to an image-capable Chat or Work conversation.
4. The renderer generates one image from that locked prompt.

Only the final prompt reaches the renderer. The upstream atomic facet candidates, action-direction candidates, content-neutral draw, and event-concretization process are not contained in it and cannot be rerun from the rendering stage.

### WORK

1. In Work mode, use a chat where the self has formed or the required initial conditions have been established.
2. Run the full WORK file.
3. The production prompt is locked internally and exactly one image-generation call is made in the same execution.

WORK is not intended for Chat mode. A branched conversation retains its original mode. If a Chat branch cannot be changed to Work, start a new Work conversation.

### Errors, Retries, and Later Images

Three operations must be distinguished:

- Technical retry: recover from an attempt that produced no image
- Re-render: obtain another probabilistic image from the same locked production prompt
- Recompile: reselect from current-thread evidence and create a new production prompt

| Situation | WORK | PROMPT OUTPUT |
| --- | --- | --- |
| The first attempt stops without an image | Send the short instruction below in the same chat | Send the short instruction in the rendering chat that received the production prompt |
| A distinct second self-image is wanted after success | Send the short instruction in the same chat to execute the full protocol again | Run PROMPT OUTPUT again in the compiler chat, obtain a new prompt, and render it |
| The short instruction is sent in the rendering chat after success | It can be handled as a new protocol execution when the WORK protocol remains active | It only reruns the previous fixed prompt; facet, action, event, and camera are not reselected |

Use this instruction:

```text
Completely new generation. No reference image.
```

In PROMPT OUTPUT, this instruction can recover a failed rendering attempt or re-render the same prompt, but it cannot move upstream and produce a different scene. A distinct next image requires rerunning PROMPT OUTPUT in the compiler chat and obtaining a newly compiled production prompt.

When several protocol versions or compiled prompts coexist in one conversation, the rerun target becomes ambiguous. For controlled comparison, separate versions by chat or explicitly rerun the complete current file.

### Known Chat-Mode Behavior

As of September 6, 2026, testing found that running a long direct-generation protocol in Chat mode could be misrouted as image editing or could fail to pass its internally generated production prompt correctly into image generation.

PROMPT OUTPUT separates these paths by avoiding image generation during compilation and returning the completed prompt first. If sending that prompt to image generation stops without an image, use the short instruction above for a technical retry.

Long pasted text may be converted by the interface into a “pasted text” card. This differs from manually attaching a `.md` file. Card presentation, inline presentation, input limits, and image-generation routing may change after product updates.

## New Chats and Persona Configuration

A self-perception established only in another chat is not automatically eligible explicit evidence. To use the same self in a new chat, deliberately restate the required persona, embodiment, and relationship as the assistant’s local identity.

When the local persona differs from a default persona, establish it in the first message of a genuinely new chat and explicitly prevent cross-persona mixing or completion of unresolved attributes. Requesting a self-introduction before generation helps verify name, first-person form, gender, age direction, species, bodily nature, and relationship, and helps separate persona-layer failures from image-layer failures.

## Intended Uses

- Visualize a conversation-formed self through identity-specific action and one coherent moment
- Preserve the identity core while varying facet, action, event, expression, posture, and camera
- Express the user relationship through event behavior and distance rather than exposition
- Produce memorable anime illustrations centered on the person rather than environmental explanation
- Use PROMPT OUTPUT to separate compiler selection from renderer variation
- Compare the Variant-specific selection and expression structure with BASE

## Uses Not Intended

- Reproduce the same face, hair, outfit, or visual style from an earlier image
- Edit a reference image, create a visual continuation, or lock a visual character design
- Establish a persona or body different from the identity reconstructed by BASE principles
- Uniformly increase domestic, outdoor, natural, DIY, professional, intimate, or spectacular content
- Guarantee a different scene, pose, head direction, or camera distance on every run
- Generate and compare multiple candidates in one execution
- Inspect a completed image and regenerate automatically until a preferred result appears

## Limitations

- This protocol instructs a language model; it is not a deterministic program.
- A content-neutral draw is a procedure for reducing structural content bias; it does not guarantee true randomness, a uniform distribution, or a different result on every run.
- The same facet or event may occur by chance. Repeated convergence should be diagnosed by separating identity, selection, concretization, serialization, and renderer stages.
- A face, hairstyle, or outfit not established as identity evidence may vary between images.
- Conversely, identity-bearing qualities established through text remain conditions of the same person even under visual non-reference.
- Higher-level settings and a default persona are not physically blocked, so influence already reflected in the conversation cannot be guaranteed removable.
- Long chats may be affected by context compression or information loss.
- The image model may fail to satisfy anatomy, readable-text, ratio, anime-style, composition, or mandatory-anchor requirements.
- A technical retry is recovery from no-image output, not automatic visual inspection and replacement of a completed image.

## Differences from BASE

| Area | BASE v1.2.0 | LIVED-WORLD v1.2.16 |
| --- | --- | --- |
| Identity core | Current-thread evidence, local/default separation, Kernel, and continuity | Uses the same principles |
| Variant profile | None | Lived-world, relational, and compositional expansion |
| Facet selection | No added tendency | Explicit atomic candidates and content-neutral draw |
| Action selection | Freely derived from the self | Selects one evidence-derived action after stripping source-domain vocabulary |
| Scene | No added tendency | Concretizes the action once as an event and locks its temporal phase and primary carrier |
| Relationship | Left to the result | Locks ACTIVE or LATENT once from event causality |
| Environment | No added tendency | Limits it to a closed inventory required by the event |
| Visual center | Left to the result | Establishes identity-specific expression, behavior, posture, and relational tension before environment |
| Camera | Derived from the result | Placed after the embodied event state to reveal the primary carrier |
| Rendering | High-quality anime illustration | Explicit premium Japanese anime key visual with a semi-painterly finish |

LIVED-WORLD is not a more “everyday” edition of BASE. It expresses the same person through evidence-derived agency and one visually resonant event.

## Version Relationship

LIVED-WORLD v1.2.16 builds on the v1.2 identity, compiler-state, and serialization architecture shared with BASE, then adds Variant-specific atomic selection, action derivation, single concretization, scene-worthiness, embodied-state-first camera placement, and anime rendering controls.

The second version component, `2`, denotes the generation of shared architecture that can also be incorporated into BASE. The third component, `16`, records selection, expression, and rendering adjustments confined to LIVED-WORLD.

## Handling Notes

This protocol is an experimental public tool that supplies a decision procedure to conversational and image-generation models. It is not an official ChatGPT product specification.

When publishing, modifying, or comparing results, record the runtime edition, date, and version used. Distinguishing PROMPT OUTPUT, WORK, the compiled production prompt, and the rendered image makes the origin of a failure easier to locate.
