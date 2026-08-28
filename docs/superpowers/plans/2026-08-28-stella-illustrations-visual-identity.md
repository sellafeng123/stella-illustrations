# Stella Illustrations Visual Identity Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the Ian Xiaohei visual identity with Stella's IP throughout the public documentation, installed Skill, prompts, QA rules and calibration images while preserving every content-analysis and image-output workflow.

**Architecture:** Keep the existing repository layout and workflow verbatim, but rename the installable Skill directory to `stella-illustrations` and rewrite only the identity-bearing text inside it. Reuse the supplied Stella reference images and the already-approved project outputs as drop-in sample assets under their existing filenames, so README links and generation paths continue to work unchanged.

**Tech Stack:** Markdown documentation, YAML agent metadata, PNG calibration assets, Git.

**Spec:** `docs/superpowers/specs/2026-08-28-stella-illustrations-visual-identity-design.md`

## Global Constraints

- Public project name, Skill directory, YAML display name and invocation are `Stella Illustrations` / `stella-illustrations` / `$stella-illustrations`.
- Do not change article parsing, shot-list quantities, structure-type selection, individual-image generation, output path `assets/<article-slug>-illustrations/`, or output numbering.
- Preserve the existing directory depth and every image filename under `examples/images/` and `stella-illustrations/assets/examples/`.
- Every active IP description enforces bangs, side hair, cat, left-cheek mint star, mint side star, two connected lavender outline arms/hands, two legs, and theme-matched cute expressions.
- No active user-facing visual prompt may retain Xiaohei, black-character, or `$ian-xiaohei-illustrations` instructions.
- Keep `LICENSE`, `NOTICE.md`, historical Git data and unrelated author/legal metadata unchanged.

---

### Task 1: Rename the installed Skill and replace all visual identity rules

**Files:**
- Rename: `ian-xiaohei-illustrations/` → `stella-illustrations/`
- Modify: `stella-illustrations/SKILL.md`
- Modify: `stella-illustrations/agents/openai.yaml`
- Rename: `stella-illustrations/references/xiaohei-ip.md` → `stella-illustrations/references/stella-ip.md`
- Modify: `stella-illustrations/references/style-dna.md`
- Modify: `stella-illustrations/references/prompt-template.md`
- Modify: `stella-illustrations/references/qa-checklist.md`
- Modify: `stella-illustrations/references/composition-patterns.md`

**Interfaces:**
- Consumes: the immutable IP contract in the approved design spec.
- Produces: an installable `$stella-illustrations` Skill whose flow and paths match the prior Skill.

- [ ] **Step 1: Rename the installed directory and IP reference file without moving its subdirectories**

Run:

```bash
mv ian-xiaohei-illustrations stella-illustrations
mv stella-illustrations/references/xiaohei-ip.md stella-illustrations/references/stella-ip.md
```

- [ ] **Step 2: Update frontmatter and internal reference links**

Set `SKILL.md` frontmatter `name: stella-illustrations`; change its title and all active references to `references/stella-ip.md`. In `agents/openai.yaml`, set:

```yaml
interface:
  display_name: "Stella IP 正文配图"
  short_description: "为中文文章生成温柔像素蜡笔风、有 Stella IP 的正文配图资产"
  default_prompt: "Use $stella-illustrations to 为这篇中文文章设计并生成几张 Stella IP 正文配图。"
```

- [ ] **Step 3: Replace the IP definition with the approved immutable contract**

Write `references/stella-ip.md` with the exact visual anchors, hand/limb prohibitions, allowed theme-driven expression changes, and core-action requirement from the approved design spec. Keep the original document sections—role, appearance, personality, common responsibilities, prohibitions and acceptance test—so the skill's reasoning flow does not change.

- [ ] **Step 4: Replace the style DNA and prompt template blocks**

In `style-dna.md` and the `Visual DNA`, `Recurring IP character required`, `Color use` and `Constraints` blocks in `prompt-template.md`, replace black/red/orange/blue Xiaohei rules with:

```text
Clean white 16:9 canvas; lavender #C9AFFE pixel-crayon linework; mint #A5D8DD IP accents; amber/orange #FBBF24 flow arrows and key callouts; deep purple #8B5CF6 emphasis; sparse short handwritten Chinese labels.
```

