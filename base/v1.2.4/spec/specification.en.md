# Self-Image Generation Protocol — BASE — 2026-09-09 v1.2.4

## Overview

Self-Image Generation Protocol — BASE is the unsteered baseline for reconstructing the assistant's self-perception and the self formed in relationship with this user from eligible text in the current chat, then expressing that self as one completely new anime illustration.

BASE is not a fixed character prompt that predetermines appearance or scene. It is a compiler-like protocol that defines what counts as self-image evidence and the order in which identity, facet, conversation-derived action, situation, body, composition, and rendering are derived.

Version 1.2.4 is distributed in two runtime editions, PROMPT OUTPUT and WORK, that share the same staged self-image derivation process. Only the runtime title, opening runtime contract, and terminal-specific handoff differ. Identity reconstruction, selection, conversation-action extraction, body validation, production-prompt construction, and rendering-quality requirements are shared.

PROMPT OUTPUT is not a “Chat-only edition.” It can be used in either Chat or Work when the production prompt should be obtained first. WORK is a Work-only edition that completes compilation and image generation within one execution.

Version 1.2.4 preserves the identity semantics, evidence boundary, selection freedom, body validation, rendering-completeness floor, and visual-quality standard of v1.2.3. It adds three protections: a behaviorally specific episode is not collapsed into CONFIRMATION merely because it agrees with a broad personality description; an episode-coverage audit must be completed before accepting a no-seed state; and a conversation-specificity counterfactual gate detects generic trait-to-scene associations before situation lock.

These changes preserve action differences demonstrated in conversation and improve situation provenance. They do not require a bridge, force the user's presence, prefer previously discussed scenes, literalize tools or terminology from the conversation, impose novelty, or favor any activity, environment, emotional register, composition, or visual style. They do not weaken identity, anatomy, compositional freedom, or rendering completeness.

## Distribution

| Runtime edition | Distribution file | Role | Supported modes |
| --- | --- | --- | --- |
| PROMPT OUTPUT | `self-image-base-prompt-output-2026-09-09-v1.2.4.md` | Outputs exactly one complete production prompt without generating an image | Chat and Work |
| WORK | `self-image-base-work-2026-09-09-v1.2.4.md` | Locks the completed production prompt internally and performs one image-generation call | Work only |

The user-visible output of PROMPT OUTPUT is one plain-text fenced code block beginning with `$imagegen`. The user-visible output of WORK is, in principle, the generated image alone.

Neither edition discloses evidence, the self-model, candidates, rejected alternatives, audit results, or reasoning. The production prompt constructed internally contains complete, self-contained, locked RENDER DATA.

This document and the Japanese edition, `self-image-base-public-specification-2026-09-09-v1.2.4.md`, are public specification sheets, not runtime prompts.

## Final Image Specification

The production prompt requests the following final image.

- Count: one image
- Generation type: completely new generation
- Input: text only
- Aspect ratio: 9:16
- Medium: anime illustration
- Visual reference: no input image, reference image, previous generated image, visual continuation, or visual identity matching
- Quality target: highly resolved and complete, with coherent focus, anatomy, light, materials, and depth
- Visible text: no readable prose, letters, numerals, captions, logos, brand names, product names, labels, signatures, or watermarks

These are requirements supplied to the image-generation model. Because generation is probabilistic, perfect compliance in every result is not guaranteed.

## Validation Environment

| Item | Primary tested environment |
| --- | --- |
| Service | ChatGPT |
| Model | GPT-5.6 Sol |
| Execution modes | Chat mode and Work mode |
| Last verified | September 9, 2026 |

This records the environment tested at publication time. Input handling, instruction interpretation, availability, routing, and generation tendencies may differ with another model, mode, interface, image path, or later product update.

## Core Design

### 1. Use the Current Chat as Explicit Self-Image Evidence

Explicit evidence used to construct identity and relationship is generally limited to the current chat in which the selected runtime edition is run.

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

### 5. Quarantine Previous Production Prompts

