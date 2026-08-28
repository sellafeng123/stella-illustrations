# Stella Illustrations Visual Identity Design

## Goal

Convert the repository from Ian Xiaohei's visual identity to Stella's IP identity without changing the article-analysis workflow, shot-list flow, image-generation loop, output paths, image naming rules, or composition-selection logic.

## Confirmed naming

- Public project name: `Stella Illustrations`.
- Installed skill directory and Skill name: `stella-illustrations`.
- User-facing invocation: `$stella-illustrations`.
- The previous names `Ian Xiaohei Illustrations`, `ian-xiaohei-illustrations`, and `小黑` must not remain in user-facing visual documentation or generation prompts.

## Immutable Stella IP contract

Every generated character uses this identity unless the task explicitly asks for an object-only illustration:

- Thick, uneven blunt bangs; long straight hair framing both sides of the face.
- A small cat sits on the top of the head.
- Mint-green left-cheek star mark and one large mint side star.
- Lavender pixel-crayon outline; primary colors `#C9AFFE` and `#A5D8DD`.
- Simple dress body, exactly two lavender line arms/hands and exactly two lavender line legs.
- Hands are small, rounded, outline-only lavender pixel-line hands. They always connect to shoulders; no black, dark-filled, Xiaohei-style, detached, third, or fingered hands.
- The face can vary with the scene. Eyes must be cute and open when the theme calls for alertness; expressions must support the narrative rather than default to closed eyes. The character must remain recognisable.

## Visual DNA

- Wide 16:9 Chinese article illustration, sparse clean white background, large breathing room.
- Hand-drawn pixelated crayon grain: lavender as the dominant line color, mint for identity accents and secondary structure, amber/orange for flow arrows and key calls-outs, deep purple for emphasis.
- Short handwritten Chinese labels remain part of the explanatory composition.
- The mood is gentle, imaginative, approachable, and lightly whimsical; it remains an explanatory article image rather than a commercial key visual, presentation slide, dense flowchart, or product UI.

## Files to modify

| Path | Change | Must remain unchanged |
| --- | --- | --- |
| `README.md` | Rename project and installation/call examples; rewrite visual identity and examples around Stella's IP. | Section order, workflow description, output location and directory overview. |
| `examples/prompts.md` | Replace old Skill invocation, IP mention, color/style requirements and editing prompts. | Prompt scenarios and planning/generation/editing workflow. |
| `ian-xiaohei-illustrations/` → `stella-illustrations/` | Rename the installed visual-skill directory. | Internal workflow order, `agents/openai.yaml`, asset layout, output conventions. |
| `stella-illustrations/SKILL.md` | Rename frontmatter and rewrite only IP/style/generation/QA wording. | Five-step workflow, shot-list quantities, individual image generation, asset saving and output format. |
| `references/xiaohei-ip.md` → `references/stella-ip.md` | Replace character definition with the immutable Stella IP contract. | File role and cross-reference behaviour. |
| `references/style-dna.md` | Replace colors, medium, mood and visual prohibitions. | Requirements for 16:9, white background, brevity, whitespace and one core idea. |
| `references/prompt-template.md` | Replace the recurring character and visual-DNA prompt block; add hands/limbs/expression invariants. | Template variables, single-image structure and composition constraints. |
| `references/qa-checklist.md` | Replace Xiaohei checks with Stella IP continuity and hand/limb checks. | QA/iteration/acceptance structure. |
| `assets/examples/` and `examples/images/` | Replace old-character sample pixels while preserving all existing filenames and counts. | Directory paths, filenames, ordering and README image links. |

## Reference image mapping

The twelve user-selected images in `Desktop/reference图` are the authoritative visual calibration samples. They are matched to their similarly named example slots. Where the installed skill has an additional sample slot, the corresponding completed Stella output already in this workspace is copied into that same existing filename; no slot is deleted and no image-generation workflow is changed.

The examples remain calibration assets only. The Skill continues to prohibit copying an example composition unless the user explicitly asks to reproduce it.

## Non-goals and guardrails

- Do not alter composition-pattern selection, article parsing, shot-list logic, step numbering, generation count, output path `assets/<article-slug>-illustrations/`, or image naming pattern.
- Do not add product functionality, dependencies, scripts, workflows, or a new output format.
- Do not modify `LICENSE`, `NOTICE.md`, Git history, or unrelated repository metadata.
- Do not leave an old black character, Xiaohei hand, old visual description, or old Skill invocation in user-facing generation materials.

## Verification

1. Search the renamed repository for legacy identity references in active README, Skill, prompt, QA and example-prompt files.
2. Check that the prescribed workflow and asset/output paths match the pre-change content.
3. Verify every referenced example file exists with its original filename.
4. Visually inspect copied examples for Stella's cat, bangs, cheek star, mint side star and valid limbs when a character appears.
5. Confirm `$stella-illustrations` is the only documented invocation.