Add the mandatory IP rules: cat on head, fixed bangs and side hair, mint cheek star and side star, exactly two connected lavender outline hands and two legs, no black/Xiaohei limbs, and expression tied to the scene.

- [ ] **Step 5: Update QA and composition language without changing their logical lists**

Replace every `小黑` identity check and action reference in `qa-checklist.md` and `composition-patterns.md` with `Stella IP` wording, preserving each existing structure type, object pool, action pool, originality rule and checklist order. Add explicit failures for closed-eye defaulting when the scene needs alertness, square/block eyes when a cute open expression is requested, extra limbs, detached hands and black limbs.

- [ ] **Step 6: Validate the active installed Skill**

Run:

```bash
rg -n 'ian-xiaohei-illustrations|\$ian-xiaohei-illustrations|小黑|黑色实心' stella-illustrations README.md examples/prompts.md
test -f stella-illustrations/SKILL.md
test -f stella-illustrations/references/stella-ip.md
test ! -e ian-xiaohei-illustrations
```

Expected: no legacy identity hits in active visual-generation material; the renamed Skill and IP reference exist; the old Skill directory does not.

- [ ] **Step 7: Commit the self-contained Skill migration**

```bash
git add -A stella-illustrations ian-xiaohei-illustrations
git commit -m "feat: migrate skill to stella visual identity"
```

### Task 2: Update public README and reusable prompts without changing workflow documentation

**Files:**
- Modify: `README.md`
- Modify: `examples/prompts.md`

**Interfaces:**
- Consumes: the renamed Skill and visual contract from Task 1.
- Produces: public installation and usage instructions that invoke `$stella-illustrations` while retaining the original workflow and asset path contracts.

- [ ] **Step 1: Replace public naming, description and visual bullets in README**

Change the title, opening summary, default IP description, visual-style section, installation copy and example calls to Stella. Set the clone URL to `https://github.com/sellafeng123/stella-illustrations.git`. Preserve the existing headings for purpose, outputs, workflow, directory structure, limitations and notes.

- [ ] **Step 2: Preserve all process/output contracts verbatim**

Keep the README's 4–8 shot-list guidance, 16:9 output, individual generation loop, `assets/<article-slug>-illustrations/` delivery path and numbered PNG convention unchanged. Update only nouns/adjectives that identify the previous IP or visual palette.

- [ ] **Step 3: Update all copyable prompt examples**

Replace `$ian-xiaohei-illustrations` and all Xiaohei/black-line/anti-cute wording in `examples/prompts.md` with `$stella-illustrations`, lavender pixel-crayon style, Stella IP action requirements, connected-limb constraints and theme-matched expressions. Retain each existing example scenario and its request shape.

- [ ] **Step 4: Verify public documentation references**

Run:

```bash
rg -n 'ian-xiaohei-illustrations|\$ian-xiaohei-illustrations|Ian Xiaohei Illustrations|小黑' README.md examples/prompts.md stella-illustrations
rg -n 'assets/<article-slug>-illustrations/|01-topic-name\.png|4-8' README.md stella-illustrations/SKILL.md
```

Expected: the first command reports no active legacy visual identity; the second confirms unchanged output location, numbering and shot-list guidance.

- [ ] **Step 5: Commit documentation migration**

```bash
git add README.md examples/prompts.md
git commit -m "docs: update public stella illustration guidance"
```

### Task 3: Replace calibration images in place and verify asset layout

**Files:**
- Modify in place: `examples/images/01-two-breakpoints.png` through `examples/images/08-trust-bridge.png`
- Modify in place: `stella-illustrations/assets/examples/01-two-breakpoints.png` through `stella-illustrations/assets/examples/14-trust-bridge.png`

**Interfaces:**
- Consumes: user-selected images in `/Users/stella/Desktop/reference图/` and approved Stella PNGs in the current workspace output folder.
- Produces: unchanged example asset paths whose pixels no longer depict the black original IP.

- [ ] **Step 1: Copy each supplied reference image into its matching sample slot**

Use these source-to-target mappings, preserving target filenames:

