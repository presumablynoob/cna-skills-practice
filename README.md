# CNA Skills Practice

A single-page practice tool for the California nurse aide skills test, covering both test
providers used in the state. Every step is quoted in the provider's own wording, not paraphrased.

## Providers

A toggle at the top switches the whole app between the two, and **Credentia is the default**.
Switching reloads both tabs against that provider's list.

| | Skills | Steps | Critical steps | Video walkthroughs |
|---|---|---|---|---|
| **Credentia** | 23 | 286 | 27 | 22 of 23 |
| **Headmaster** | 18 | 451 | 36 | none |

The two lists are not the same material. Headmaster bundles tasks that Credentia keeps separate
(its bedpan skill also covers measuring urine output and hand washing), so its skills are fewer
but much longer – up to 49 steps against Credentia's 20. Check which provider your test site uses before drilling.

## Modes

- **Practice Exam**: draws a skill at random, then at random either puts its steps back in
  sequence or asks you to mark its critical element steps (missing one fails the skill).
  Each round is labelled "Determine Order" or "Critical Steps" above the skill name. There
  is no skill picker. Ordering rounds are reordered by dragging a step anywhere on its row;
  press Submit to grade, then Next for another round. A skill longer than `MAXORDER` (20) is
  drilled as one random run of consecutive steps rather than all of it at once, and the round
  says which run, as in "Steps 14-33 of 48"; Reshuffle keeps that run, Next draws a new one.
  No Credentia skill is long enough to be split; most Headmaster ones are. On a touch screen a swipe still
  scrolls the list: dragging a row starts after a short hold, or immediately from the
  numbered handle.
- **Skills**: reference rather than testing, with two views. **Focus** (the default) shows
  one skill at a time, with a dropdown to jump straight to a skill and Previous/Next buttons
  that wrap around; **List** shows every skill as a collapsible section with Expand/Collapse
  all. Both show every step in order with critical steps bold, italic and tagged, and under
  Credentia, Focus also embeds that skill's video walkthrough. The chosen view and your place
  in it survive switching tabs. Graded lists in Practice Exam keep critical steps bold only.

Critical steps are shown bold wherever they are revealed, never before, so a "Critical Steps"
round does not give away its own answer. A skill with no critical step flagged always draws the
ordering task instead, so a round is never unanswerable.

## Run it

Live at <https://presumablynoob.github.io/cna-skills-practice/>.

Locally, open `index.html` in any browser. No build step and no dependencies.

Hosting is GitHub Pages, serving `main` at the repository root. Pushing to `main` redeploys it.

## Editing skills

Both lists live in the `PROV` object near the top of the script in `index.html`:

```js
PROV.credentia.skills = [ ["Skill name", [["step text"], ["critical step text", 1], ...]], ... ]
```

A trailing `1` marks a critical element step. `PROV.<provider>.videos` is index-aligned with that
provider's `skills`; `null` means no video for that skill, and `videos: null` (Headmaster) drops
the video section entirely. `blurb`, `src`, `srcName` and `note` fill the subtitle and the footer.

## Sources

Step wording is quoted verbatim, so corrections belong upstream rather than here.

- **Credentia** — [California candidate handbook skills list](https://kb-nc.credentia.com/en/article/skills).
  Critical element steps are the ones that page sets in bold. In California, manual blood
  pressure (Skill 23) is tested, not electronic (Skill 12).
- **Headmaster** — [California Mock Skills](https://hdmaster.com/assets/ca-mock-skills.pdf)
  (PDF, effective for testing 1 February 2026). Critical steps are the ones set in bold in that
  document; the steps are extracted from the PDF text, with each step's `a.`/`b.` sub-points and
  scoring criteria folded into it. Headmaster states these steps are guidelines for preparing
  candidates, not complete care.

Always check against the official candidate handbook for your state before the exam.

Video walkthroughs come from the [Credentia CNA Skills (Updated)](https://www.youtube.com/playlist?list=PL7D7SigffS4ms3_ff_0mGLx55c0sgRlg7)
playlist by XY Nursing Skills, who state they are not affiliated with Credentia. The playlist has
no video for Credentia skill 12 (electronic blood pressure), so that skill links to the playlist
instead. There is no equivalent playlist for Headmaster. Embeds use `youtube-nocookie.com`, and
only the focused skill's player is on the page at a time.
