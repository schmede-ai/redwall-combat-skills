# Redwall Combat Skills

Two Claude Skills for making Redwall-style animal combat videos with AI — armored mouse warriors, weasel duelists, sword fights in torchlit courtyards.

They cover the two halves of the pipeline:

| Skill | What it does |
| --- | --- |
| **redwall-image-prompting** | Photoreal cinematic Redwall stills in Nano Banana 2 / Pro. House style, lore constraints (species scale, weapons, clothing and materials), the model quirks that bite on this kind of imagery, and safety-filter workarounds. |
| **redwall-story-grid-prompting** | Animating a finished still into video with Vidu Story Grid. One start frame carries the appearance, the prompt carries motion and diegetic audio. Built around four validated prompts included verbatim. |

Both are standalone — no external dependencies, no other skills required. Use them together or on their own.

---

## Install

### On claude.ai (web or desktop)

1. Download the skill you want:
   - [**redwall-image-prompting.zip**](https://github.com/schmede-ai/redwall-combat-skills/raw/main/zips/redwall-image-prompting.zip)
   - [**redwall-story-grid-prompting.zip**](https://github.com/schmede-ai/redwall-combat-skills/raw/main/zips/redwall-story-grid-prompting.zip)
2. In Claude, go to **Customize → Skills**
3. Click **+**, then **Create skill**
4. Choose **Upload a skill** and pick the `.zip`

Works on Free, Pro, Max, Team and Enterprise. Skills you upload stay private to your own account.

> Getting a "missing required SKILL.md" error? That happens when a file gets zipped instead of the folder. The zips linked above are already shaped correctly — use those rather than re-zipping.

### In Claude Code

Drop the folder into `~/.claude/skills/` to have it everywhere, or `.claude/skills/` inside a single project.

```bash
git clone https://github.com/schmede-ai/redwall-combat-skills.git
cp -r redwall-combat-skills/redwall-image-prompting ~/.claude/skills/
cp -r redwall-combat-skills/redwall-story-grid-prompting ~/.claude/skills/
```

### Just want to read them

Open the `SKILL.md` inside either folder. They're plain text — you can paste the contents into a chat if you'd rather not install anything.

---

## How to use them

Once installed you don't invoke anything. Ask for what you want and the right skill loads on its own:

- *"Make me a Redwall image prompt — a mouse warrior in chainmail holding the abbey gate"*
- *"Write a Story Grid prompt to animate this still"*
- *"My character keeps changing between shots, fix this prompt"*

Claude hands back a finished prompt in a code block, ready to paste into the generator.

## The pipeline

1. **Generate the still** — a photoreal cinematic frame of the moment you want
2. **Animate it** — feed that still into Vidu Story Grid as the start frame and prompt the motion
3. **Cut it together** — assemble the clips in any editor

## What you'll need

- A Claude account for the skills themselves
- Access to Nano Banana 2 / Nano Banana Pro for the stills
- A Vidu account for Story Grid
- An editor to cut the finished clips

---

## Notes

These are prompting skills — not models, not software. They encode what actually works: the failure modes, the phrasing that survives generation, the settings that matter. The point is to skip the part where you learn it the hard way.

Made by [Schmede](https://schmede-ai.github.io). Not affiliated with Redwall, the estate of Brian Jacques, Google, or Vidu.
