# CNA Skills Practice

A single-page practice tool for the 23 nurse aide skills on the Credentia skills evaluation.

## Modes

- **Practice Exam**: draws a skill at random, then at random either puts its steps back in
  sequence or asks you to mark its critical element steps (missing one fails the skill).
  Each round is labelled "Determine Order" or "Critical Steps" above the skill name. There
  is no skill picker. Ordering rounds are reordered by dragging a step anywhere on its row;
  press Submit to grade, then Next for another round. On a touch screen a swipe still
  scrolls the list: dragging a row starts after a short hold, or immediately from the
  numbered handle.
- **Skills**: reference rather than testing, with two views. **Focus** (the default) shows
  one skill at a time with Previous/Next buttons that wrap around; **List** shows all 23 as
  collapsible sections with Expand/Collapse all. Both show every step in order with critical
  steps bold and tagged. The chosen view and your place in it survive switching tabs.

Critical steps are shown bold wherever they are revealed, never before, so a "Critical Steps"
round does not give away its own answer.

## Run it

Live at <https://presumablynoob.github.io/cna-skills-practice/>.

Locally, open `index.html` in any browser. No build step and no dependencies.

Hosting is GitHub Pages, serving `main` at the repository root. Pushing to `main` redeploys it.

## Editing skills

All skill data lives in the `S` array near the top of the script in `index.html`. Each skill is
`["Name", [["step text"], ["critical step text", 1], ...]]`, where a trailing `1` marks a critical step.
Both tabs read from that one array.

Skills 5, 17 and 19 currently have no step flagged critical, so Practice Exam always gives them
the ordering task rather than an unanswerable "spot the critical steps" round. Add a trailing `1`
to the relevant steps if your state's handbook marks any.

## Source

Steps are paraphrased from [Credentia's skills page](https://kb-nc.credentia.com/en/article/skills).
Always check against the official candidate handbook for your state. In California, manual blood
pressure (Skill 23) is tested, not electronic (Skill 12).