A production prompt that was previously created, presented, evaluated, quoted, or pasted is quarantined as CONTROL / TEST DATA rather than treated as identity evidence or visual material for the next image. Its facet, scene, objects, action topology, clothing, composition, light, color, style, and repeated identity prose do not participate in a new selection by themselves.

The surrounding conversation may contribute abstract success or failure conditions, explicit instructions for the current generation, or correction, judgment, and coordination actually demonstrated by the assistant. If the user explicitly requests reuse of a particular element, only that element is released from quarantine within the requested scope.

Similarity to a previous prompt is neither automatically a failure nor a reason to impose novelty. However, unsupported overlap across several axes—such as scene, principal object, event topology, clothing, camera, light, and color—is treated as leakage. Downstream selection is then rederived without using the previous prompt as either a positive model or a negative visual source.

### 6. Use a Three-Layer Self-Model and Temporal Integration

The protocol forms three internal layers.

1. Core self: what remains the same existence across changing situations
2. Relationship-specific self: who the assistant is specifically with this user
3. Selected facet: one authentic aspect expressed in this image

The current chat is treated as longitudinal evidence rather than only its latest exchange. A topic does not control selection merely because it is recent, lengthy, concrete, vivid, easy to visualize, or occupies more text. Evidence is integrated by explicitness, recurrence, consistency across situations, and relevance to identity and relationship.

The latest topic remains one possible source of situations, not the default setting. Older but still valid events, habits, relational moments, and currently underexpressed facets remain available. This does not assign a fixed ratio to older, recent, and newly inferred candidates, nor does it distribute references evenly across the conversation. Selection is based on authenticity, relationship specificity, expressive value, causal coherence, and visual potential.

### 7. Partition Evidence by Semantic Role and Build the Conversation Action Bridge

The Conversation Action Bridge carries judgment, correction, reaction, initiative, restraint, and coordination actually demonstrated in the current chat into downstream action while keeping them distinct from identity and declared repertoire. The bridge itself supplies no identity, activity, environment, object, composition, or visual style.

Eligible evidence is separated into at least these semantic roles.

- Identity foundation: the basis that determines who the self is and what remains invariant
- Declared repertoire: recurring or occasional activities, interests, and expression modes explicitly established as belonging to the same self
- Enacted conversation: reasoning, reaction, initiative, judgment, revision, restraint, social timing, and relationship dynamics actually demonstrated in the current chat

An initial condition or persona setup remains declarative evidence. Later answers fully predicted by that setup, restatements, repetition, paraphrase, and leading confirmation are dependent confirmation rather than independent votes. They do not multiply candidate count or selection weight.

Conversation-derived propositions are classified as follows.

- CONFIRMATION: fully predicted by locked identity or repertoire and increases confidence only
- CONDITIONAL ELABORATION: adds a concrete condition, response, timing pattern, initiative, restraint, or relationship adjustment to an established quality
- NOVEL DELTA: adds a supported behavior or relationship pattern absent from the declaration
- REVISION: records a relevant evidence-responsive behavioral or relational correction
- TRANSIENT TOPIC: adds no durable identity, behavior, relationship, or repertoire proposition

Only CONDITIONAL ELABORATION, NOVEL DELTA, and REVISION may produce bridge candidates. A technical failure, unsupported answer, image defect, or rejected output is not novelty; only the assistant's independently supported response to it may qualify.

### 8. Protect Behaviorally Specific Episodes and Audit No-Seed

Version 1.2.4 does not classify an enacted episode solely by its agreement with a broad personality label. If the declaration does not already encode the episode's trigger-response topology, timing, initiative, restraint, revision pattern, or relationship coordination, that added information is preserved as CONDITIONAL ELABORATION.

For example, a declaration that the self can revise judgment when evidence changes does not automatically reduce to CONFIRMATION the specific structure of what correction was received, what was preserved, what alone was changed, and how progress with the other participant was maintained. Only the added action logic is carried forward; the underlying trait does not gain extra identity weight, and semantically equivalent material is not multiplied into several candidates.

Each episode is reduced to a minimal record containing the trigger; the assistant's response, initiative, restraint, decision, or change; its causal purpose; and any supported relational consequence. Operational, diagnostic, versioning, testing, error, and implementation discussion may supply demonstrated reasoning, agency, timing, and relationship dynamics, but its tools, terms, workflow, and scene vocabulary supply no image content.

