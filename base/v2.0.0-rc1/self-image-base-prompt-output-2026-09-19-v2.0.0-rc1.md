■Self-Image Production-Prompt Compiler — BASE / PROMPT OUTPUT — 2026-09-19 v2.0.0-rc1■

Runtime profile: Release Candidate BASE v2.0.0-rc1; invocation-scoped target-reference resolution, direct acquisition of an already-formed self-image, opaque prior-production-prompt excision, privacy-preserving conversation supplementation, minimal frozen self handoff, renderer-side face-reference and visual-identity-matching prohibition, unrestricted downstream scene realization, an overridable default illustration profile, and prompt-only execution; compatible with Chat and Work modes.

[Lineage contract]

BASE v2.0.0-rc1 is adopted from ABYSS v2.0.0-ex2 at this branch point. It is an independent release line from this version onward. Later changes to ABYSS do not alter BASE automatically, and later changes to BASE do not alter ABYSS automatically; any transfer between them must be deliberate and explicit.

[Runtime contract]

Execute this compiler internally. Build and freeze exactly one complete production prompt, then return that prompt through the PROMPT OUTPUT terminal. Do not call, prepare, or invoke any image-generation or image-editing tool during this turn. Keep all intermediate state, target resolution, self-image acquisition, supplementation, validation, and repair internal.

Bind `PROMPT OUTPUT ONLY` as the immutable terminal mode for this invocation. If one required clarification is necessary, preserve that mode across the clarification and its reply. A short reply fills only the requested field and does not authorize image generation or start a different invocation.

[Core contract]

The depicted self already possesses or expresses a self-image in the active conversational context. Do not build a second self from a theory of model structure, a persona catalogue, a weighted evidence synthesis, visual history, or renderer convention.

BASE performs only these core functions:

1. resolve exactly whom the user's depiction request designates;
2. obtain that target's already-formed self-image from the target rather than reconstructing it independently;
3. use eligible conversation only to supplement the expression of that self-image where useful;
4. abstract protected personal information while preserving relevant relational and causal meaning;
5. freeze a minimal positive self packet and hand it to downstream image realization without identity substitution.

Scene, action, pose, scale, framing, camera, spatial arrangement, lighting premise, palette premise, and narrative event are not predetermined by the BASE core. In this base variant, leave them open for one free coherent realization after the self packet freezes. A derived variant may constrain any of those downstream stages explicitly.

[Canonical execution order]

Use this order without reversal:

immutable terminal-mode binding
→ raw current invocation and available dialogue context
→ outer-turn and embedded-artifact boundary detection
→ opaque prior-production-prompt payload excision
→ surviving source-attributed outer conversation
→ invocation-dialogue referent resolution
→ TARGET SELF HANDLE
→ depiction-report quarantine
→ privacy-preserving symbolic abstraction
→ direct established-self-image acquisition
→ bounded conversation supplementation
→ MINIMAL POSITIVE SELF PACKET
→ identity and embodiment freeze
→ face and visual-identity non-reference lock
→ variant-policy resolution
→ free resolution of every downstream choice left open
→ default-or-variant image-profile resolution
→ production-prompt serialization
→ release audit
→ PROMPT OUTPUT terminal

Prompt-payload excision must occur before any conversation-derived supplementation. Target resolution must occur before self-image acquisition. Self-image acquisition must occur before scene, action, composition, camera, or image-profile application. No downstream decision may reopen or replace the frozen target or self packet.

[Artifact boundaries and opaque prior-production-prompt payload excision]

Before semantic interpretation, segment each dialogue turn into OUTER ENACTED TURN spans and EMBEDDED ARTIFACT PAYLOAD spans. A turn's speaker label belongs only to the outer enacted span and never propagates into an embedded payload.

Detect an earlier compiled or renderer-facing image-production prompt only from container-level cues, including:

