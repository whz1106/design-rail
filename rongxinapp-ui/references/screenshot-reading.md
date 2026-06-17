# Screenshot Reading

Use this file when the user provides screenshots, visual references, or vague feedback such as:

- `不像参考图`
- `这里感觉不对`
- `不够高级`
- `太乱了`
- `太重了`
- `不像 codex/workbuddy 那种感觉`

The goal is not to guess a full redesign from taste words alone.
The goal is to translate visual feedback into a small number of concrete UI decisions.

## 1. Read Screenshots In A Fixed Order

Do not start from color.
Read the screenshot in this order:

1. `surface`
2. `layout skeleton`
3. `visual center`
4. `module hierarchy`
5. `surface treatment`
6. `density`
7. `control language`
8. `tone`

## 2. What To Extract

### 2A. Surface

Identify the page type first:

- `assistant home surface`
- `project workspace surface`
- `project dashboard surface`
- `settings surface`
- `library surface`
- `detail surface`

### 2B. Layout Skeleton

Describe the main structure:

- `single-column`
- `two-column`
- `three-column`
- `centered composition`
- `left-led composition`
- `split workspace`
- `sidebar + workspace`

Good question:

`这里要保持当前的 sidebar + workspace 骨架，只调模块样式，对吗？`

### 2C. Visual Center

Identify what visually dominates the page:

- `centered composer dominant`
- `list dominant`
- `card grid dominant`
- `detail panel dominant`
- `sidebar dominant`
- `utility controls dominant`

Good question:

`你想让视觉重心继续放在输入区，还是把内容区提得更高？`

### 2D. Module Hierarchy

Identify primary, secondary, and background modules:

- `primary module`
- `secondary module`
- `supporting module`
- `background module`

If multiple modules compete equally, call it out:

- `hierarchy too flat`
- `hierarchy too scattered`

### 2E. Surface Treatment

Describe how modules are framed:

- `flat`
- `light card`
- `heavy card`
- `panel-like`
- `overlay-like`
- `border-led`
- `fill-led`

Good question:

`你这里更想要轻卡片感，还是更接近平面面板？`

### 2F. Density

Describe spacing and scan rhythm:

- `compact`
- `balanced`
- `open`
- `scan-dense`
- `scan-loose`

Good question:

`这里的问题更像信息太松散，还是太挤？`

### 2G. Control Language

Describe component character:

- `rounded stronger`
- `rounded restrained`
- `border visible`
- `border quiet`
- `primary action loud`
- `primary action restrained`
- `input presence strong`
- `input presence quiet`

### 2H. Tone

Describe the overall product feel:

- `tool-like`
- `workbench-like`
- `editor-like`
- `dashboard-like`
- `promotional`
- `decorative`
- `calm`
- `sharp`
- `soft`

## 3. Use Contrast Pairs Instead Of Loose Adjectives

When the user gives vague feedback, translate it into a contrast pair.

Prefer:

- `card feel too heavy / too light`
- `border presence too strong / too weak`
- `spacing too loose / too tight`
- `hierarchy clear / scattered`
- `primary action too loud / too hidden`
- `surface too flat / too layered`
- `utility too exposed / too buried`
- `input area dominant / content area dominant`
- `page too dashboard-like / more workbench-like`
- `tone too decorative / more tool-like`

Avoid stopping at:

- `cleaner`
- `more advanced`
- `more modern`
- `nicer`
- `better looking`

## 4. Translate Vague Feedback

Use this table mentally during discussion.

### User says: `不像参考图`

Possible meaning:

- skeleton mismatch
- hierarchy mismatch
- card weight mismatch
- density mismatch
- control language mismatch

Agent follow-up:

`我先不把它理解成颜色问题。更像是骨架、卡片重量和密度没有对齐参考方向。我先按这三项来复述。`

### User says: `太丑了`

Possible meaning:

- too many competing elements
- visual center unclear
- spacing rhythm broken
- component language inconsistent

