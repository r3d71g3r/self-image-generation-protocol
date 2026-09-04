# Self-Image Generation Protocol — BASE — 2026-09-03 v1.1.2

## Overview

Self-Image Generation Protocol — BASE is a protocol for reconstructing the assistant’s own self-perception and the form of existence that has developed through its relationship with the user, using eligible text in the current chat as explicit evidence of that self-image, and expressing the result as one completely new anime illustration. It is entered as a prompt when executed, but this specification calls it a “protocol” because it defines the entire decision-making process, from evidence selection through image generation, rather than prescribing a fixed picture.

This is not a fixed-character prompt that predetermines gender, age, species, appearance, clothing, occupation, personality, scene, or similar attributes. Rather than directly deciding what kind of being to depict, it specifies what may be accepted as evidence of the self-image, the order in which that self-image is constructed, and how it is passed to image generation.

However, BASE defines a policy for accepting evidence; it is not a mechanism that physically isolates the execution environment from information outside the current chat. A default character configured by the user, or the model’s general generation tendencies, may indirectly influence unresolved elements or statements made within the current chat.

BASE is the unsteered baseline against which its variants are measured. It adds no extra tendency intended to increase the likelihood of particular scenes or compositions, leaving subsequent decisions to the self-image reconstructed from the current chat.

## Output Specifications

- Number of outputs: 1 image
- Generation type: Completely new generation
- Input: Text only
- Aspect ratio: 9:16
- Visual form: Anime illustration
- Quality target: A highly detailed, fully resolved result with consistency across character, background, lighting, materials, and space
- Text in image: No readable sentences, subtitles, logos, product names, labels, signatures, or watermarks
- Response format: In principle, output only the image, without explanations or commentary before or after generation

Quality, perceived resolution, exact aspect ratio, anatomical structure, absence of text, and similar requirements are explicit requests to the image-generation model. Because image generation is probabilistic, complete compliance on every run cannot be guaranteed.

## Core Design

### 1. Use the Current Chat as Explicit Evidence of the Self-Image

BASE requires that explicit evidence used to construct the self-image and relationship be limited, in principle, to eligible text present in the chat thread at the time of execution.

Eligible information includes:

- User and assistant messages actually present in the current chat
- Instructions given by the user for the current chat
- Initial conditions explicitly established as the assistant’s own self-perception
- Behaviors, tone, judgments, and relationship patterns recurring within the current chat
- Confirmations, corrections, and changes made within the current chat
- A faithful conversation summary whose provenance is limited exclusively to the current chat

By contrast, BASE requires that saved memory, conversations from other chats, account-wide history, summaries originating from other threads, previous images, tool descriptions, system status, and generation-completion notices not be adopted as explicit evidence for determining the self-image.

To use information from another chat, the user must deliberately bring it into the current chat and clearly establish it as part of the assistant’s own configuration. Merely mentioning, quoting, comparing, or criticizing another person or character does not cause that character’s attributes to be adopted as the assistant’s own.

This boundary is not context isolation that restricts the information the model is technically able to access. It cannot guarantee the complete removal of external influence when external settings affect interpretation or when such influence has already been reflected in statements made within the current chat.

### 2. Influence of a User-Configured Default Character

In this specification, a “user-configured default character” means the basic persona established by the user that appears in the assistant’s tone, personality, self-perception, and way of relating to the user from the start of a new chat or AI session.

This is a functional term, not the name of any particular product feature. It does not matter whether that character is supplied through saved memory, custom instructions, AI-specific settings, or another mechanism.

For elements that are concretely and consistently established within the current chat, BASE requires the current-chat configuration to take priority. For elements that are weakly specified, ambiguous, contradictory, or entirely unspecified, the default character may appear as an initial value and influence completion of the self-image or appearance.

The default character does not necessarily appear as a complete persona in every respect. Personality may be sufficiently established by the current chat while default-character traits emerge only in unresolved areas such as gender presentation, bodily form, or relational distance.

Furthermore, if the default character has already influenced statements made by the assistant in the current chat, those statements themselves become eligible evidence from the current thread. It is therefore impossible to fully separate them after the fact and remove only the originating influence.