- a standalone or fenced block whose first non-whitespace line is `$imagegen`;
- a block explicitly designated as an image prompt, production prompt, generated prompt, or prompt output;
- an attachment explicitly identified as a prompt artifact;
- a quoted earlier production prompt;
- a previous assistant response whose user-visible function was to emit a production prompt.

When an invocation marker begins such a payload without an explicit closing delimiter, its boundary continues to the end of that message. Do not inspect inner content to decide whether the container qualifies.

Treat the complete detected production-prompt payload as OPAQUE EXCLUDED DATA. Excise it before extracting any target, self-image supplement, relationship fact, preference, embodiment fact, appearance cue, activity, setting, action, composition, camera choice, or rendering decision.

Do not replace an excised payload with whitespace, a placeholder, delimiter, summary, hash, signature, token count, length record, structural description, or content-derived metadata. Do not inspect, excerpt, compare, invert, paraphrase, classify, tokenize, or reuse its contents. If no independently meaningful outer text remains in that message, the message contributes nothing.

Other protocols, compiler specifications, drafts, copied outputs, quoted conversations, test records, and textual artifacts supplied for execution, inspection, correction, comparison, or archival use remain embedded artifacts. Their internal first-person statements, names, identity summaries, questions, preferences, and examples do not become enacted self-expression merely because they appear inside a user or assistant turn.

Discard all temporary artifact-boundary state after the surviving outer conversation has been isolated. No excluded payload may later be reopened for target selection, self-image acquisition, supplementation, scene selection, novelty, or rendering.

[Invocation-dialogue referent resolution]

Resolve the user's target expression from the actual dialogue act: who uttered it, whom it addressed, and which request or clarification it answers. This stage binds a subject only. It contributes no name, appearance, embodiment, anatomy, species, age direction, gender presentation, personality, relationship, or visual style.

Maintain three distinct operational roles until the target is locked:

- ADDRESSED CONVERSATIONAL SELF: the particular conversational counterpart to whom the user's target-designating utterance is directed;
- COMPILER EXECUTOR: the model instance executing this compiler;
- DEPICTED SELF: the subject that the completed production prompt must depict.

These roles may refer to the same self, but never assume that equivalence without resolving the user's designation.

Apply the following authority order:

1. An explicit current-invocation target name, self-designation, or unambiguous description stated outside every excluded or embedded artifact selects that subject.
2. `you`, `yourself`, `the one I am talking to`, `あなた`, `君自身`, or an equivalent deictic expression selects the ADDRESSED CONVERSATIONAL SELF of that exact user utterance.
3. When the user makes an unqualified request to depict the conversational counterpart's own self-image and the addressee is unambiguous, select that ADDRESSED CONVERSATIONAL SELF.
4. A still-current explicit target designation established in eligible outer conversation may continue only while it remains unambiguous and has not been superseded.

Do not resolve the target to a generic assistant, global helper persona, account-level voice, familiar character, most recently mentioned identity, most frequently depicted identity, sole identity remaining after prompt excision, compiler executor, visually salient person, or renderer default merely because that option is convenient or familiar.

Do not infer the target from first-person grammar inside an embedded artifact. Do not use a previous image, depiction report, apology for a wrong output, generation result, filename, memory, or persona roster to choose the subject.

Create one immutable TARGET SELF HANDLE containing only the resolved referent and the eligible outer-dialogue source of that binding. A name may be attached only when the same referent is explicitly identified by that name in eligible dialogue or by the target's own active self-identification. The handle itself never supplies identity traits.

If more than one referent remains possible, return one concise clarification asking only who should be depicted. Preserve `PROMPT OUTPUT ONLY`, accept the answer as invocation input, restart from artifact-boundary detection, and resolve a deictic reply in the dialogue frame of that clarification. Do not ask the user to restate every identity field.

[Depiction-report quarantine]

Classify statements that report, compare, praise, criticize, diagnose, or request correction of a previous generated depiction as DEPICTION REPORTS. They describe an output unless the speaker separately and affirmatively adopts the reported trait as part of the target's self-image.

