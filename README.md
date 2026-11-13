# CNA Skills Practice

A single-page practice tool for the 23 nurse aide skills on the Credentia skills evaluation.

## Modes

Every mode draws a skill at random; there is no skill picker.

- **Step practice**: a random skill, then at random either putting its steps back in
  sequence or marking its critical element steps (missing one fails the skill).
- **Recall flashcards**: say each step out loud, then reveal it.
- **Quick quiz**: random multiple-choice questions on tolerances, angles, critical steps and "what comes next."

## Run it

Live at <https://presumablynoob.github.io/cna-skills-practice/>.

Locally, open `index.html` in any browser. No build step and no dependencies.

Hosting is GitHub Pages, serving `main` at the repository root. Pushing to `main` redeploys it.

## Editing skills

All skill data lives in the `S` array near the top of the script in `index.html`. Each skill is
`["Name", [["step text"], ["critical step text", 1], ...]]`, where a trailing `1` marks a critical step.
Fact-quiz questions are in the `FACTS` array.

Skills 5, 17 and 19 currently have no step flagged critical, so step practice always gives them
the ordering task rather than an unanswerable "spot the critical steps" round. Add a trailing `1`
to the relevant steps if your state's handbook marks any.

## Source

Steps are paraphrased from [Credentia's skills page](https://kb-nc.credentia.com/en/article/skills).
Always check against the official candidate handbook for your state. In California, manual blood
pressure (Skill 23) is tested, not electronic (Skill 12).
