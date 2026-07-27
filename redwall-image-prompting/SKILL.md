---
name: redwall-image-prompting
description: A complete, self-contained playbook for making lore-accurate, style-consistent Redwall (Brian Jacques) images with Nano Banana 2 / Nano Banana Pro. Covers Nano Banana fundamentals from zero, a proven photoreal cinematic house style with paste-ready locked blocks, Redwall lore constraints (species scale, weapons, clothing/materials), the specific model quirks and fixes for this kind of imagery, safety-filter workarounds, and a lore-plausibility checklist. No external dependencies.
---

# Making Redwall Images — A Complete Playbook
### Photoreal cinematic stills with Nano Banana 2 / Pro

This is a standalone guide to producing **Redwall Abbey–style images** — armored mouse warriors, feasting woodlanders, Long Patrol hares, sea-rat hordes, towering badgers and wildcats — as **photoreal cinematic film stills** that look like frames from a live-action creature feature and stay visually consistent shot to shot.

You don't need any prior experience with these tools. Part 1 teaches the model from scratch; Part 2 gives you a complete, proven look you can use as-is; the rest keeps you lore-accurate and shows you how to fix the specific things that go wrong. Everything you need is in this one document.

> **Scope:** This is a fan/tribute framework built on Brian Jacques' Redwall world (the books). It works entirely from the novels' descriptions. See the short note on source material at the end.

---

## Part 1 — Nano Banana fundamentals (start here)

**What Nano Banana is.** Nano Banana 2 (NB2) and Nano Banana Pro (NBP) are Google's Gemini-based image models (you'll find them in Freepik/Magnific, Google's Gemini apps, and elsewhere). Crucially, they are **not** old-style "tag" image generators. They *reason* about your prompt — intent, physics, composition, spatial relationships. That single fact changes how you write for them.

**Rule #1 — brief it like a director talking to a human artist, not like you're tagging.** Write full, natural sentences that describe the scene the way you'd explain it to a person. Do NOT write keyword salad.
- ✗ `mouse, armor, sword, cat, night, cinematic, 4k, detailed`
- ✓ `A small armored mouse warrior stands his ground on wet stone at night, sword raised two-handed, facing a wildcat twice his height that looms over him snarling.`

**Rule #2 — when you use a reference image, describe the *change*, not the whole picture.** If you feed the model a reference that already shows a character's face or costume, don't re-describe what's visible in it — that makes the model average the reference against your words and drift the likeness. Instead lock it ("keep the face exactly from the reference, do not change it") and describe only what's new: the new pose, action, lighting, or location. (This matters once you start building a cast and reusing characters across shots.)

**NB2 vs NBP — which to pick.**
- **NB2:** fast, great for iterating and for simple single-subject shots.
- **NBP:** slower but reasons harder — use it for **anything with multiple characters, precise scale relationships, or crowds**, and for polished final images. Most Redwall scenes here (feasts, duels, charges) want NBP.

**How to actually run a prompt.** Paste the finished prompt text into your generator. Then set two things **in the app's controls, NOT in the prompt itself**:
- **Aspect ratio:** use **21:9** (wide cinematic scope) — it suits the anamorphic look and wide standoffs. 16:9 is fine when you need it.
- **Resolution:** highest available.

Aspect ratio and resolution are UI settings; putting them inside the prompt text does nothing useful.

**If you have to fix a prompt, replace the whole thing.** When a result is wrong and you adjust the wording, regenerate from the **entire, complete prompt** — don't try to paste in just the changed sentence. These prompts are long and the pieces interact; always work from the full text.

---

## Part 2 — The house style (a complete, proven look)

The goal is that every image cuts together as if from **one film**. The method is **locked blocks**: certain paragraphs get pasted **word-for-word into every shot and never reworded**. You only change the shot-specific subject, action, and composition. This is what keeps the grade, mood, and "camera" consistent across an entire sequence.

Three things stay constant across every shot: **the head**, **the lighting register**, and **the grade tail**.

### The head (locked except the camera angle)

```text
A photorealistic cinematic film still, live-action fantasy creature-feature VFX quality — fully realistic fur, materials and animal anatomy, no illustration or cartoon styling. Shot on an ARRI Alexa Mini LF, [FOCAL]mm anamorphic lens, f/2.8, [ANGLE — the one part you write fresh per shot].
```

Treat focal length like swapping lenses on a real camera, not a random dial:
- **32mm** — wide / establishing shots, landscapes, big standoffs
- **40–50mm** — medium shots, characters, two-ups
- **65–75mm** — food hero shots and tight detail

