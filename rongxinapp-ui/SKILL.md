---
name: rongxinapp-ui
description: Use when a task changes app UI, visible components, layout, styling, navigation, dialogs, cards, settings, lists, forms, color, typography, screenshot-referenced interfaces, or other renderer-facing surfaces in ways that could affect product consistency.
---

# RongxinApp UI

This skill provides a reusable UI governance workflow for app UI work.

The goal is not maximum design freedom.
The goal is to keep product UI consistent while making agent-user UI discussions concrete and efficient.

## When To Use

Use this skill when a task touches:

- pages
- visible components
- spacing
- typography
- color or surface treatment
- navigation
- dialogs, popovers, menus
- cards, lists, settings, forms
- any renderer-facing interaction surface

Use it for both:

- optimizing an existing UI
- adding a new page, module, or local interaction pattern

Do not use it for:

- backend-only changes
- invisible refactors with no UI effect
- purely technical fixes that do not alter the rendered surface

## Required Reading

Read these files before proposing UI changes:

1. `references/design.md`
2. `references/workflow.md`
3. `references/component-rules.md`
4. `references/ui-communication-glossary.md`
5. `references/screenshot-reading.md`

Read these when relevant:

- `references/implementation-rules.md`
  - required if the task includes implementation code
- `references/ui-glossary.md`
  - required when you need pattern-family, color-family, or broader UI terminology

## Hard Gates

Do not implement immediately after recognizing a UI task.
Confirmation is not optional for UI work that involves screenshots, reference images, visual style, layout, hierarchy, density, color, or component treatment.

Before implementation, you must:

1. identify the current `surface`
2. identify the target `module`
3. name the main `issues`
4. propose the intended `adjustments`
5. ask focused decision questions
6. wait for explicit user confirmation before editing

For any of these, user confirmation is required before implementation:

- `module change`
- `new module`
- any task that includes a current screenshot or reference screenshot
- any small change that affects layout, hierarchy, color, typography, pattern choice, or density

No confirmation means no implementation.
If the user provided screenshots, first return a screenshot difference report and adjustment options, then wait.

Do not silently invent a new local UI pattern.

Do not anchor the design discussion on a specific competitor name.

Use generic pattern language such as:

- `centered home workspace`
- `project browsing workspace`
- `capability discovery workspace`
- `capability catalog workspace`
- `board-style task workspace`
- `settings analytics workspace`
- `library browsing workspace`
- `automation onboarding workspace`

Use neutral color-family language such as:

- `cool white base`
- `warm off-white base`
- `keep current neutral palette`

## Execution Contract

### 1. Classify The Change

Classify the task as:

- `small change`
- `module change`
- `new module`

Then identify:

- current surface
- target module
- closest existing pattern
- shell and hierarchy constraints

Use `references/workflow.md` for the full step-by-step process.

### 2. Run The Confirmation Loop

Before implementation, return a structured UI reading:

```text
Current surface:
Target module:
Observed issues:
Proposed improvements:
Pattern direction:
Color direction:
Density direction:
Need your decision on:
```

Minimum required fields:

- `Current surface`
- `Target module`
- `Observed issues`
- `Proposed improvements`

Use `references/ui-communication-glossary.md` for:

- issue naming
- adjustment language
- decision prompts
- response patterns

Use `references/screenshot-reading.md` for:

- reading screenshot structure before proposing edits
- translating vague visual feedback into specific UI issues
- comparing the current UI and the reference UI on a small number of concrete axes

If screenshots are involved, include:

- `Reference reading`
- `Current mismatch`
- `Likely cause`
- `Recommended adjustment paths`
- `Need your decision on`

Then stop and wait for the user.
Do not edit files in the same response unless the user has already confirmed the proposed path.

### 3. Implement Only After Direction Is Clear

After the user confirms the direction:

- write a short design direction
- follow `references/workflow.md`
- obey `references/component-rules.md`
- obey `references/implementation-rules.md` when code changes are involved

Do not invent a new local UI pattern unless the user has explicitly confirmed that direction.

## Communication Rules

When discussing UI, do not rely on vague phrases like:

- `make it cleaner`
- `make it better`
- `make it more advanced`
- `make it more modern`

Instead, structure communication as:

1. `surface`
2. `module`
3. `issue`
4. `adjustment`
5. `decision`

For non-trivial UI tasks, also confirm:

6. `pattern direction`
7. `color direction`
8. `density direction`

## Vocabulary Routing

Use `references/ui-communication-glossary.md` for:

- page names
- module names
- component names
- issue names
- adjustment verbs
- confirmation and response templates

Use `references/screenshot-reading.md` for:

- screenshot analysis order
- visual contrast pairs
- screenshot-to-decision prompts
- converting "feels off" feedback into concrete design questions

Use `references/ui-glossary.md` for:

- broader pattern families
- surface and structure terminology
- visual and interaction vocabulary
- neutral color-family language

## Completion Standard

A UI task is complete only when:

- the feature works
- the surface still feels like the same product
- no unnecessary new pattern was introduced
- code structure remains reasonable
- key states were checked
- the design direction was clear before implementation
- the final UI was reviewed against skeleton, hierarchy, surface treatment, density, control language, and product consistency
- visual verification is confirmed by an updated user screenshot or explicitly marked as pending user review

Use `references/workflow.md` for the detailed done standard and verification sequence.