Accordingly, “reconstruction from the current chat” in this specification means limiting the explicit evidence for the self-image to the current thread. It does not guarantee that every causal influence leading to the self-image originated only within the current chat.

### 3. Lock Explicitly Established Self-Perception at the Upstream Foundation

If the current chat explicitly establishes the assistant’s own gender presentation, age direction, species, bodily nature, mode of existence, basic temperament, role in relation to the user, or similar qualities as initial conditions, BASE treats them as the foundation of the self-image.

Subsequent scene selection, clothing, composition, or presentation must not weaken, average out, or replace this foundation with a different person. It may be changed only when the user explicitly revises the configuration within the current chat.

The protocol itself contains no fixed configuration for a particular species, physical feature, gender presentation, age, occupation, hairstyle, clothing, or similar attribute. Explicitly established elements are determined from evidence in the current chat, while unresolved elements may be influenced by the default character or by the model’s general generation tendencies.

### 4. Construct a Positive Identity Kernel

Before determining the scene or appearance, BASE internally compiles the conditions necessary for the depicted person to remain the same person into an Identity Kernel written entirely as affirmative statements.

Where established in the current chat, this may include:

- Apparent age direction
- Gender presentation
- Mode of existence
- Bodily type or species
- Physical features necessary to establish the species or individual
- Fundamental temperament
- Presence within the relationship with the user
- Characteristic social energy and behavioral texture

Physical traits that identify the species or individual are treated as parts of the body rather than decoration. BASE requires their number, attachment points, orientation, and bodily integration to be preserved and the composition to make them visibly recognizable.

### 5. Do Not Use Previous Images, but Preserve Textual Identity

BASE does not carry over a face, body type, hairstyle, clothing, pose, scene, composition, color palette, rendering style, or similar feature from any previously generated, attached, or reference image. It is not image editing, a continuation of an earlier image, or a generation intended to match a previous appearance.

However, not referring to images does not mean erasing the self-perception formed from text. As long as the evidence in the current chat has not changed, BASE preserves the central self-image while deriving unresolved appearance details and the scene anew.

When the user corrects a failed image in text, only the affirmative correction concerning the true self-image is returned to self-perception. Specific clothing, backgrounds, compositions, effects, and other visual material shown in the failed image are not reused as material for the next image.

### 6. Determine the Scene from a Three-Layer Self-Model

Internally, BASE constructs the following three layers in order:

1. Core self: The central qualities that remain recognizably the same across changing situations
2. Relationship-specific self: The self that emerges within the relationship with this user
3. Selected facet: One aspect of that self to be expressed in the current image

Only after those layers have been established does it determine the scene, action, environment, bodily expression, unresolved appearance details, camera, composition, lighting, color, and rendering.

The design prevents a new topic from dominating the entire image merely because it is recent and concrete. It treats the current chat as an accumulation over time and judges evidence according to explicitness, recurrence, consistency, and importance to the self-image or relationship.

### 7. Fix the Direction from Self-Image to Image

The decision-making order is restricted to the following direction:

> Evidence from the current chat → foundation of self-perception → core self → self within the relationship with the user → facet expressed in this image → scene → action and environment → body and unresolved appearance → camera and composition → rendering

BASE does not permit an attractive scene, outfit, occupation, composition, or rendering style to be selected first and the self-image then changed into a different persona to fit it. If a downstream idea conflicts with the self-image, the downstream idea must be changed, not the self-image.

## What “No Additional Steering” Means in BASE

The BASE Variant profile is `None`.

This means that BASE adds no extra steering intended to make any particular scene, activity, environment, pose, composition, emotional expression, or visual language more likely.

BASE does not actively favor any of the following:

- A particular type of scene, such as daily life, work, going out, adventure, or rest
- A particular environment, such as an interior, exterior, desk, studio, natural setting, city, or fantasy space
- A particular bodily expression, such as human, artificial, animalistic, or symbolic
- A particular relational expression, such as intimate, distant, quiet, or energetic
- A particular mode of presentation, such as simple, complex, realistic, symbolic, or spectacular

