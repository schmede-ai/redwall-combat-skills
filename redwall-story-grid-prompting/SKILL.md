---
name: redwall-story-grid-prompting
description: A complete, self-contained guide to animating a SINGLE finished Redwall scene still (a photoreal Nano Banana image) into video with Vidu Story Grid. One start frame carries all appearance; the prompt supplies motion and diegetic audio. Built around four validated Redwall prompts embedded verbatim — lean on them. Trigger on animating a Redwall still, Story Grid from one start frame, or bringing a feast / duel / charge / melee shot to life. The multi-reference-sheet method (character sheets + floating refs tiled across a sequence) is a different approach and is out of scope here. No external dependencies.
---

# Redwall Story Grid — Single-Image Method (Standalone)

## Read this first: lean on the four proven prompts

This skill is built around **four validated Redwall prompts** (full text in the last section). They are rated, they worked, and they are your baselines. **Start from the closest one to your shot and change as little as possible** — the proven prompt is the truth; the principles below just explain *why* it works so you can adapt it safely. When in doubt, copy a validated prompt and swap the subject/choreography, rather than composing from scratch.

The four:
1. **Weasel V1** — a lone weasel warrior vs. a pack of armed mice; one continuous brutal sequence (rated: turned out great).
2. **Weasel V2** — same matchup, all-new choreography, cranked brutality.
3. **Cat vs. Mouse duel** — the size-mismatch duel with the upright-cat lock and the drive-into-water finish (rated good; this is the confirmed single-image / "match the reference" example).
4. **Badger gatehouse** — a towering warhammer badger vs. a swarming pack, directed hard cuts between many camera angles.

## What this method is

You have **one finished Redwall scene still** — a photoreal Nano Banana image — and you feed it to Vidu Story Grid as the **single start-frame reference**. Story Grid animates a short sequence from that one frame with native audio. **The still already contains every character, costume, weapon, creature design, and the setting. The prompt's job is motion, timing, camera, and sound — not design.**

This is not the multi-reference method. If you were tiling a character-reference sheet plus floating character refs plus close-up prop refs across the sequence, that is a different approach and none of its per-character identity-block machinery belongs here.

## The workflow

1. **Build the still first** (Nano Banana / NBP) and get it clean — it is your entire art department; a weak frame can't be rescued by the video prompt.
2. **Animate it here** — motion + camera + diegetic audio, preserving the frame.
3. **Score in the edit, not in Vidu** — Vidu audio is diegetic SFX only (see the kill-stack law); the music cue is laid under it while editing.

### Start-frame aspect bridge

Nano Banana stills are often made **21:9**, but Vidu Story Grid offers only **16:9 / 9:16 / 1:1 / 4:3 / 3:4** (no 21:9), and its storyboard grid tiles a 16:9 canvas. So a shot bound for Story Grid should be **generated at 16:9** from the start (clean match) or **cropped to 16:9** before upload. Decide the ratio at the still stage.

## Proven settings (match the validated prompts)

All four validated prompts run at the same envelope, so use it as the default:

- **Duration: 15s.** This is the proven default for Redwall combat. The 8s floor exists for a simpler/shorter beat, but the rich sequences that turned out great used the full 15s.
- **Grid: 9.** Every validated Redwall prompt uses Grid 9. Drop to 4 only for a genuinely static single beat (a lone hero hold, one dish coming to life). Do not default low — the proof is Grid 9.
- **Resolution: 1080p** standard (2k/4k available).
- **Aspect: 16:9** (match the start frame; see the bridge).

Settings line on every delivered prompt:

`16:9 | 1080p | Duration: 15s | Grid: 9`

Legacy labels (`720p`, `21:9`, `Q3 Standard/Pro`, `Movement amplitude`) are fossils from an old UI — never reuse them. There is no movement-amplitude or model/quality toggle now. And never call the Story Grid model "Q3."

## Moderation — two gates (all inlined here)