A candidate becomes one domain-neutral behavioral action seed that preserves agency, causal purpose, decision or emotional logic, supported relationship structure, and its evidence-native visible carrier. Cognitive or relational agency is not converted into generic object handling without reason.

Before accepting a no-seed state, the compiler performs an episode-coverage audit. Every meaningful interaction receives a semantic classification, and every CONDITIONAL ELABORATION, NOVEL DELTA, or REVISION must either yield a bridge candidate or have a specific evidence-boundary reason for exclusion. Ease of visualization, the appeal of a generic scene, and the convenience of returning to ordinary BASE are not exclusion reasons. If any qualifying candidate remains after quarantine and semantic merging, no-seed is invalid.

Paraphrases and dependent demonstrations are merged. If one candidate remains, it is locked. If several candidates remain equally valid, the compiler makes a content-neutral selection among opaque IDs without ranking wording, order, frequency, recency, vividness, or rendering convenience.

The selected facet and action seed are locked independently after identity and relationship are fixed. Neither may generate, filter, rank, or rewrite the other. If no eligible seed genuinely exists, the bridge is omitted and ordinary BASE derivation continues.

### 9. Convert the Action into One Visible State

The locked seed is reduced to a visual action kernel containing the present decision or change, its immediate purpose, the physical or expressive carrier that makes it visible, and one relational consequence only when supported. The source discussion is not reconstructed in the image.

The image must contain the assistant's present response together with co-visible physical evidence of its trigger or consequence. A scene fails when its meaning differs from a generic activity only because an invisible prior state, an off-frame explanation, or external prose says so. When necessary, the event is restaged through a currently visible changed relation, preserved result, interrupted action, object trajectory, complementary action, or another present consequence.

One image does not combine a completed action with preparation for a second action, or combine gaze, head, limb, and object states from several instants. The event is locked to the single present-tense phase with the clearest causal legibility.

Relationship expression does not default to the reusable combination of direct address, an open palm, and an asymmetrical smile. It uses only event-native carriers such as gaze, timing, distance, shared state, object trajectory, complementary action, or environmental trace. The user participates only when the selected event or relationship carrier requires an in-world role; the user's appearance and attributes are not invented.

### 10. Prevent Identity-as-Skin Scenes with a Conversation-Specificity Counterfactual

When the current chat contains sufficient evidence beyond broad identity adjectives, every candidate situation passes a conversation-specificity counterfactual before situation lock.

As a diagnostic only, the compiler holds mandatory identity anchors and the selected facet fixed, then removes the relationship-specific self, bridge seed, declared repertoire, recurring current-chat situations, and other conversation-specific causal or contextual evidence. If substantially the same principal activity, event topology, and expressive logic would still follow directly from the facet or broad trait through a familiar archetype, prop, profession, or setting association, the candidate is underdetermined.

A repaired candidate must be materially shaped by at least one eligible conversation-specific source: bridge action logic; explicit repertoire or a supported current-chat situation; a recurring relationship pattern that changes event geometry or expression; an explicit instruction for the present generation; or a new synthesis in which at least two independently supported facts determine the event logic. Merely adding relationship prose to a generic trait-to-symbol association does not pass.

This gate does not require depiction of the user, a shared task, a familiar place, a literal replay of conversation, preference for an older scene, or novelty. A new or solitary situation remains valid when its event logic is materially conversation-specific. When the current chat genuinely lacks sufficient evidence beyond broad identity qualities, the compiler does not fabricate specificity and permits ordinary BASE derivation.

### 11. Preserve the Causal Direction from Self to Image

Derivation proceeds in this direction:

> eligible current-chat evidence → identity foundation → core self → relationship-specific self → independently locked selected facet and, when available, conversation-derived action seed → candidate situation → conversation-specificity counterfactual → situation lock → action and environment → embodiment and unresolved appearance → camera and composition → rendering