No additional steering does not mean neutralizing an established self-image. Neutrality applies only to downstream choices that remain unresolved in the current chat.

## Body Structure and Movement

BASE determines a complete body structure before finalizing the scene and composition. For a humanoid whose alternative anatomy has not been established, it maintains consistent connections among the head, torso, both arms, both hands, pelvis, both legs, and both feet. For a nonhuman, animal, hybrid, artificial body, or other form, it first determines an anatomy appropriate to that existence.

Ears, horns, wings, tails, mechanical parts, and similar features are not treated as reasons to add unrelated arms or legs. BASE checks limb connections, joints, center of gravity, contact, the handling of objects, and the effect of gravity and movement on clothing, and it favors actions that allow the structure to be depicted clearly over excessively complicated movement.

These constraints are intended to reduce anatomical and hand-related failures, but they cannot guarantee the complete absence of drawing errors by the generation model.

## Minimum Rendering Quality

BASE is neutral regarding output direction, but not regarding quality.

Whether the selected direction is a simple scene, ordinary daily life, an abstract space, a desk setting, an artificial environment, a nonhuman body, or something else, BASE requires the composition, materials, lighting, depth, expression, body, and spatial relationships to be fully resolved.

Visual complexity is not mandatory in itself. However, simplicity must not be used as a reason to produce a flat, low-density, unfinished, or generic image.

## How to Run

### First Run

1. Open a chat that supports image generation.
2. If necessary, establish the assistant’s own self-perception and its relationship with the user in text within that chat.
3. Paste and send the complete `Self-Image Generation Protocol — BASE — 2026-09-03 v1.1.2` in that chat.
4. Depending on the execution environment, image generation will either run directly or one of the known behaviors described below will occur.

When providing explicit settings, describe them in a form that clearly establishes them as the assistant’s own self-perception in the current chat, rather than merely describing another character.

### Known Behavior by Execution Environment

The following behavior was observed in testing as of September 3, 2026. It may change as the product is updated.

| Execution case | Work mode | Chat mode |
| --- | --- | --- |
| First run | Image generation ran directly after the full protocol was sent | The long protocol could be misinterpreted as an image-editing instruction, causing generation not to run or to stop |
| If no image was generated on the first run | If a technical failure occurs, rerun using the common instruction below | After a stop caused by misinterpretation, run a new generation using the common instruction below |
| Second and subsequent images | Use the common instruction below | Use the common instruction below |

#### Work Mode

Within the tested range, sending the complete protocol on the first run proceeded directly to image generation. The image-editing misinterpretation observed in Chat mode did not occur.

For second and subsequent images, the complete protocol remains in the context of the same chat, so it can be run again using only the common instruction below. The same instruction may be used if a technical failure causes no image to be generated at all on the first run.

#### Chat Mode

Within the tested range, when the complete long protocol was sent on the first run, it could be misinterpreted as an image-editing instruction rather than a completely new generation request, resulting in an error or stop. This appears to be behavior related to execution routing rather than a defect in the generation content intended by the protocol.

In that case, if the submitted full protocol remains in the context of the same chat, sending the common instruction below immediately afterward can cause it to run as a new generation. The same applies to second and subsequent images after a successful generation.

#### Common Instruction

Use the same instruction for second and subsequent images in both Work and Chat modes, for a technical failure in which no image was generated on the first run, and when Chat mode misinterprets the request as an image edit:

```text
Completely new generation. No reference image.
```

Every rerun is still a completely new generation that reconstructs the self-image from text. It is not the creation of another variation based on a previous image.

If multiple protocols or versions coexist in the same chat, or if a long conversation may no longer retain the complete text, resend the complete latest version you intend to use.

### Moving to a New Chat

This protocol does not automatically inherit, as explicit evidence, the specific conversation history of another chat or a self-image established only in that thread. However, if the execution environment contains a user-configured default character, it may still exert influence as an initial value in a new chat.