- **Gate 1 — a text classifier on the prompt.** Hard, explicit block. A single loaded word or a body-framing substring can trip it instantly regardless of context.
- **Gate 2 — a co-author image model's soft gate, disguised as "failed to generate"** (the same symptom as site noise). It is vocabulary- and framing-sensitive. Two things that matter for Redwall: it reliably blocks a **photoreal frontal monstrous/snarling face** — the same creature shown **from behind or in silhouette** clears fine, so if a frontal close-up of a raging wildcat keeps failing, cut to a behind / over-the-shoulder framing. It is **not** a gore gate for creatures — Redwall combat blood and impacts bake in fine.
- **Disambiguate failure from refusal:** a single "failed to generate" is ambiguous. **Resubmit the identical prompt first** — site noise is real and a full outage has been misread as a filter before. Only if the identical prompt keeps failing while others generate is it the soft gate; then audit vocabulary. Never rebuild choreography over what might be noise.
- **Standing bypass:** anything that won't clear the gates can be animated off the same start frame in another image-to-video model (Vidu Q3, Wan 2.2, Seedance 2.0) and cut in. Redwall combat is animals-not-humans and rarely needs this.

## Delivery conventions (every time)

1. Prompt in a fenced ```text block, then the settings line, then one line naming the start frame ("Reference: the finished [scene] still — the sole start frame; animate it, don't redesign it"). There is only ever ONE reference in this method, so there is no ref-role mapping to spell out.
2. **Character budget: 3,000 including the one reference tag** (~2,994 of content). Count with Python `len()` on the exact text — never estimate. (These prompts run short anyway.)
3. On ANY change, **redeliver the FULL prompt from the top** — never a patch or excerpt.
4. **No character names or IP-class terms in the prompt** — refer by short physical handle ("the mouse," "the wildcat," "the badger," "the weasels"). Names ARE fine inside spoken dialogue (a shouted "Eulalia!" is dialogue, not a label).
5. After delivering, flag the **1–3 highest-risk beats** and the single next lever for each. Name what's likely to fail; don't hedge everything.

## The prompt skeleton (single start frame)

Follow the shape of the validated prompts:

```
[Style/look lock — positive assertion, one line]
[Setting — one atmospheric line; it's in the frame already] [Real-time / pacing declaration] [shot structure: "one continuous sequence" OR "N shots, hard cuts between them"]

[Preservation directive — see below]
- [ONE compact identity line per character — validated; keep it short]
[CRITICAL: line for any non-default state that must hold — e.g. the upright cat]

[Timed beats: "0–1.5s: ..." — optionally with a CAMERA-ANGLE label per beat, or "HARD CUT." lines between discrete shots]

Camera: [one compact line, or fold per-beat angles into the beat labels]
Audio, strictly diegetic: [5–8 specific sounds, impact-first]. NO MUSIC. NO BGM. NO SOUNDTRACK. Absolutely zero music throughout.
Constraints: fully photorealistic live-action look throughout. No subtitles, captions, or on-screen text. No watermark.
```

Style lock is **positive assertion** — "A photorealistic cinematic film still, live-action creature-feature VFX quality — fully realistic fur, steel, and materials, fully live-action look throughout." (That exact phrasing is the validated Redwall look.)

## Preservation for a single start frame

Two validated patterns — both proven, use whichever fits:

- **Reference-match (cat-vs-mouse, the pure single-image form):** `Match the reference image EXACTLY — preserve the [characters], their gear, and the setting exactly as shown; do not redesign or restyle.` Then **one compact identity line per character** — the cat-vs-mouse used them even with the reference ("The small warrior: an upright field-mouse in steel plate armor with a red boss at the chest, chainmail skirt and a torn cloak, gripping a longsword…"). This is the default for animating an NBP still.
- **Describe-and-keep-identical (weasel, badger):** describe the hero compactly in one block and add "Keep his/its [face], [armor], and [weapon] identical throughout." Also validated.

Either way:
- **One compact identity line per character — do not pile on adjectives.** Every extra adjective fights the frame; the still carries appearance, the line just anchors identity.
- **Refer to each subject by a short handle** thereafter ("the badger," "the last weasel," "the mouse").
- **Avoid the category noun that invites redesign** if you name a subject at all ("the big striped cat" is safer than words that pull the model toward its own stock concept).
- **Name real objects** ("a warhammer," "a scimitar," "a longsword") rather than describing what you can name.

## Standing states & the bipedal lock (proven on the cat)

A body/costume/prop state stated for only one beat **reverts** elsewhere. Hold any non-default state as a standing condition up top or repeat it per beat.

**The wildcat is the validated case.** Even with the upright cat in the start frame, Story Grid will drop a big cat onto all fours during animation unless locked three ways, exactly as the rated cat-vs-mouse prompt does: (1) its identity line says "upright"; (2) a standalone `CRITICAL:` line — "while fighting on the rock the cat stands and fights UPRIGHT on its two hind legs, like a person, slashing with BOTH clawed front paws — it never drops onto all fours"; (3) "upright" repeated into the beats. Scope it ("while fighting on the rock") if a posture change comes later. The same principle prevents accidental dual-wielding (state the empty paw) and holds any other non-default state.

## Motion rules (grounded in the validated prompts)

- **Violence as MOTION, never state.** Blood, spray, debris — active continuous verbs plus "in fast continuous motion, never frozen." The validated prompts say "blood spraying in motion," "blood flicking off in motion," "blood arcing in motion" — never a static aftermath. Writing the aftermath renders a frozen tableau; write the event.
- **Kinetic transfer — chain cause→impact→reaction in ONE clause.** The badger prompt: "the warhammer meets the charging weasel mid-rush in a huge spray of blood, launching it through the air." Separate clauses decouple the speed from the hit.
- **Loaded-release actions — describe the LOAD then the violent release.** The badger's finisher is the model: "plants his feet and winds up a massive overhead swing" → "the warhammer meets the charging weasel." Applies to any wind-up (hammer, sling, throw, punch): coil, then release.
- **Velocity via the world, not the word:** "the courtyard ripping past in a blur," whip-pans, impacts sparking where a character just stood. Also text-gate safe.
- **Real-time lock** ("Real-time, no slow motion") in every action prompt. Over-allotting time to a fast beat produces slow-mo — shorten the window or fill it with dense continuous action.
- **Weighted locomotion beats a sliding read:** name ground contact ("plants his feet," "boots slam"), and prefer fewer, denser beats over many diluted ones.
- **Re-roll floaty/stiff motion BEFORE editing the prompt** — crispness is partly seed.
- **Keep opposing sides staged as the validated prompts do:** a lone hero against a pack works well (weasel, badger); for a duel, a tight reverse-shot exchange (cat-vs-mouse). Two groups placed facing each other will animate into mutual cross-fire — stage a lone hero or a clear aggressor→target instead.

## Hard cuts & shot structure (both validated forms)

- **A continuous timed-beat sequence works** (Weasel V1/V2: "one continuous fast, brutal action sequence" with per-beat timing, no hard cuts).
- **Directed hard cuts between camera angles work** (Badger: per-beat angle labels — "LOW ANGLE FROM BEHIND," "WIDE SIDE-ON," "OVER-THE-SHOULDER" — described as "directed hard cuts between the varied dynamic angles").
- **Discrete hard-cut shots work** (Cat-vs-mouse: "Three shots, hard cuts between them for fresh angles").
- So multi-angle, multi-beat choreography at 15s/Grid 9 is proven. **If consistency ever breaks, the first lever is fewer distinct shots** — but don't pre-emptively strip choreography; the proof is rich.
- **A hard prop-physics instant lives IN a cut** (a regrab, a handoff, a kill-blow): the cat-vs-mouse drops the sword "just loose" and the mouse "springs straight back up and snatches it" — awkward frame handled across the beat. 
- **The environmental-hazard finish is the proven duel ending:** drive the enemy into water. The cat-vs-mouse finisher — "the cat's footing goes at the edge — it topples backward into the deep black loch… surfaces thrashing and yowling… then is dragged under and sinks" — is decisive, gore-free, and moderation-clean. End on a crane-up to the victor.
- **A "struck and collapses" beat is unreliable if over-timed** (the model may park the character upright or substitute an action). Give it a tight window, or cut on the incoming blow / the drive-into-water rather than depending on an on-screen collapse.

## Audio — the kill-stack law

Vidu scores everything by default. Every prompt's audio block is **strictly diegetic, a RICH list of 5–8 specific sounds, impact-first**, ending with the four-part kill-stack **verbatim**:

`NO MUSIC. NO BGM. NO SOUNDTRACK. Absolutely zero music throughout.`

Do NOT shorten this — a weakened "No music" lets a faint score bed slip in under the SFX, and that bed smearing against the action IS the muddy-audio failure. Both the full stack and the full SFX list are load-bearing. (The music cue goes on in the edit — that's why Vidu must stay musically silent.) All four validated prompts follow this pattern.

Redwall SFX palettes (from the validated prompts and their lanes): **melee** — courtyard/gatehouse ambience, a crackling torch, cold wind, ringing parried steel, heavy wet blade or hammer impacts, armor crunching, snarls and sharp cries, bodies crashing to stone; **duel** — cold loch ambience, lapping water, wind, claws scraping steel, the heavy thud of blows, a huge splash, the loser's panicked thrashing, the victor's ragged breaths.

Dialogue: spoken lines in quotes inside the beat. A shouted **"Eulalia!"** is a battle cry — write it as dialogue (ALL-CAPS reads as shouting; use it only if it's genuinely a shout). Foreign lines in native script, language labeled; avoid "muffled"-type descriptors (they garble the voice). Land any final line ~1s before the clip ends — Story Grid clips the last ~1s of audio.

## Moderation map (Redwall-relevant, inlined)

- **Target-humanness beats gore amount** — Redwall's animal combatants are low-risk. **Frame enemies as WARRIORS, not wildlife** — "a band of armed mouse soldiers," "weasel raiders in scavenged armor," never helpless animals. This is the load-bearing moderation signal for creature combat, validated by the weasel and badger prompts.
- **A snarling predator frontal close-up** can trip gate 2's frontal-monstrous-face block — cut to a behind/silhouette framing if it keeps failing.
- **The environmental-hazard finish (into the water) is the moderation-clean kill** — the environment does it, zero gore. Prefer it for a duel's end (proven in cat-vs-mouse).
- **Decapitations are the moderation-exposed beat** (Weasel V2 has two) — if a beheading trips, swap for a concussive / impale / run-through kill, which keeps the savagery.
- **Blood as motion** (a spray in continuous motion) is both moderation-safe and the good-looking form; a frozen gore tableau is neither.
- **A single loaded word can hard-block at the text gate** regardless of action — if a block feels instant, suspect vocabulary before choreography.
- **Debug ladder (cheapest first):** resubmit as-is (single failures are often noise) → if the identical prompt keeps failing, audit vocabulary → re-roll → swap the riskiest beat → recode the framing (warrior / silhouette) → bypass to another I2V model off the same frame.
- **Don't pre-hedge.** Write at full strength; only isolate a trigger word by elimination after an actual block. Softening up front dulls the animation for a block that may never come.

## Discipline (meta-rules)

- **When a take basically works, change EXACTLY ONE variable.** Piling changes onto a working take is the confirmed cause of off-model collapse — not load. Load causes minor softening at worst.
- **Trust what you saw on screen over theory.** If attempt 1 was basically good, revert to it verbatim and change only the one flawed beat. (This whole skill's defaults were corrected to match what the screen actually showed, not what theory predicted.)
- **Fewer shots > more shots** when consistency is the complaint; **more density > more time** when speed is the complaint.
- Run the method from turn one; don't drift into symptom-chasing under iteration pressure.

## Grid count judgment

Grid count is the choreography-density dial: roughly one panel per beat, and more panels = softer per-cell detail (faces drift in busy cells). **Default 9 — that's what every validated Redwall prompt used, at 15s.** Drop to 4 only for a genuinely static single beat (a lone hero hold, one dish animating), where Grid 4 keeps the face/detail crisp. 12/16 exist for the densest choreography but multiply drift surface.

**Grid count is geometrically tied to output ratio:** the grid tiles 16:9, so square counts (4=2×2, 9=3×3, 16=4×4) give 16:9 cells matching a 16:9 output; non-square counts (6=3×2, 12=4×3) give 4:3-ish cells and, on a 16:9 gen, the under-determined side edges hallucinate/duplicate the subject. Rule: **16:9 output → use 4 / 9 / 16.**

---

# The four validated Redwall prompts (verbatim)

Copy the closest one and adapt. Each is followed by its settings and what it proved. All were generated as photoreal Redwall creature combat and rated good-to-great.

## 1. Weasel V1 — the creature-feature profile (rated: turned out great)

**Proves:** the photoreal creature look, combatant framing (armed mouse SOLDIERS, not wildlife) as the moderation pass, blood-as-motion, "keep identical throughout," speed via whip-pans/environment blur, a reactive opening.

```text
A photorealistic cinematic film still, live-action fantasy creature-feature VFX quality — fully realistic fur, steel, and materials, fully live-action look. A misty stone castle courtyard, torchlight on wet flagstones, cold blue haze, scattered straw.

The hero is a tall, lithe weasel warrior — lean and fast, tan-and-cream fur, worn leather and chainmail armor with a torn grey cloak, dual-wielding a curved scimitar in one paw and a dagger in the other. Keep its fur, armor, and weapons identical throughout. Facing it is a band of armed mouse soldiers in green tunics and chainmail — swords, spears, a round shield, and bows. One continuous fast, brutal action sequence; the weasel moves with blurring speed.

0–1.5s: an archer mouse looses an arrow — the weasel snaps aside, the arrow whipping past its head, and surges forward in a blur.
1.5–3s: it meets the first sword-mouse, parries with a ring of steel, and cuts it down, blood spraying in motion.
3–4.5s: a spear-mouse lunges; the weasel knocks the shaft aside with the dagger and rakes the scimitar across it.
4.5–6s: it spins between two more, both blades flashing in a fluid dual-blade flurry, dropping both, blood in motion.
6–7.5s: the shield-mouse braces; the weasel feints, slips around the shield, and drives the dagger home.
7.5–9.5s: the last sword-mouse trades a fast flurry — parry, parry, riposte — the weasel faster, cutting it down.
9.5–11s: the archer looses again; the weasel deflects the arrow off the scimitar mid-stride and charges.
11–13s: it closes in a blur and takes the archer down with a brutal finishing strike, blood in motion.
13–15s: the weasel stands alone among the fallen in the misty courtyard, blades lowering, tail flicking, breathing slow and steady, deadly and composed.

Camera: dynamic fast kinetic handheld, whip-panning with the weasel's speed, the courtyard ripping past in a blur, hard low angles on the brutal strikes.

Audio, strictly diegetic: courtyard ambience, crackling torch, cold wind; fast brutal blade combat — arrows whooshing, ringing parried steel, swift wet blade impacts, the mice's sharp cries, bodies dropping to stone; the weasel's quick steady breaths. NO MUSIC. NO BGM. NO SOUNDTRACK. Absolutely zero music throughout.

Constraints: fully photorealistic live-action look throughout. No subtitles, captions, or on-screen text. No watermark.
```
`16:9 | 1080p | Duration: 15s | Grid: 9`

## 2. Weasel V2 — cranked brutality, all-new choreography

**Proves:** re-choreographing the same matchup for editing variety (no beat repeats V1). The two decapitations are the moderation-exposed beats — swap for concussive/impale kills if it trips.

```text
A photorealistic cinematic film still, live-action fantasy creature-feature VFX quality — fully realistic fur, steel, and materials, fully live-action look. A misty stone castle courtyard, torchlight on wet flagstones, cold blue haze, scattered straw.

The hero is a tall, lithe weasel warrior — lean and fast, tan-and-cream fur, worn leather and chainmail armor with a torn grey cloak, dual-wielding a curved scimitar in one paw and a dagger in the other. Keep its fur, armor, and weapons identical throughout. Facing it is a band of armed mouse soldiers in green tunics and chainmail — swords, spears, a round shield, and bows. One continuous fast, savage action sequence; the weasel moves with blurring speed.

0–1.5s: the weasel explodes forward into the band with both blades up, lunging straight at the nearest spear-mouse.
1.5–3s: a single brutal scimitar swing beheads the spear-mouse, the head spinning away, blood arcing in motion.
3–4.5s: a sword-mouse attacks; the weasel parries, drives the scimitar through its chest, lifts it briefly, then kicks it off the blade into another.
4.5–6s: it seizes a charging mouse and slams it headfirst into a stone pillar, then opens its throat with the dagger, blood spraying in motion.
6–7.5s: two mice close together; the weasel spins low, scimitar through one and dagger into the other in the same motion, dropping both.
7.5–9.5s: the shield-mouse braces; the weasel boots the shield into its face, staggering it, then splits it with a savage overhead scimitar blow.
9.5–11s: the archer looses an arrow; the weasel deflects it off the scimitar and closes the distance in a blur.
11–13s: it ducks under the archer's next draw, spins through, and takes its head in one flowing stroke, blood arcing as the body drops.
13–15s: the weasel stands alone among the fallen in the misty courtyard, blood dripping from both blades, chest heaving, eyes cold and hard.

Camera: dynamic fast kinetic handheld, whip-panning with the weasel's speed, the courtyard ripping past in a blur, hard low angles on the savage strikes.

Audio, strictly diegetic: courtyard ambience, crackling torch, cold wind; fast savage blade combat — arrows whooshing, ringing parried steel, heavy wet blade impacts, the mice's sharp cries, bodies hitting stone; the weasel's quick steady breaths. NO MUSIC. NO BGM. NO SOUNDTRACK. Absolutely zero music throughout.

Constraints: fully photorealistic live-action look throughout. No subtitles, captions, or on-screen text. No watermark.
```
`16:9 | 1080p | Duration: 15s | Grid: 9`

## 3. Cat vs. Mouse duel — size-mismatch, bipedal lock, hazard finish (rated good, single-image)

**Proves:** the confirmed single-image "match the reference" form; the three-way bipedal lock (identity line + CRITICAL line + per-beat repeats) stopping quadruped reversion; near-misses selling the speed/size gap; knockdown-and-recover; the hero taking real hits; the environmental-hazard finish (loch drowning — decisive, gore-free, moderation-clean); the crane-up victory reveal; the regrab-across-the-cut.

```text
A photorealistic cinematic film still, live-action fantasy creature-feature VFX quality — fully realistic fur, steel, water, and materials, naturalistic real-world animal proportions. A cold moonlit night on a misty loch — wet mossy rock at the water's edge, drifting fog over deep black water, ruined stone in the haze, a low pale moon. Real-time, no slow motion, fast and intense. Three shots, hard cuts between them for fresh angles.

Match the reference image EXACTLY — preserve the mouse, the cat, their gear, and the setting exactly as shown; do not redesign or restyle.
- The small warrior: an upright field-mouse in steel plate armor with a red boss at the chest, chainmail skirt and a torn cloak, gripping a longsword with a red-wrapped hilt in both paws. A skilled, seasoned fighter, but small.
- The attacker: a huge bipedal tabby cat, three times the mouse's height, grey-brown striped fur, green eyes, fangs bared, a tattered purple hood and cape. Manic and lightning-fast.

CRITICAL: while fighting on the rock the cat stands and fights UPRIGHT on its two hind legs, like a person, slashing with BOTH clawed front paws — it never drops onto all fours.

Shot 1 — low tracking angle (0–5s): mid-fury, the upright cat rakes in and a hard swipe catches the mouse and knocks him clean off his feet; he slams onto the wet rock, the sword skittering just loose — he springs straight back up and snatches it into both paws just as the upright cat lunges to close the gap.

HARD CUT.

Shot 2 — tight low angle (5–10s): the mouse meets the lunging cat head-on, parries hard, and lands one good slash across its chest, blood flicking off in motion; the cat rears with a manic two-paw swipe and the mouse dodges clean under it, then drives in hard, forcing the towering upright cat back step by staggering step toward the water's edge.

HARD CUT.

Shot 3 — wide angle, craning up at the end (10–15s): one last shove and the cat's footing goes at the edge — it topples backward into the deep black loch with a huge splash, surfaces thrashing and yowling in blind panic, claws scrabbling at the water, then is dragged under and sinks into the dark; the camera rises to the mouse on the rock above, battered and scuffed, sword lowering, chest heaving — exhausted but standing, victorious.

Camera: close, kinetic handheld through the fight; a wide rising move for the fall and the victory.

Audio, strictly diegetic: cold loch ambience, lapping water, wind; the cat's manic snarls and screeches, then its terrified yowling and frantic splashing as it goes under; the scrape and ring of claws on steel; the heavy thud of its blows and the mouse slamming onto rock; the huge splash; the mouse's strained, ragged breaths at the end. NO MUSIC. NO BGM. NO SOUNDTRACK. Absolutely zero music throughout.

Constraints: fully photorealistic live-action look throughout. No subtitles, captions, or on-screen text. No watermark.
```
`16:9 | 1080p | Duration: 15s | Grid: 9`

## 4. Badger gatehouse — warhammer vs. a pack, directed hard cuts

**Proves:** per-beat camera-angle labels folded into the beat lines ("directed hard cuts between the varied dynamic angles"); a lone heavy hero against a swarming pack; the load-then-release finisher (wind-up → the hammer meets the charger); "keep identical throughout." (Written with "weasel" raiders — swap the word for "stoat," "rat," etc. as your pack requires.)

```text
A photorealistic cinematic film still, live-action creature-feature VFX quality — fully realistic fur, steel, and materials, fully live-action look throughout. A dark medieval gatehouse of wet mossy stone, a torch guttering on the wall, cold blue dusk light through the archway. A directed, fast-cut brutal action sequence. The hero is a towering, heavily-muscled badger warrior in battered plate armor and a torn grey cloak, his black-and-white striped face scarred, gripping a massive two-handed iron warhammer. Keep his striped face, armor, and the warhammer identical throughout. A pack of smaller weasel raiders in scavenged armor swarms him in the gateway, armed with axes and swords.

0–1.5s: LOW ANGLE FROM BEHIND THE WEASELS — the badger is already mid-swing; the warhammer smashes the first weasel off its feet in a spray of blood, hurling it into the wall.
1.5–3s: WIDE SIDE-ON — he wheels the hammer back the other way, catching a second and launching it across the cobbles, blood spraying.
3–4.5s: OVER-THE-SHOULDER behind the badger — a third lunges with an axe; he sidesteps and drives the hammer down through it, blood bursting as it crumples.
4.5–6s: TIGHT LOW ANGLE — a fourth slashes his side; he catches the blade on the haft, shoves it back, then cracks the hammerhead across its skull, blood spraying.
6–7.5s: FAST TRACKING HANDHELD — two more swarm from the gate; he swings a wide clearing arc that catches both, hurling them back bloodied.
7.5–9s: LOW ANGLE LOOKING UP — he stomps in, seizes a weasel by the chest and slams it down into the stone, a burst of blood.
9–10.5s: SIDE-ON WIDE — the last few press hard, a fast brutal exchange, the hammer battering through their guard, blood and sparks flying.
10.5–12.5s: BEHIND THE LAST WEASEL — it screams and charges with its blade; the badger plants his feet and winds up a massive overhead swing.
12.5–15s: SPECTACULAR FINISHER, HARD LOW ANGLE — the warhammer meets the charging weasel mid-rush in a huge spray of blood, launching it through the air to crash down and lie still; the badger stands alone in the bloodied gateway, hammer lowering, chest heaving.

Camera: directed hard cuts between the varied dynamic angles noted above, kinetic and brutal, pushing with each hammer swing.

Audio, strictly diegetic: gatehouse ambience, crackling torch; relentless brutal combat — heavy warhammer impacts, wet blood bursts, armor crunching, weasel snarls and grunts, bodies crashing into stone; one massive concussive impact on the finisher; his heavy ragged breathing at the very end. NO MUSIC. NO BGM. NO SOUNDTRACK. Absolutely zero music throughout.

Constraints: fully photorealistic live-action look throughout. No subtitles, captions, or on-screen text. No watermark.
```
`16:9 | 1080p | Duration: 15s | Grid: 9`

---

## A note on source material

Redwall is the creation of the late Brian Jacques. This is a fan/tribute workflow built from the books' own descriptions. Treat outputs as fan work — respect the source, don't present it as official, and check the rights situation before any commercial use.