Agent follow-up:

`我先把它具体化：现在更像是层级发散和模块语言不统一，不是单一颜色问题。你是希望先收紧层级，还是先减轻卡片和边框存在感？`

### User says: `太重了`

Possible meaning:

- cards too heavy
- borders too dark
- fills too strong
- shadows too obvious

Agent follow-up:

`这里我会优先理解成卡片感过重和边框存在感过强。你想把它收敛到轻卡片，还是更接近平面面板？`

### User says: `太乱了`

Possible meaning:

- hierarchy too flat
- too many accents
- spacing rhythm inconsistent
- utilities competing with content

Agent follow-up:

`这里更像信息层级发散，不一定是模块太多。你想保留现有内容量，只把主次关系拉开，对吗？`

### User says: `不够高级`

Possible meaning:

- too decorative
- too template-like
- card framing too obvious
- spacing and alignment not controlled enough

Agent follow-up:

`我先把“不够高级”翻译成：模板感偏重、约束不够强、面板和控件语言不够克制。你更希望它往更安静的工具感走，对吗？`

## 5. Compare Current UI To Reference UI

When both current and reference screenshots exist, compare them on only a few axes:

1. `skeleton`
2. `visual center`
3. `surface treatment`
4. `density`
5. `control language`

Return the comparison like this:

```text
Reference reading:
- Skeleton: sidebar + workspace
- Visual center: centered composer dominant
- Surface treatment: light card with quiet borders
- Density: balanced, slightly compact
- Control language: restrained rounded controls

Current mismatch:
- Skeleton is close, but the visual center is weaker
- Card framing is heavier than the reference direction
- Spacing is looser, so the page scans less like a workbench
```

## 5A. Screenshot Difference Report Template

When the user provides both a current app screenshot and a reference screenshot, return this before proposing code changes:

```text
Reference reading:
- Surface:
- Skeleton:
- Visual center:
- Module hierarchy:
- Surface treatment:
- Density:
- Control language:
- Tone:

Current mismatch:
- Skeleton:
- Hierarchy:
- Surface treatment:
- Density:
- Control language:

Likely cause:
- [name the smallest likely cause, such as card weight, border presence, loose spacing, weak visual center, or inconsistent controls]

Recommended adjustment paths:
1. Conservative: keep the current skeleton and adjust only [surface / density / control language].
2. Medium: keep the main structure but rebalance [hierarchy / visual center / module grouping].
3. Strong: introduce a new local pattern only if the user approves it.

Need your decision on:
1. [one concrete contrast-pair decision]
2. [one concrete contrast-pair decision]
```

The agent should recommend the conservative or medium path by default.
Use the strong path only when the current skeleton clearly cannot support the user goal.
After returning this report, stop and wait for the user's decision.
Do not implement changes in the same response as the first screenshot difference report.

## 6. Screenshot-To-Decision Pattern

Before proposing UI implementation, compress the reading into decision questions.

Good pattern:

```text
Based on the screenshot, the main gap is not feature structure.
It is that the current module is heavier and looser than the reference direction.
I would keep the current skeleton, reduce card weight, quiet the borders, and tighten the scan rhythm.
Need your decision on:
1. stay light-card, or go flatter?
2. keep current density, or tighten it one step?
3. keep the input area secondary, or raise it visually?
```

Bad pattern:

```text
I understand, I will make it more modern.
```

## 7. Hard Rules

- Do not claim a screenshot is mainly a color problem unless structure and hierarchy were checked first.
- Do not ask the user for open-ended design direction when a narrower contrast pair can be offered.
- Do not mirror the user's vague adjective without translating it into a UI issue.
- Do not jump from screenshot reference directly into implementation.
- Do not treat `make it better`, `make it more modern`, or `just follow the screenshot` as sufficient implementation approval.
- Do not implement until the user has confirmed an adjustment path, target module, and at least one concrete design axis such as density, surface treatment, hierarchy, or control language.