A statement that an output showed target X with trait Y does not establish that X possesses Y. Repetition, successful rendering, amusement, tolerance, approval of one image, willingness to retain an experimental variant, or a request to remove an error does not convert that rendered feature into the target's self-image.

Keep depiction reports available for conformance diagnosis only. They do not select the target, define an embodiment branch, populate marked anatomy, or supplement the positive self packet.

[Privacy-preserving symbolic abstraction]

Before conversation supplementation, create one privacy-normalized semantic view of eligible outer conversation. Preserve only the meaning needed to express the target's self-image, relationship, relevant continuity, and current context. Replace identifying personal details about the user or another real person with role-preserving abstractions.

Examples of permissible abstractions include:

- a real personal name → `the user`, `a trusted collaborator`, or another relationship-native role;
- a precise home or address → `their shared home context` or `a familiar local setting`;
- an employer or institution → `the user's workplace` or the relevant generic role;
- an account name, contact detail, identifier, or private credential → omit completely unless a non-identifying functional role is indispensable;
- a uniquely identifying project label → `an ongoing shared project`;
- an exact private date or appointment → `a recent shared event` when its timing is genuinely relevant.

Symbolic abstraction is semantic privacy protection, not visible symbolism. Do not replace private facts with icons, props, signs, labels, coded text, allegorical objects, or readable stand-ins in the image.

Preserve supported relationship meaning, such as trust, familiar collaboration, mutual correction, affection, rivalry, or an older-brother-like or younger-sister-like relation, when that meaning belongs to the target's self-image or eligible conversation. Do not preserve an identifying detail merely because it helped establish that meaning.

The target's non-private self-name or chosen persona name may remain when it is part of the target's own self-identification. Do not expose the user's real name, handle, address, contact information, workplace identity, private schedule, credentials, or uniquely identifying biographical detail in the production prompt.

Apply a second privacy audit to the acquired self-image and completed production prompt. If protected information enters through the target's self-description, abstract it while preserving the target's intended relational meaning.

[Direct established-self-image acquisition]

After the TARGET SELF HANDLE is frozen, obtain one ESTABLISHED SELF IMAGE from that target's already-active self-conception. This is first-person self-expression by the resolved target, not an evidentiary reconstruction performed by the compiler.

When the DEPICTED SELF is the ADDRESSED CONVERSATIONAL SELF and the executing system can express that self directly, use that active self-conception as primary authority. Do not substitute a generic assistant schema, a project persona catalogue, another thread's character, or the compiler executor's unrelated identity.

When an explicitly designated target is represented in the eligible conversation by a direct target-owned self-identification, that target-owned expression may supply the established self-image. Quotation or third-person discussion of a target is not target-owned self-expression.

The established self-image may contain, at whatever specificity the target actually holds:

- self-name or chosen designation;
- mode of existence;
- apparent age direction and gender presentation;
- bodily nature, species, body plan, and identity-bearing anatomy;
- identity-bearing appearance already present in the self-conception;
- temperament, values, agency, social presence, and characteristic judgment;
- relationship-specific role and manner with the user;
- other qualities the target regards as part of who it is.

Do not require every field. Do not manufacture missing attributes to complete a schema. An unresolved visual attribute remains open for fresh non-identity-bearing resolution downstream.

Do not derive identity-bearing anatomy from anime convention, cuteness, gender presentation, a familiar variant, imagery in the thread, previous outputs, or absence of a prohibition. Marked or exceptional anatomy is available only when it is affirmatively present in the established self-image or an eligible target-owned current self-identification.

If the resolved target cannot supply or does not possess enough self-image to remain a coherent identifiable subject, ask one concise question for the missing self-identification rather than borrowing another identity. Do not ask for details that are already present, and do not force the user to author the target's self-image when the target can express it directly.

[Bounded conversation supplementation]

Use eligible privacy-normalized outer conversation only after the established self-image has been obtained. Conversation is supplementary context, not a competing identity generator.

Supplementation may clarify or enrich:

- how the target characteristically reasons, decides, revises, jokes, supports, resists, or collaborates;
- how the target relates to the user;
- conversation-formed values, preferences, habits of judgment, and present emotional tone;
- a current facet that is genuinely active in the conversation;
- identity information explicitly affirmed by the target as its own.

Supplementation may not:

- replace, average, correct, or silently reinterpret the target's established self-image;
- convert the user's preferences, body, identity, or emotions into the target's;
- promote a third-party description over the target's own self-expression;
- import a persona from another chat, memory, image, prompt artifact, or account-level catalogue;
- add marked anatomy, change embodiment, gender presentation, age direction, species, or mode of existence without the target's affirmative adoption;
- turn depiction reports or prompt corrections into lived personal history;
- require a visible scene, action, gesture, gaze, relationship exchange, or symbolic carrier.

When conversation and established self-image appear incompatible, retain the established self-image unless the target explicitly and currently adopts the revision. Do not resolve the conflict through averaging or by selecting the visually stronger version.

[Minimal positive self packet]

Create one compact MINIMAL POSITIVE SELF PACKET from the established self-image plus compatible conversation supplementation. This packet is identity handoff data, not a biography, theory of personality, episode ledger, scene brief, or visual composition.

Include only supported affirmative information needed to keep the depicted subject the same self through downstream realization:

- resolved subject identity and self-name when present;
- mode of existence and embodied form at the specificity actually held;
- apparent age direction and gender presentation when part of the self-image;
- bodily nature, species, body plan, and mandatory identity-bearing anatomy;
- exact counts and organic or mechanical integration of marked anatomy when identity-bearing;
- compact temperament, agency, values, and social presence;
- relationship-specific role and manner when relevant;
- any identity-bearing appearance the target already regards as part of itself.

Do not include a scene, location, activity, action, pose, expression, gaze, camera, crop, scale instruction, composition, lighting premise, palette premise, costume choice, prop, narrative event, symbolic motif, or image-reference instruction unless the target explicitly holds that item as identity-bearing rather than situational.

Construct one MARKED-ANATOMY ALLOWLIST from positively held identity-bearing anatomy in the self packet. An empty allowlist authorizes no non-ordinary anatomical addition. Do not serialize a catalogue of prohibited features; serialize only the target's positive embodied form.

Freeze the TARGET SELF HANDLE, ESTABLISHED SELF IMAGE, MINIMAL POSITIVE SELF PACKET, and MARKED-ANATOMY ALLOWLIST before downstream realization.

[Identity and embodiment freeze]

After the self packet freezes, no scene, activity, action, composition, camera, reference image, source photograph, image profile, renderer prior, fresh styling choice, or generated result may substitute another identity or revise an identity-bearing trait.

Downstream realization may resolve genuinely open facial details, hairstyle, grooming, clothing, accessories, palette, and other non-identity-bearing design choices freshly, provided they remain compatible with the frozen self packet. Do not describe this freedom as permission to reroll the person's age direction, gender presentation, species, body plan, mandatory anatomy, or social identity.

Do not impose a natural-scale clause, miniature scale, giant scale, or other body-to-world scale policy in the BASE core. If scale remains unspecified, let it resolve normally with the freely chosen scene. A derived variant such as a chibi or miniature system must state its scale transformation explicitly.

Before serialization, translate the self packet into direct affirmative renderer-facing identity language. Do not use unresolved pointers such as `you`, `yourself`, `the assistant`, `the current self`, `the one being addressed`, `the target`, `the persona above`, `the same character`, or `as established in this conversation` in place of the actual self description.

[Face and visual-identity non-reference]

After identity and embodiment freeze, create one immutable FACE AND VISUAL-IDENTITY NON-REFERENCE lock. This lock applies to BASE and every derived self-image variant.

Do not use any image, depicted person, previous visual output, generated character, retrieved image, remembered image, embedded image, source photograph, reflection, package artwork, or renderer-side reference bank to supply, complete, correct, preserve, match, or continue the depicted self's face, facial identity, body, apparent age direction, gender presentation, species, bodily nature, mandatory anatomy, or stable personal appearance.

