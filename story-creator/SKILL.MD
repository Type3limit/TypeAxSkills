---
name: story-creator
description: Use when Codex needs to create, develop, stress-test, outline, or draft fiction, especially Chinese novels, medium-length stories, high-concept science fiction, suspense, thriller openings, “炸裂开场”, “试读”, “大纲”, cover concepts after the story theme and outline are approved, or stories that need a strong “哇，原来是这样” reveal. Pair with write-like-human whenever prose is drafted or revised so the final text avoids AI-like rhythm, formulaic phrasing, hollow grand statements, and over-neat paragraphing. Pair with imagegen after the user has finalized the story theme and outline and wants a cover image.
---

# Story Creator

## Operating Rule

Use this skill for the story architecture. When producing actual prose, also use `write-like-human` if it is available. Do not duplicate that skill’s whole checklist; apply its standards after drafting: natural rhythm, fewer formulaic turns, specific details, no empty slogans, and paragraph breaks that serve the scene instead of constant short-line suspense.

When the user has approved or clearly settled the story theme and outline, offer or create a cover image if requested. Use `imagegen` for the raster cover art. For Chinese titles, prefer generating a text-free cover background and adding title/subtitle locally afterward, so the cover does not depend on the image model rendering Chinese text correctly.

## Working Assumptions

Start by stating assumptions when the user has not specified genre, length, audience, tone, point of view, or output shape. If the ambiguity changes the story in a major way, ask. If a reasonable default is safe, choose it and name it.

Push back when the premise depends on people ignoring obvious facts. A “炸裂” story still needs to survive common questions about cameras, records, bodies, money, incentives, law, physics, technology limits, and why no one noticed earlier.

## Creation Workflow

1. Define the target.
   - Identify genre, approximate length, tone, and deliverable: idea list, outline, chapter plan, opening sample, full chapter, revision, or saved files.
   - Name the success criteria. Example: “The opening must hook within the first page, the reveal must reframe earlier clues, and the logic must pass a common-sense audit.”

2. Build the premise before writing prose.
   - Create a concrete ordinary system: a job, institution, technology, family rule, public policy, investigation, market, or routine.
   - Add one impossible-looking anomaly that violates that system.
   - Make the anomaly specific enough to dramatize in a scene, not just explain in narration.

3. Design the opening hook.
   - Start with an event that forces action now.
   - Give the protagonist a concrete reason to investigate rather than merely react.
   - Use shock through implication and procedure, not just gore, screaming, or fragmented paragraphs.
   - Keep paragraph rhythm varied. Reserve one-line paragraphs for turns that deserve impact.

4. Design the “原来是这样” reveal.
   - The reveal must re-contextualize earlier facts instead of merely adding a bigger secret.
   - Plant fair clues early: odd wording, procedure gaps, repeated details, institutional behavior, missing data, or a character’s strange caution.
   - Make the reveal answer “why the opening happened that way.”
   - Prefer a reversal of category: victim vs beneficiary, reality vs simulation, rescue vs exploitation, accident vs test, protection vs deletion.

5. Run a common-sense audit.
   - Evidence: What records, bodies, logs, sensors, witnesses, or money trails exist?
   - Institutions: Why do police, hospitals, companies, schools, platforms, or families behave this way?
   - Incentives: Who benefits, who pays, who is afraid, and why now?
   - Technology or speculative rule: What can it do, what can it not do, and what visible side effects does it leave?
   - Reader objection: What would an alert reader challenge first? Fix that before expanding.

6. Outline with escalation.
   - Write a one-sentence story.
   - List the core rule, anomaly, false explanation, true explanation, and cost of knowing.
   - Build chapters around discoveries and choices, not just lore drops.
   - End each major section with changed understanding, changed danger, or a point-of-no-return decision.

7. Generate a cover after approval.
   - Do this only after the user has settled the theme and outline, or explicitly asks for a cover based on the current story.
   - Derive the cover prompt from the story’s genre, core contradiction, protagonist role, setting, key visual motif, color mood, and title.
   - Ask for format only if needed; otherwise default to a vertical 2:3 novel cover.
   - Prefer “no text” in the image prompt for Chinese covers, then add the title locally if a final cover file is needed.
   - Save the cover with the story artifacts when the user gives or implies an output folder.

8. Draft the试读 or chapter.
   - Enter through scene, not premise lecture.
   - Give the protagonist a professional or personal lens that makes the details sharp.
   - Let exposition appear as procedure, conflict, records, conversation, or physical evidence.
   - Avoid explaining the metaphor. Trust the reader.

9. Apply `write-like-human`.
   - Smooth unnatural AI rhythms after the draft exists.
   - Remove overused connective phrases, hollow profundity, fake three-part balance, and repetitive suspense line breaks.
   - Vary sentence and paragraph length.
   - Keep concrete details that make the world feel lived-in.

## Useful Output Shapes

For an early concept:

```markdown
## 方向
## 开场钩子
## 核心设定
## 真正的反转
## 常识合理性检查
## 大纲
```

For a stronger outline:

```markdown
## 书名暂定
## 一句话故事
## 类型与气质
## 核心设定
## 主要人物
## 三层反转
## “原来是这样”的回扣
## 分章大纲
## 主题问题
```

For a试读:

```markdown
## 试读目标
## 试读
## 自检
```

Keep the self-check brief and concrete: hook strength, reveal potential, common-sense risks, prose naturalness.

For a cover after theme and outline approval:

```markdown
## 封面方向
## 画面主体
## 关键视觉钩子
## 色彩与情绪
## imagegen 提示词
## 保存路径
```

Use a text-free image prompt unless the user explicitly wants text generated inside the image. If adding Chinese typography locally, keep the generated art separate from the final titled cover.

## Quality Bar

Do not call an opening “炸裂” because every sentence is short. It is strong when the first page creates a clear contradiction the reader wants resolved.

Do not call a twist good because it is surprising. It is good when the reader can look back and feel the earlier details were hiding in plain sight.

Do not protect a premise by making everyone stupid. Strengthen the system, then show where it fails.
