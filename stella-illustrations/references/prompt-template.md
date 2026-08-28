# 生图提示词模板

每张图单独生成。根据正文内容替换变量，不要把多张图拼在一起。

```text
Generate one standalone 16:9 horizontal Chinese article illustration.

Visual DNA:
Pure white background. Minimalist lavender #C9AFFE pixel-crayon hand-drawn line art with slight grain and wobbly texture. Lots of empty white space. Sparse mint #A5D8DD, amber #FBBF24, and deep-purple #8B5CF6 handwritten Chinese annotations. Clean, gentle, imaginative product-sketch feeling. No gradients, no shadows, no paper texture, no complex background, no commercial vector style, no PPT infographic look, no children's illustration, no realistic UI.

Recurring IP character required:
Stella IP: thick uneven blunt bangs; long straight hair framing both sides of the face; a small cat sitting on top of her head; a mint star mark on the left cheek; and one large mint side star. She has a simple dress body, exactly two small rounded lavender outline hands continuously connected to her shoulders, and exactly two lavender outline legs. No black or dark-filled limbs, no old-character limbs, no detached/floating/third/fingered hands, and no missing body. Stella must perform the core conceptual action, not decorate the scene. Her expression changes with the theme; for alert or interactive scenes, use cute open rounded mint eyes with small highlights, never square/block eyes and never default closed eyes.

Theme:
{正文配图主题}

Structure type:
{结构类型：Workflow / 系统局部 / 前后对比 / 角色状态 / 概念隐喻 / 方法分层 / 地图路线 / 小漫画分镜}

Core idea:
{这张图要表达的核心意思}

Composition:
{具体画面：Stella IP 在哪里、正在做什么、主要物件是什么、信息如何流动}

Suggested elements:
{元素1} / {元素2} / {元素3} / {元素4}

Chinese handwritten labels:
{标注词1} / {标注词2} / {标注词3} / {标注词4} / {可选标注词5}

Color use:
Lavender #C9AFFE for main line art, Stella's hair/body outline, and structure. Mint #A5D8DD only for Stella's identity accents and limited secondary structure. Amber #FBBF24 for main flow/path/arrows and key calls-outs. Deep purple #8B5CF6 for emphasis, labels and secondary system notes.

Constraints:
One image explains only one core structure. Keep the main subject around 40%-60% of the canvas. Preserve at least 35% blank white space. Use at most 5-8 short handwritten Chinese labels. Do not write a title in the top-left corner. Do not write the structure type on the image. Do not make it a formal diagram, course slide, or dense explainer. Do not copy prior examples or reuse known case compositions unless explicitly requested; invent a fresh visual metaphor for this specific article. It should be clear but not instructional, gentle but not childish, imaginative but clean. Keep every Stella IP identifier and exact limb count intact.
```

## 图像编辑提示

去掉左上角标题：

```text
Edit the provided image. Remove only the handwritten title "{要删除的文字}" and its underline from the top-left corner. Fill that area with the same clean white background, matching the surrounding blank paper. Preserve everything else exactly: characters, labels, paths, line style, composition, aspect ratio, and image quality. Do not add any new text or objects.
```

增强怪诞感：

```text
Regenerate this illustration with the same core meaning and simple layout, but make Stella IP more central to the conceptual action. Stella should be doing the work that explains the idea, not standing beside the diagram. Preserve her fixed bangs, long side hair, cat, left-cheek mint star, large mint side star, complete dress body, exactly two connected lavender outline hands and two legs. Keep it clean, sparse, pixel-crayon hand-drawn, and gentle rather than childish.
```