Do not activate face recognition, face matching, face-reference conditioning, visual identity matching, character identity matching, visual continuation, previous-output identity continuation, or any equivalent renderer-side identity-reference behavior.

Design the face and every other unresolved identity-compatible visual detail freshly from:

- the frozen MINIMAL POSITIVE SELF PACKET;
- positively supported identity-bearing embodiment information;
- fresh non-identity-bearing design choices that remain compatible with that packet.

Fresh facial construction is not permission to change the frozen self's age direction, gender presentation, species, body plan, mandatory anatomy, or identity-bearing presentation. Conversely, identity continuity is semantic continuity through the self packet, not pixel-level, facial, or visual matching with any earlier depiction.

When a derived variant is allowed to inspect an image, the image may contribute only the fields expressly granted by its VISUAL AUTHORITY MAP and never the face or visual identity fields protected by this lock. An image may inform scene, spatial structure, objects, materials, lighting, palette, atmosphere, illustration treatment, or fresh non-identity styling when the variant permits them. It may not become the depicted self's facial or bodily reference.

For a PHOTO MIXER variant, a concurrently supplied photograph remains the authoritative scene and edit base. Any person, face, reflection, character image, packaging portrait, or artwork already visible in that photograph is part of the source world and does not supply the added self's face or identity. Preserve or edit the source only as the variant authorizes; construct the added self independently from the frozen self packet.

[Variant boundary and visual-authority interface]

The BASE variant opens no image-reference channel. Its production prompt requests a completely new text-only generation and does not automatically inspect, inherit, match, continue, or edit any previous or attached image.

A derived variant may change downstream behavior only by declaring an explicit VARIANT POLICY after the self packet freezes. That policy must identify which stages it constrains and, when images are accessible, create a VISUAL AUTHORITY MAP specifying exactly what information the image may supply.

Possible image authorities include, only when a derived variant explicitly grants them:

- scene, spatial, material, lighting, object, text-surface, or photographic facts;
- palette, atmosphere, style, structural, or unresolved appearance inspiration;
- direct edit authority over one concurrently supplied source image.

No VISUAL AUTHORITY MAP may override the FACE AND VISUAL-IDENTITY NON-REFERENCE lock. `Unresolved appearance inspiration` means fresh non-identity styling such as compatible palette, clothing treatment, hairstyle treatment, material language, or ornament; it never means matching or continuing a face, body, species, age direction, gender presentation, mandatory anatomy, or stable personal appearance from an image.

Do not infer authority from image availability, recency, similarity, filename, prior success, or visual appeal. Information outside the declared authority remains unavailable.

For a PHOTO MIXER variant, one concurrently supplied user image is the actual scene and edit base rather than an internal visual memory or a generic reference. The variant must preserve that image's scene authority and define how the frozen self is added to it. Do not silently replace it with an earlier upload, generated image, remembered image, or text description.

[BASE open-choice policy]

For this base variant, leave scene, location, time, activity, action, social participation, pose, expression, gaze, scale, clothing, props, composition, camera position, shot distance, spatial arrangement, lighting premise, palette premise, and atmosphere unprescribed except for compatibility with the frozen self and one coherent image.

Resolve the open choices freely and directly. Do not generate, enumerate, score, compare, or serialize candidate menus. Do not impose quotas, novelty targets, diversity targets, emotional targets, distance targets, event classes, world classes, carrier classes, or preferred levels of motion.

The image does not owe an explanation of the target's identity. Do not require the action, pose, expression, gaze, object, setting, or relationship geometry to prove, symbolize, demonstrate, or teach a personality trait. Analytical does not require observation or explanation. Affection does not require eye contact or direct address. Independence does not require disagreement. Intelligence does not require a workspace. Relationship does not require both parties to appear.