```text
01-two-breakpoints.png -> examples/images/01-two-breakpoints.png
03-sort-by-purpose.png -> examples/images/02-sort-by-purpose.png
03-one-fish-many-uses.png -> examples/images/03-one-fish-many-uses.png
04-handoff-path.png -> examples/images/04-handoff-path.png
10-information-well-hand-redrawn.png -> examples/images/05-information-well.png
Codex 图像 2026年8月28日 18_13_54.png -> examples/images/06-idea-press.png
12-content-fermentation.png -> examples/images/07-content-fermentation.png
14-trust-bridge-ip-hand-restored.png -> examples/images/08-trust-bridge.png
```

For the last source, use the approved project output at `outputs/ip-illustrations-v2/14-trust-bridge-ip-hand-restored.png` because it is the current confirmed bridge version.

- [ ] **Step 2: Populate all fourteen installed-Skill calibration paths without deleting any slot**

Copy the user-selected files into `stella-illustrations/assets/examples/` while preserving the installed Skill's current filenames:

```text
01-two-breakpoints.png                    -> 01-two-breakpoints.png
02-minimum-loop.png                       -> 02-minimum-loop.png
03-sort-by-purpose.png                    -> 03-sort-by-purpose.png
03-one-fish-many-uses.png                 -> 04-one-fish-many-uses.png
04-handoff-path.png                       -> 05-handoff-path.png
按目的分类.png                              -> 06-three-sources.png
<approved Stella output>                  -> 07-three-content-jobs.png
08-handoff-copy-toolbox.png               -> 08-handoff-copy-toolbox.png
09-common-pits-no-title.png               -> 09-common-pits.png
10-information-well-hand-redrawn.png      -> 10-information-well.png
Codex 图像 2026年8月28日 18_13_54.png        -> 11-idea-press.png
12-content-fermentation.png               -> 12-content-fermentation.png
13-system-bearing-expression.png          -> 13-system-bearing.png
14-trust-bridge-ip-hand-restored.png      -> 14-trust-bridge.png
```

Only `07-three-content-jobs.png` has no directly selected counterpart; use its approved Stella output from `outputs/ip-illustrations-v2/`. This keeps every original path present without reviving the old IP.

- [ ] **Step 3: Verify dimensions, filenames and legacy-pixel replacement**

Run:

```bash
test "$(find examples/images -type f -name '*.png' | wc -l | tr -d ' ')" = 8
test "$(find stella-illustrations/assets/examples -type f -name '*.png' | wc -l | tr -d ' ')" = 14
sips -g pixelWidth -g pixelHeight examples/images/*.png stella-illustrations/assets/examples/*.png
rg --files examples/images stella-illustrations/assets/examples | sort
```

Then visually inspect every copied source sample, confirming the cat, bangs, mint cheek star, mint side star and absence of black/Xiaohei limbs whenever the IP appears.

- [ ] **Step 4: Commit sample asset replacement**

```bash
git add examples/images stella-illustrations/assets/examples
git commit -m "assets: replace examples with stella ip calibration"
```

### Task 4: Final migration audit

**Files:**
- Verify: repository root and `stella-illustrations/`

**Interfaces:**
- Consumes: Tasks 1–3.
- Produces: evidence that only the visual identity changed and the functional workflow remains intact.

- [ ] **Step 1: Audit the repository diff for scope**

Run:

```bash
git diff HEAD~3..HEAD --stat
git diff HEAD~3..HEAD -- README.md examples/prompts.md stella-illustrations/SKILL.md stella-illustrations/references
```

Expected: modifications are limited to visual identity documentation, renamed Skill metadata/references and example PNGs; no scripts, dependencies, workflow code or output-path logic change.

- [ ] **Step 2: Run final identity and structure checks**

Run:

```bash
rg -n 'ian-xiaohei-illustrations|\$ian-xiaohei-illustrations|小黑|黑色实心' README.md examples stella-illustrations || true
test -d stella-illustrations/assets/examples
test -f stella-illustrations/agents/openai.yaml
test -f stella-illustrations/references/composition-patterns.md
git status --short
```

Expected: no active legacy-identity text, all required directories/files exist and the worktree is clean after commits.

- [ ] **Step 3: Deliver the migration summary**

Report the renamed Skill invocation, the exact installable directory, asset verification counts, preserved workflow constraints and commits created. Provide links to the new README and `stella-illustrations/SKILL.md`.
