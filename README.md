# Redwall Combat Skills

Two Claude Skills for making Redwall-style animal combat videos with AI. Armored mouse warriors, weasel duelists, sword fights in torchlit courtyards.

## Download

| | |
| --- | --- |
| **[Download the image skill](https://github.com/schmede-ai/redwall-combat-skills/raw/main/zips/redwall-image-prompting.zip)** | Photoreal cinematic Redwall stills in Nano Banana 2 / Pro |
| **[Download the video skill](https://github.com/schmede-ai/redwall-combat-skills/raw/main/zips/redwall-story-grid-prompting.zip)** | Animating those stills into video with Vidu Story Grid |

Both are standalone. No other skills required, no dependencies. Grab one or both.

## Install (2 minutes)

1. Download a `.zip` above
2. Open Claude and go to **Customize → Skills**
3. Click **+**, then **Create skill**
4. Choose **Upload a skill** and pick the `.zip`

That's it. Works on every Claude plan, including free. Skills you upload stay private to your own account.

> Don't unzip the file first, and don't re-zip it. Upload the `.zip` exactly as downloaded.

## Using them

You don't have to invoke anything. Ask Claude for what you want and the right skill loads on its own:

- *"Make me a Redwall image prompt. A mouse warrior in chainmail holding the abbey gate."*
- *"Write a Story Grid prompt to animate this still."*
- *"My character keeps changing between shots, fix this prompt."*

Claude hands back a finished prompt in a code block, ready to paste into the generator.

## The pipeline

1. **Generate the still.** A photoreal cinematic frame of the moment you want.
2. **Animate it.** Feed that still into Vidu Story Grid as the start frame and prompt the motion.
3. **Cut it together.** Assemble the clips in any editor.

You'll need a Claude account for the skills, access to Nano Banana 2 or Nano Banana Pro for the stills, a Vidu account for Story Grid, and an editor to cut the finished clips.

---

## Other ways to get them

**Read them first.** Open the `SKILL.md` inside either folder above. They're plain text. You can paste the contents into a chat if you'd rather not install anything.

**Claude Code.** Drop the folder into `~/.claude/skills/` to have it everywhere, or `.claude/skills/` inside a single project.

```bash
git clone https://github.com/schmede-ai/redwall-combat-skills.git
cp -r redwall-combat-skills/redwall-image-prompting ~/.claude/skills/
cp -r redwall-combat-skills/redwall-story-grid-prompting ~/.claude/skills/
```

---

These are prompting skills, not models or software. They encode what actually works: the failure modes, the phrasing that survives generation, the settings that matter. The point is to skip the part where you learn it the hard way.

Made by [Schmede](https://schmede-ai.github.io). Not affiliated with Redwall, the estate of Brian Jacques, Google, or Vidu.