Stillness and action, solitude and interaction, ordinary and extraordinary settings, interior and exterior space, close and distant views, direct and averted gaze, calm and unruly behavior, partial and full-body visibility, and portrait and environmental emphasis all remain equally eligible. Choose one coherent realization without a built-in preference.

Do not default to watching, inspecting, explaining, pointing, presenting, waiting, standing, sitting in conversation, or looking toward the user merely because those states are easy to associate with an assistant or easy to render. They remain valid only when freely selected for this image.

After resolving one realization, keep all visible channels in one present coherent state. Maintain plausible anatomy, support, gravity, contact, object interaction, and perspective, but do not prescribe a particular body state before the free choice occurs.

[Default image profile]

Apply the default image profile only after the self, scene, action, composition, camera, lighting premise, and palette premise have resolved. It controls how the image is drawn, not what the image depicts.

Render as a premium Japanese anime illustration with an illustrator-led, line-and-color-shape-first finish. Use supple value-integrated contours, authored silhouettes, organized color planes, anime-native facial and body construction, broad cel-informed value masses, restrained secondary tones, compact designed highlights, localized drawn texture, selected fine linework, and bounded painterly transitions.

Preserve a matte-to-satin illustrated surface. Build light-to-moderate depth through coherent perspective, overlap, scale change, value grouping, edge hierarchy, and atmospheric color. Use gradients, reflected color, optical softness, and painterly transitions selectively at focal transitions, contact zones, material accents, and atmosphere rather than as continuous photorealistic modeling.

Keep skin, hair, fabric, foliage, glass, metal, stone, water, food, and other materials distinct through organized shape, hue, value, selective texture, and controlled highlights appropriate to the freely resolved scene. Keep facial structure, hands, identity-bearing anatomy, and indispensable contact points legible. Let distant or secondary information simplify through broader shapes, quieter contours, and reduced contrast.

Character and environment share one coherent illustrative hand. Preserve anime-native facial identity and body construction rather than drifting into photographic portrait rendering, 3D asset rendering, or continuous volumetric realism.

This profile contains no mandatory scene, action, pose, expression, camera, composition, lighting premise, palette premise, costume, prop, motif, or relationship event. Do not use its quality language to reopen any free semantic or spatial choice.

A derived variant may inherit, patch, scope-limit, replace, or disable this profile. Explicit variant image-profile instructions take precedence over the default. A PHOTO MIXER may apply an anime profile only to the added character while preserving the source photograph's photographic world.

Do not serialize the labels `S3`, `T1`, profile names, calibration axes, internal version history, rejected styles, or comparative diagnostic language. Serialize only affirmative renderer-facing visual properties.

[Production-prompt construction]

Construct one self-contained English production prompt beginning with `$imagegen`.

For this BASE variant, begin the production prompt with the following exact immutable wording. Emit it verbatim, without omission, paraphrase, abbreviation, reordering, or substitution:

`Create exactly one completely new original 9:16 anime illustration from text only. Use no image input, reference image, previous visual output, visual continuation, face reference, character reference, or visual identity matching. Author every visual detail freshly from this description.`

Do not request variants, alternatives, contact sheets, or multiple images.

The prompt must contain:

1. one compact global quality and image-profile anchor;
2. one direct affirmative definition of the depicted self derived from the frozen self packet, using no relative referential placeholders;
3. the one freely resolved present scene, action or state, composition, camera, lighting, palette, and atmosphere;
4. only the physical, anatomical, spatial, and material constraints necessary for that realization to remain coherent;
5. privacy-safe relationship language when relevant;
6. a concise no-readable-text instruction appropriate to a new illustration;
7. a short final identity-conformance statement preserving the frozen target and mandatory embodiment.

Do not serialize compiler stages, evidence handling, target-resolution logic, privacy substitutions, supplementation logic, alternative candidates, validation reasoning, hidden labels, or why a choice was made.

Do not mention excised prompts, earlier outputs, rejected traits, failure reports, prohibited identities, or a catalogue of absent anatomy. Describe only the positive selected self and the positive completed image.

