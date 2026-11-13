# CNA Skills Practice

A single-page practice tool for the 23 nurse aide skills on the Credentia skills evaluation.

## Modes

- **Put steps in order**: a skill's steps are shuffled; tap them back into sequence.
- **Spot critical steps**: mark the critical element steps (missing one fails the skill).
- **Recall flashcards**: say each step out loud, then reveal it.
- **Quick quiz**: random multiple-choice questions on tolerances, angles, critical steps and "what comes next."

## Run it

Open `index.html` in any browser. No build step and no dependencies.

To host it, enable GitHub Pages (Settings → Pages → Deploy from branch → `main` / root).

## Editing skills

All skill data lives in the `S` array near the top of the script in `index.html`. Each skill is
`["Name", [["step text"], ["critical step text", 1], ...]]`, where a trailing `1` marks a critical step.
Fact-quiz questions are in the `FACTS` array.

## Source

Steps are paraphrased from [Credentia's skills page](https://kb-nc.credentia.com/en/article/skills).
Always check against the official candidate handbook for your state. In California, manual blood
pressure (Skill 23) is tested, not electronic (Skill 12).