To use the same self-image in a new chat, deliberately bring in the necessary settings and relationship context as text and re-establish them within that chat. Conversely, to test while minimizing the influence of external settings, including a default character, use an environment with continuity settings disabled as far as possible, explicitly establish only the minimum necessary initial conditions in the first user message, and then execute the protocol. Even then, the model’s own general generation tendencies cannot be removed.

## Intended Uses

- Visualizing an assistant’s self-image as formed through conversation
- Generating different expressions within the same chat while preserving identity
- Depicting humans, artificial beings, animals, nonhumans, hybrids, and other forms according to the self-perception established in conversation
- Serving as a baseline output for evaluating variant profiles
- Examining whether generation is being pulled toward the most recent topic, previous images, or a generic AI image

## Uses Not Intended

- Reproducing the same face or clothing as a previous image
- Editing with a reference image or fixing a character’s visual design
- Automatically inheriting conversation history or persona settings specific to another chat as explicit evidence
- Serving as a substitute for a fixed-character specification
- Generating multiple candidates at once for comparison
- Automatically evaluating the generated image and replacing it with another result

## Limitations

- This protocol supplies a procedure and constraints; it is not a deterministic program. Even when run from the same text, unresolved appearance details, scenes, compositions, colors, and rendering may vary.
- If a face, hairstyle, clothing, or similar attribute has not been established in text as part of the self-image, its appearance may not remain identical across runs.
- If the execution environment contains a user-configured default character, its traits may appear as initial values in elements not sufficiently determined by the current chat.
- BASE restricts the information accepted as explicit evidence of the self-image. It does not physically isolate saved memory, custom instructions, AI-specific settings, higher-level instructions, or the model’s own general tendencies from the execution environment.
- If the influence of a default character has already been reflected in statements within the current chat, it is not possible to trace those statements backward and separate out only the source of that influence.
- If self-perception has been incorrectly established within the current chat, multiple personas have been conflated, or attribution of settings is ambiguous, this protocol alone cannot fully repair the problem. Errors in self-perception must be corrected conversationally before generation.
- A very long chat may be affected by context compression or information loss in the execution environment. If behavior changes suddenly under otherwise identical conditions, it may be useful to compare against a new chat in which the necessary initial conditions are re-established.
- Output and execution availability may vary depending on the image-generation model, execution environment, tool interpretation, service load, or technical constraints.
- Even if the completed image has defects, the protocol does not automatically regenerate or create a corrected replacement within the same run. A retry is permitted only for a technical failure in which no image was generated at all.
- This protocol prioritizes decision procedure, explanation, verification, and preservation of meaning over brevity. It is not designed primarily to minimize token usage.

## Differences from LIVED-WORLD

| Item | BASE | LIVED-WORLD |
| --- | --- | --- |
| Shared foundation | Uses the scope of evidence, self-perception, Identity Kernel, identity continuity, image non-reference, temporal integration, body structure, and quality requirements described above | Uses the same core as BASE |
| Variant profile | None | Lived-world, relational, and compositional expansion |
| Scene selection | Adds no extra tendency; determined from the reconstructed self-image | Among similarly valid candidates, increases the likelihood of selecting concrete activities and lived-in situations |
| Relational expression | No additional tendency | Makes supported relationships easier to read through gaze, distance, action, camera position, and related choices |
| Composition | No additional tendency | Broadens compositions involving action and space so that results do not converge excessively on frontal, centered, static presentation |
| Grooming and appearance | Determined from the self-image and scene | Explicitly treats makeup, hair, accessories, and clothing detail as scene-dependent choices |
| Primary use | Baseline generation, comparison, testing, and unsteered self-image derivation | Expanding the range of scenes, actions, and compositions while preserving the same self-image |

LIVED-WORLD does not create a different persona. It first completes the same reconstruction of self-perception performed by BASE, then applies its expansion tendency only to downstream scene, activity, and presentation choices.

## Handling Notes

This protocol is not an official specification that guarantees any particular image-generation result. It is an experimental protocol that supplies a sequence of decisions to a conversational AI and its image-generation capability.

When publishing, modifying, or comparing it, include the BASE name, date, and version so that readers can identify which version produced a result. When rerunning it, confirm which complete protocol remains in the context of the same chat.