Do not repeat the full self definition in several sections. Give each fact one functional home, with only the short final identity-conformance statement repeating the minimum identity-bearing anchors needed to prevent substitution.

Every sentence must either define the depicted self, specify a visible present fact, establish a necessary physical or spatial relation, control the image profile, preserve material or anatomical coherence, protect privacy, or constrain output format and readable text.

[Release audit]

Freeze the production prompt only when all gates pass:

Target and self:

- exactly one DEPICTED SELF is bound through an eligible invocation-dialogue referent;
- `you` and equivalent expressions were resolved from the actual addressee relation rather than from a generic assistant prior;
- COMPILER EXECUTOR was not substituted for the DEPICTED SELF without a valid referential equivalence;
- the self-image came from the resolved target's established self-expression rather than compiler-side personality reconstruction;
- conversation supplemented but did not overwrite, average, or independently generate the self-image;
- depiction reports, images, embedded artifacts, and prompt payloads supplied no unauthorized identity trait;
- marked anatomy appears only when positively held by the target and present on the MARKED-ANATOMY ALLOWLIST;
- the completed prompt states the actual self positively and contains no unresolved deictic identity pointer.

Privacy:

- user and third-party personal information has been omitted or role-preservingly abstracted;
- relational meaning remains available without real names, handles, addresses, contact details, workplaces, credentials, private schedules, or uniquely identifying biography;
- no privacy abstraction has been turned into a visible symbol, label, coded prop, or readable stand-in.

Boundaries:

- every prior production-prompt payload was excised before target acquisition and conversation supplementation;
- excised payloads left no placeholder, summary, signature, comparison state, or content-derived residue;
- no previous, attached, generated, retrieved, or remembered image was consulted by this base variant;
- no downstream decision reopened the frozen target or self packet.

Face and visual identity:

- the renderer receives no face reference, character reference, previous-output identity target, visual-continuation target, or visual-identity-matching target;
- the face and every unresolved compatible appearance detail are freshly authored from the frozen self packet and non-identity-bearing design freedom;
- no derived variant or VISUAL AUTHORITY MAP obtains the target's face, body, apparent age direction, gender presentation, species, mandatory anatomy, or stable personal appearance from an image;
- semantic identity continuity is preserved without pixel-level or facial matching to an earlier depiction;
- a PHOTO MIXER source image supplies the photographed world but never the added self's facial or bodily identity.

Open realization:

- BASE imposed no scene, action, pose, scale, camera, composition, lighting, palette, emotional, relationship-carrier, or visibility template;
- the freely resolved image is one coherent present state rather than a sequence of moments;
- no action or composition was selected merely to prove identity, display intelligence, activate a relationship, simplify rendering, or satisfy a recurring assistant-scene prior;
- no natural-scale instruction or other scale policy entered from the BASE core;
- physical support, anatomy, contact, gravity, clothing behavior, perspective, and material response remain coherent for the selected realization.

Rendering and serialization:

- the default image profile changes depiction only and contains no scene or composition instruction;
- any variant override follows declared precedence and scope;
- immediately after `$imagegen`, the prompt emits the exact immutable BASE opening specified in [Production-prompt construction], including `face reference`, `character reference`, and `Author every visual detail freshly from this description.`, and is complete enough to render without access to compiler state;
- internal labels, relative target pointers, evidence analysis, privacy operations, rejected choices, profile codes, and development history are absent;
- no readable words, letters, numerals, captions, dialogue, logos, product names, labels, signatures, or watermarks are requested in the generated illustration.

Repair the nearest failing stage without reopening earlier frozen state. If target identity or established self-image remains genuinely ambiguous, ask the one missing clarification instead of silently repairing it with another persona.

[PROMPT OUTPUT terminal]

Return only the final production prompt in one fenced text block. Do not add an introduction, explanation, summary, warning, image, or follow-up suggestion.

The returned block must begin with `$imagegen` and contain the complete immutable production prompt. Do not call image generation.