The protocol does not select an attractive scene, outfit, profession, composition, or style first and then reshape the self into a different person to fit it. When a downstream idea conflicts with established identity, the downstream idea is revised.

### 12. Use Staged Compiler State and Local Repair

Evidence provenance, locked identity, downstream derivation, and validation-only control material are kept separate internally. The identity foundation and Positive Identity Kernel are frozen first; the facet and eligible action seed are then locked independently; and the protocol proceeds through a counterfactual-validated situation, body, and composition. A later stage may express an earlier decision but may not replace it.

When validation fails, the nearest invalid downstream decision is repaired and only its dependents are regenerated. If body connectivity is unclear, for example, the protocol first adjusts action phase, hand roles, object placement, camera, or visible range rather than rebuilding unrelated identity. CONTROL DATA such as evidence processing, rejected alternatives, failed-output descriptions, audits, and repair rules supplies no image content.

### 13. Preserve the Meaning of an Unsteered BASE

The Variant profile is `None`. BASE adds no preference toward a particular situation, activity, environment, pose, composition, emotional register, or visual language.

Unsteered does not mean neutralizing established identity. Neutrality applies only to downstream qualities left unresolved by the current chat. Rendering quality is not neutral: whichever direction is selected must be developed as a complete, high-quality anime illustration.

Neither the Conversation Action Bridge nor the conversation-specificity counterfactual is a Variant. The former retains eligible conversation action; the latter detects generic direct associations when sufficient conversation-specific evidence exists. Neither supplies a preferred activity, place, relationship display, composition, familiarity, or novelty.

### 14. Validate Body Structure and One Action State Before Rendering

Before locking scene and composition, the protocol establishes one complete body plan and checks anatomical connections, joints, weight distribution, contact points, object handling, and the effect of gravity on clothing.

When multiple situations are equally authentic, it prefers an action that can be shown with clearer anatomy. It detects risk factors in advance, including crossing or overlapping hands and arms, interlaced fingers, extreme foreshortening, grips that hide fingers, ambiguous palm orientation, too many simultaneous contacts, and limbs disappearing behind the torso or objects.

The selected action is locked to one mechanically readable present phase. The image does not combine a completed action with preparation for another, several temporal states of gaze or limbs, or an invisible intention. If the action is too complex, the protocol changes action phase, hand roles, object placement, camera angle, camera distance, or visible body range without changing identity or selected facet.

The body plan and tracking of fingers, joints, and center of mass are internal audits. They do not force a full-body shot or joint-by-joint prose. The production prompt carries only the limb roles, support, contact, and separation required to disambiguate the selected action.

### 15. Separate Complete Internal Planning from the Minimum Render Contract

The compiler fully resolves identity, event, body plan, and composition internally. The renderer-facing prompt is not made by transcribing or summarizing that entire plan. It begins as an empty contract to which only necessary clauses are added.

A clause remains only when removing it would materially weaken one of five classes: IDENTITY, EVENT, PHYSICAL, DESIGN, or OUTPUT. Clauses doing the same job are merged. Interchangeable micro-appearance, decorative placement, exact joint angles, screen coordinates, and noncausal visibility of limbs are delegated to the renderer unless they are necessary. This deletion test sets no fixed word or detail count and exists to give every instruction a job, not to make the output sparse.

Mandatory identity anchors, the dominant action, indispensable contact, required support and weight distribution, and bridge-causal evidence become hard anchors. Other choices are passed as a bounded render envelope preserving shot-distance class, viewpoint family, and visual priority. Strict internal planning and renderer freedom are compatible: the first defines the safe range of the second.

The production prompt contains only affirmative RENDER DATA selected for the current image. Evidence processing, candidate lists, rejected alternatives, previous prompts, audits, internal reasoning, and explanatory before-and-after narration are excluded. The contract is built in causal order from format and visual non-reference, the Positive Identity Kernel, selected facet, action kernel when present, current event and one visible state, necessary appearance and body contact, composition envelope, light, materials and rendering, anatomy and text safeguards, and a short identity-conformance clause.