Angles skew **low** — "a low hero angle," "low from the waterline," "a steep worm's-eye angle looking up." Low angles are the house style *and* your main tool for making big things loom (more on that under scale).

### Lighting registers — pick ONE per scene, then lock it across that scene

**COMBAT / EXTERIOR — cold dawn** (day duels, skirmishes, charges):
```text
Lighting: low-key and dramatic — cold blue dawn light as the dominant fill across the water and mist, a low rising sun just cresting the horizon throwing warm gold rim-light along [the subjects], deep shadow falloff; the mist catching the warm light.
```

**COMBAT / EXTERIOR — night** (moonlit duels; pair with the "realism push" in Part 5):
```text
Lighting: low-key, dramatic and nocturnal — soft directional moonlight spilling in from off-frame as the cool key, faintly silvering the mist, the wet stone and the rippled water and tracing a thin cool rim along [the subjects], with only the faintest warm undertone; deep crushed shadow falloff into the black night, strong naturalistic contrast.
```

**FEAST / INTERIOR — warm hall** (the Abbey feast):
```text
Lighting: warm-dominant and low-key — golden candlelight and lantern light as the key on the food and fur, deep blue twilight from the stained-glass windows as the cool fill and rim, deep shadow falloff into the hall.
```

**The dual-temperature rule (do not break it).** The look is always a **cool key + warm accent** (or warm key + cool accent, for the feast). And the warm source must be **plausibly there in the world** — a hearth/candle/torch indoors, the rising sun outdoors, or a low warmed moon at night. Never put a torch on bare open ground with nothing burning. Flat single-temperature light (e.g. pure blue moonlight with no warm anywhere) goes dead and kills the whole look — always give the warmth somewhere to come from.

### The grade tail (locked — pick day or night)

**Day / exterior / feast:**
```text
Photorealistic cinematic film still — Kodak Vision3 tones, warm gold highlights, teal-grey shadows, crushed blacks, fine 35mm grain, atmospheric haze. No text, no labels, no humans, no naked figures.
```
*(Feast variant ends: "…atmospheric haze with dust motes in the light. No text, no labels, no humans, no human figures.")*

**Night / maximum realism:**
```text
Natural-history photographic realism — Kodak Vision3 tones, cool moonlit blues, restrained highlights, teal-grey shadows, crushed blacks, fine 35mm grain, atmospheric haze. No text, no labels, no humans, no naked figures, no other animals.
```

### The settings line for every prompt

```
21:9 | Highest resolution | NBP
```
(Use NB2 instead of NBP only for simple single-subject shots.)

---

## Part 3 — How to write the prompt (block order)

Assemble every prompt in this order. Not every shot needs every block, but this sequence works:

1. **Head** — medium + camera + the shot's angle (from Part 2).
2. **Foreground subject** — the hero, described concretely: build, fur color/texture, gear and its materials, expression, weapon, pose. Specificity = control. ("A small, slight mouse warrior with brown fur in a battle-worn riveted steel breastplate…" beats "a mouse in armor.")
3. **Midground / background subjects** — secondary characters, described more softly.
4. **Scale + cast line** — the relative sizes of the species present, and the rule that everyone is a clothed anthropomorphic animal (see Part 4; this block does double duty as your anti-error insurance).
5. **Setting** — a specific place with concrete detail (time of day, textures, what's around).
6. **Lighting** — paste the chosen register from Part 2.
7. **Depth of field** — say explicitly what's razor sharp and what dissolves to soft bokeh. ("The two fighters razor sharp, the misted lake behind dissolving into cool anamorphic bokeh.")
8. **Grade tail** — paste from Part 2.

**Anti-patterns to avoid:**
- **Tag soup** — write sentences, not comma-lists of keywords.
- **Over-prompting** — contradictory or excessive detail confuses the model; keep it coherent.
- **Vague placement** — say "left foreground" / "center of frame," not just "on the left."
- **Describing a change instead of an end-state** — say where a thing *ends up*, not "move it left."
- **Generic lighting** — never "good lighting"; always name source, direction, and color temperature (the registers do this for you).

---

## Part 4 — Staying lore-accurate (the Redwall rules)

These keep your images faithful to the books. Most are also error-prevention.

### Species scale hierarchy — this drives every multi-species shot

Biggest to smallest: **Badgers / wolverines** (tower over everyone, broad as ~3 mice) → **Wildcats** (just below, ~2–4× a mouse) → **Otters & hares** (a full head-and-shoulders above the small folk, lean) → **Mice, squirrels, moles, hedgehogs, voles** (the small band, roughly equal) → **Shrews** (smallest).

**Always anchor a size difference TWO ways that agree — a ratio AND a body-part cue.** If the number and the body cue disagree, the model follows the body cue and ignores the number. Use this conversion:

| Size ratio | Body-part cue (the small one's head reaches…) |
|---|---|
| ~2× | the big one's **waist** |
| ~3× | the big one's **mid-thigh / just above the knee** |
| ~3.5–4× | the big one's **knee** |

- To make something **loom without changing its size**, drop the camera **low and look up**. Do *not* write "towering," "fills the frame," or "huge foreshortening" as the way to get scale — the model reads those as *literally giant* and blows the proportions. State the ratio + body cue for size; use the low angle for drama.
- If a small character keeps rendering **too chunky/large**, fix its *build* — "small, slight, slender, diminutive" — and make the small one smaller rather than enlarging the big one.
- The model tends to **undershoot** big height gaps, so if it's still not dramatic enough, bump the body-part cue up one notch.

### Clothing & materials

- **Everyone is fully clothed** in simple medieval homespun — habits, smocks, jerkins, tunics, aprons, sashes. Fur covers the body; **no bare skin or bare torsos**. State this in your cast line *and* in the tail negatives.
- **Hares (Long Patrol) are medieval, NOT modern.** Never use the bare word "military" — it drags in khaki, brass buttons, WW1 uniforms. Write **"a simple buff homespun tunic, a faded green sash knotted across one shoulder."** If khaki still creeps in, escalate to **"undyed oat-colored homespun tunic."**
- Light species wear **light kit** (leather jerkins, rope belts). **Heavy forged plate only on big species** (badgers). Otters wear light skirmisher jerkins, never plate (unless it's a ceremonial ruler figure).
- **Tableware and props are wood, earthenware, stoneware, and iron. No glass** — it isn't in the world. Serve trifles in **wide earthenware bowls** with the layers shown where a spoon scooped. (Stained-glass *windows* are fine — that's architecture, not dishware.)

### Weapons by species

- **Mice:** sword (the great hero blade is bright pale meteoric steel with a red stone in the pommel — never rusty or plain), short blades, sling.
- **Hares (Long Patrol):** sabre, longbow, sling, **lance** (a long thrusting spear used *on foot* — there is no hare cavalry). Battle cry **"Eulalia!"**, shouted together, most often at the charge.
- **Badgers:** oversized axe, war hammer, mace, or great battle sword; plus claws and berserk fury. Also cry "Eulalia!".
- **Otters:** **sling + double-pointed javelin** are the signature (best thrown as a group volley); blade and bow as secondary. The best slingers in the world. Led by a "Skipper."
- **Squirrels:** the **archers** — bow first, sling second.
- **Shrews:** rapier, sling, bow.
- **Hedgehogs:** natural spines; some carry daggers.
- **Rats / sea-rats / corsairs:** cutlass, scimitar, dagger, hook.
- **Stoats / weasels / ferrets:** crude mismatched blades, spears, bows; they fight as **ragged snarling hordes** in scavenged armor (spiked iron helmets, red sashes, studded leather) — chaos, not clean formation.
- **Foxes:** cunning, poison, trickery, the occasional bolas.
- **Wildcats:** claws and fangs; **blazing green eyes**, heavy grey-brown tabby coat, thick black-ringed bushy tail, a tattered **purple warlord's cape**. They stand and fight **upright on their hind legs** (dropping to all fours only for a charging lunge). Note: the classic wildcat villain fights her great duel **unarmoured, with no weapon** — pure claws and fangs.
- **No beavers.** Beavers are not part of this world. If you want a water-and-wood fighter, use an **otter**.

### Speech (only if you're doing dialogue / lip-sync)

Species that speak in plain English (best for spoken lines): **mice, squirrels, otters** (light sea-dog flavor — "matey," "ahoy"), **hedgehogs**. Avoid heavy dialects for dialogue (moles and sparrows are written in thick phonetic accents), and go easy on the hares' "wot wot, jolly good" patter.

---

## Part 5 — Model quirks & fixes for this kind of imagery

These are the specific things that go wrong when making Redwall images, and how to fix each.

- **Scale looks wrong / the big creature shrinks** → your number and body cue disagree; the model followed the body cue. Make them match (Part 4 table). Still not dramatic enough? Push the body cue up a notch.
- **A whirling sling renders wrong** (a floating ring, a stiff stick, the whole sling flung, or a stone flying detached from the cord) → the model **cannot draw a fast-spinning cord in a still image**. Don't try to freeze the spin. Two poses that DO work: **(a)** the wound-up throw — two straight taut cords from paw to pouch, stone still in the pouch, body coiled; **(b)** the overhead swing frozen at the top of the arc — arm raised high overhead, cord hanging in a slack U-curve down to a raised pouch, stone still cupped. Add negatives: "no spinning circular sling shapes, no forked sticks, no slingshots." (True spinning motion is a job for a video/animation tool, not a still.)
- **A sling looks like a slingshot** → the giveaway is the arm. A **sling** has the arm raised **overhead**; a **slingshot** is pulled back toward the face. Write "overhead" and negate "slingshot / forked Y-frame."
- **Random humans or naked figures appear** → state the "everyone is a clothed anthropomorphic animal" rule in the cast line **and** repeat it in the tail negatives ("no humans, no human figures, no naked or bare-skinned figures"). If one shot keeps leaking, change its background from "a crowd of shapes" to a **specific counted handful of named creatures**.
- **The character count drifts** → state the number **twice** ("exactly six … , no more") — once in the body, once in the cast line — and **re-roll** if it overshoots. Exact counts aren't perfectly reliable.
- **Crowds turn to mush** → beyond ~12 figures the model fuses limbs and faces, and any face smaller than ~5% of the frame degrades. Keep **2–3 sharp foreground figures plus soft background bodies**, cap the count, and use a low silhouette angle to hide the messy dense areas.
- **A small armored figure vanishes into a dark night** → put it on the **moonlit side** so the rim-light catches its metal, and nudge the key up ("a little more moonlight on the figures") rather than adding a second light.
- **A reared-up cat drops to all fours** → write "standing upright on its two hind legs like a warrior," and re-roll if needed.
- **You want maximum photographic realism** (to get "real animal" instead of "great CG") → open the prompt with **"indistinguishable from a real wildlife photograph, natural-history documentary realism"** and add micro-detail cues: "true-to-life fur with individual strands and natural grooming, fine micro-detail in skin, claws, weathered steel and worn cloth." Pair with the night grade tail.

---

## Part 6 — Paste-ready locked blocks

### Universal cast + no-humans line (combat / exterior)
```text
Every figure is an anthropomorphic [SPECIES] with fur covering the body, no bare skin. No humans, no naked figures, and no other creatures anywhere in the scene.
```

### FEAST scene — the locked trio (paste all three, verbatim, into every feast shot)

Setting:
```text
Setting: a close, table-level slice of a medieval abbey feast hall at dusk — warm red sandstone wall soft in the background, the base of a great fluted column, the deep blue glow of a tall stained-glass window blurred beyond, one long oak feast table crowded with dishes, blossoms strewn over cream linen, lit close by candelabras, beeswax candles and small hanging lanterns.
```
Scale + cast:
```text
Creature scale and cast, consistent throughout: mice, squirrels, moles and hedgehogs are small creatures of roughly equal height; otters and hares stand a full head-and-shoulders taller and leaner; badgers tower over everybeast, broad as three mice. Every figure in the scene is an anthropomorphic woodland animal, fully clothed in simple medieval homespun — monastic habits, smocks, jerkins, tunics and aprons. No humans anywhere in the scene.
```
Then add the **feast warm-hall lighting register** and the **feast grade tail** from Part 2.

**Feast staging tips:** keep the architecture a **soft, partial slice** (column base + blurred window glow) — never show the whole hall, because partial + out-of-focus is exactly where architectural inconsistency stops being visible. Food is the star: shoot **stations** (a pie station, soup station, ale station, cake station) with the hero dish tack-sharp and the characters as warm soft shapes behind. High-recognition dishes: the golden domed **Deeper'n'Ever Pie** (beet-purple and cream filling when cut open), red-orange **shrimp-and-hotroot soup** in an iron cauldron, dark foamy ale in wooden tankards, bright pink cordial in wooden beakers, a tiered sugared **great cake**, pale meadowcream, glossy candied chestnuts. Keep the mood warm-through-abundance-and-ceremony.

### COMBAT / DUEL scene — pattern

Combat settings change per scene, so write them fresh — but two **lore-rich defaults** work beautifully: a **river ford** (an otter's home ground: wet rocks, reeds, mist, an ambush at the crossing) and a **misty lakeshore strewn with half-sunk fortress rubble** (a ruined, flooded castle — and water in frame quietly foreshadows a wildcat's doom, since wildcats fear water). Then paste your chosen **combat lighting register** + **grade tail** + the **universal cast line**.

---

## Part 7 — A full worked example

A single-hero shot with every block assembled, so you can see how it fits together. Copy it, then swap the subject to make your own.

```text
A photorealistic cinematic film still, live-action fantasy creature-feature VFX quality — fully realistic fur, materials and animal anatomy, no illustration or cartoon styling. Shot on an ARRI Alexa Mini LF, 50mm anamorphic lens, f/2.8, a low hero angle from the water's edge looking up at a lone otter on a rocky river ford at cold dawn.

Foreground, tack sharp: a single anthropomorphic river otter standing braced on the wet rocks, lean and powerfully muscled with sleek rich-brown waterproof fur darkened and dripping with river water, a pale cream throat, a long thick rudder-tail out for balance, webbed paws. It wears a weathered leather jerkin and a rope belt with a small stone-pouch, a short dirk sheathed at the hip. It holds a loaded sling wound up in the overhead position — the arm raised high above the head, the cord hanging in a slack U-curve down to a pouch swung up and out to the side, the stone still cupped in the pouch — coiled to loose, eyes locked downriver.

Every figure is an anthropomorphic otter with fur covering the body, no bare skin. Exactly one otter in the scene. No humans, no naked figures, no other creatures, no spinning circular sling shapes, no slingshots.

Setting: a rocky river ford in deep woodland at cold dawn — wet moss-slick boulders, rushing shallow water breaking white over stones, tall reeds and rushes along the banks, thin mist rising off the river, pale blue early light, the far bank lost in haze.

Lighting: low-key and dramatic — cold blue dawn light as the dominant fill across the water and mist, a low rising sun just cresting the trees throwing warm gold rim-light along the otter's wet fur and raised sling, deep shadow falloff; the mist catching the warm light.

Depth of field: the otter and its raised sling razor sharp, the misted far bank dissolving into cool anamorphic bokeh.

Photorealistic cinematic film still — Kodak Vision3 tones, warm gold highlights, teal-grey shadows, crushed blacks, fine 35mm grain, atmospheric haze. No text, no labels, no humans, no naked figures.
```
```
21:9 | Highest resolution | NBP
```

---

## Part 8 — Safety-filter workarounds

These models sometimes throw **false refusals** on legitimate creative work — combat scenes, quasi-religious abbey imagery, dramatic peril. If a fair, non-graphic Redwall prompt gets blocked:

- **Switch the style label first.** Identical content described as "professional film still," "editorial photography," or "natural-history photograph" passes more often than the same thing labeled loosely. Vague prompts get read pessimistically by the filter.
- **Add production/craft framing** — "a cinematic concept frame," "a museum-quality illustration" — which reads as legitimate creative work.
- **Name it fictional** — "a fictional character, not based on any real person" — if a description could be misread as a real individual.
- **Swap trigger words for plain ones** — clinical/neutral vocabulary instead of loaded terms.
- **Don't resubmit the identical blocked prompt** — change the wording before retrying; repeated identical blocks can look like circumvention.

**Hard limits that won't (and shouldn't) be worked around:** sexual content involving minors, realistic depictions of real named people in compromising situations, and weapons-of-mass-destruction instructional imagery. Some major named IP characters and realistic named individuals are also restricted — if a Redwall character name gets blocked, describe the character physically instead of naming it.

---

## Part 9 — Lore-plausibility checklist

Before you generate, run the scene past these six:

1. **Weapons match the species?** (mouse = sword; hare = sabre/lance/sling; otter = sling/javelin; squirrel = bow; shrew = rapier; badger = axe/mace; rat = cutlass; wildcat = claws.)
2. **Size gap right, and anchored two ways that agree?** (ratio + body-part cue.)
3. **Everyone clothed, medieval materials, no glass, no modern hare uniforms?**
4. **Terrain suits the fighters?** (otters → water; wildcats → dry ground and doomed near water; hares → open ground for a charge, not dense forest for lances.)
5. **No off-world species?** (no beavers, no humans.)
6. **Lighting is dual-temperature with a warm source that makes sense in the scene?**

All six pass → it's faithful. Build it.

---

## A note on the source material

Redwall is the creation of the late **Brian Jacques**, across his novels. This playbook works only from the books' own descriptions, and it exists to help fans make tribute imagery in that world. The models can use character names as anchors, but treat this as fan work: respect the source, don't pass it off as official, and check the rights situation before doing anything commercial with Redwall-based images.