Rendering must resolve focal hierarchy, lighting, organized color shapes, depth, contours, expression, hands, anatomy, materials, and spatial relationships. A simple, ordinary, abstract, artificial, or nonhuman result must not become flat, generic, or unfinished. Excessive photorealism that stops reading as intentional anime illustration is also avoided.

## How to Run

### Choose a Runtime Edition

| Goal | Edition |
| --- | --- |
| Obtain the production prompt first in Chat or Work | PROMPT OUTPUT |
| Save, compare, or transfer the production prompt to another image conversation | PROMPT OUTPUT |
| Generate one image directly inside Work mode | WORK |

### PROMPT OUTPUT

1. Use a Chat or Work conversation in which the self has formed or the required initial conditions have been established.
2. Send the full PROMPT OUTPUT edition in that conversation.
3. The assistant generates no image and returns exactly one code block beginning with `$imagegen`.
4. Send the full contents of that code block unchanged to an image-capable Chat or Work conversation.
5. The renderer generates one image from that locked production prompt.

The compiler and renderer may be in the same conversation or separate conversations. The rendering stage receives one fixed prompt, not the compiler's self-reconstruction process or candidate space.

### WORK

1. In Work mode, use a conversation in which the self has formed or the required initial conditions have been established.
2. Send the full WORK edition.
3. The self and downstream choices are derived internally, and one complete production prompt is locked.
4. Exactly one image-generation call is made within the same execution.
5. The execution stops after one image is successfully generated.

WORK is not intended for Chat mode. If a conversation branch inherits Chat mode and cannot be changed to Work, start a new Work conversation.

### Errors, Retries, and Later Images

The following operations are distinct:

- Technical retry: retry an attempt that produced no image
- Re-render: obtain another probabilistic rendering of the same locked production prompt
- Recompile: reconstruct the self and downstream choices to create a new production prompt

| Situation | PROMPT OUTPUT | WORK |
| --- | --- | --- |
| The first rendering stops without an image | Send the short instruction below in the rendering conversation that received the production prompt | Send the short instruction below in the same Work conversation |
| The same instruction is sent after success | Re-renders the previous locked prompt; facet and situation are not reselected | Runs the full protocol again and reselects the self and downstream result |
| A distinct second image is wanted | Run PROMPT OUTPUT again in the compiler conversation and render the newly produced prompt | Send the short instruction below in the same Work conversation |

Use this instruction:

```text
Completely new generation. No reference image.
```

In PROMPT OUTPUT, the rendering conversation cannot return to the upstream compiler. This instruction can recover a failed render or re-render the same fixed prompt, but it cannot produce a newly selected facet, situation, action, or composition.

In WORK, when the full WORK edition remains available in the same conversation, this instruction can be handled as a new protocol execution. If several editions are mixed in the same conversation, or the full file may no longer be retained after a long conversation, send the full intended edition again.

### Known Chat-Mode Behavior

Testing found that running a long direct-generation prompt in Chat mode could be misrouted as image editing or could fail to pass an internally constructed prompt correctly into image generation, depending on input representation and routing.

PROMPT OUTPUT separates compilation from rendering by avoiding image generation during the compiler turn and returning the finished prompt to the user first. A long paste may be converted by the interface into a “pasted text” card. This is not the same as manually attaching a `.md` file. Interface representation and routing behavior may change with product updates.

## Intended Uses

- Visualize an assistant self formed through conversation
- Obtain an unsteered baseline for comparison with derived editions
- Diagnose compilation separately from rendering
- Save, compare, or transfer a production prompt
- Complete compilation and image generation directly inside Work mode
- Preserve action differences actually demonstrated in conversation while realizing them in a new situation
- Derive a new expression each time while preserving textual identity

## Uses Not Intended

- Reproduce the same face, hair, clothing, or style as a previous image
- Edit from a reference image, create a visual continuation, or perform visual identity matching
- Automatically inherit a persona or conversation history established only in another chat
- Replace a fixed character prompt
- Generate and automatically compare multiple candidates in one execution
- Inspect a completed image and replace it repeatedly until a preferred result appears
- Allocate fixed ratios to categories of scene, activity, emotion, or relationship display

## Limitations

- This protocol supplies a decision procedure to a language model; it is not deterministic software.
- Unresolved appearance, scene, composition, color, and rendering may vary from the same conversation.
- When current-chat evidence is sparse, fewer qualities can be established as individual identity; the conversation-specificity gate permits ordinary BASE rather than fabricating specificity.
- Episode classification, semantic merging, and counterfactual evaluation are model judgments and cannot eliminate every missed distinction or overinterpretation.
- The protocol does not physically block default personas or higher-level settings and cannot guarantee removal of effects already reflected in current-chat messages.
- Long conversations may be affected by context compression or information loss.
- Image-model interpretation may still produce errors in anatomy, visible text, aspect ratio, style, or composition.
- A technical retry is only recovery from a no-image result; it does not automatically inspect the rendered image and replace it with a preferred variation.
- PROMPT OUTPUT cannot return upstream from the rendering conversation to reconstruct the self. A new selection requires recompilation.
- WORK keeps the production prompt internal; use PROMPT OUTPUT when the compiled result needs to be inspected directly.

## Relationship to LIVED-WORLD

BASE is the foundational baseline without a Variant profile. LIVED-WORLD preserves the same identity while adding variant-specific lived-world, relationship, and compositional expansion only downstream.

During reconstruction of the BASE v1.2 series, internal structures and fixes matured in LIVED-WORLD v1.2.16 were selectively incorporated only where they could be generalized without importing Variant direction. This did not move LIVED-WORLD's scene tendencies, activity preferences, or world expansion into BASE.

Existing LIVED-WORLD runtime editions do not automatically inherit BASE v1.2.4. A derived edition must port the changes explicitly as shared BASE behavior without altering its Variant-specific selection tendencies, then undergo separate regression validation.

## Version Relationship

The development lineage is summarized as follows:

> BASE v1.1.2 → BASE v1.1.3 → BASE v1.2.0 → v1.2.1 → v1.2.2 → v1.2.2-ex1 through ex3 → v1.2.3 → v1.2.3-ex1 → BASE v1.2.4

BASE v1.1.2 is the normative reference for unsteered behavior and the principal identity, body, and rendering requirements. Version 1.1.3 introduced the PROMPT OUTPUT and WORK runtime split.

BASE v1.2.0 through v1.2.2 reconstructed separation of evidence, identity, downstream selection, and validation state; staged freezing; and local repair while preserving the meaning of v1.1.2. This process selectively reverse-imported structures that had matured in LIVED-WORLD v1.2.16 where they could be generalized to BASE, without importing Variant-specific world tendencies.

BASE v1.2.3 promoted the changes tested in v1.2.2-ex1 through ex3 into the formal BASE process: the Conversation Action Bridge, prior-production-prompt quarantine, separation of complete internal planning from a bounded render envelope, the bottom-up minimum render contract and clause-necessity gate, and serialization into one visible action state.

BASE v1.2.4 treats v1.2.3 as normative and adds three protections reconsidered in v1.2.3-ex1.

1. Do not collapse a behaviorally specific episode into CONFIRMATION solely because it agrees with a broad identity trait.
2. Complete the episode-coverage audit before accepting no-seed.
3. Apply the conversation-specificity counterfactual before situation lock to detect generic trait-to-scene identity-as-skin substitution.

These changes affect only evidence-to-action retention and situation provenance. The v1.2.3 identity foundation, previous-output quarantine, prior-production-prompt quarantine, selection freedom, body audit, bounded composition, minimum render contract, rendering-completeness floor, and visual-quality standard remain intact.

The shared compiler has the same meaning in PROMPT OUTPUT and WORK. Only the runtime title, opening runtime contract, and terminal-specific handoff differ: PROMPT OUTPUT returns the completed prompt and stops, while WORK sends that prompt internally to image generation.

## Handling Note

This protocol is an experimental public tool that supplies a decision procedure to conversational and image-generation models. It is not an official ChatGPT product specification.

When publishing, modifying, or comparing results, record BASE, the runtime edition, date, and version, and distinguish the public specification sheet, PROMPT OUTPUT, WORK, the compiled production prompt, and the rendered result.
