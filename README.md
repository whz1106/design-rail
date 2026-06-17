# Design Rail

Design Rail is a UI workflow skill for coding agents.

It helps agents and developers keep frontend UI changes consistent by requiring:

- screenshot difference analysis before implementation
- focused user confirmation for UI direction
- shared UI terminology for vague visual feedback
- conservative module-level changes before broad redesigns
- reuse of existing components, theme tokens, and product patterns
- screenshot-driven user review after implementation

## Skill

The current skill lives in:

```text
rongxinapp-ui/
```

Use it when a task changes app UI, visible components, layout, styling, navigation, dialogs, cards, settings, lists, forms, color, typography, screenshot-referenced interfaces, or other renderer-facing surfaces in ways that could affect product consistency.

## Core Flow

1. Identify the target surface and module.
2. Read current and reference screenshots when provided.
3. Return a screenshot difference report.
4. Ask focused decision questions.
5. Wait for explicit user confirmation.
6. Implement the smallest confirmed UI change.
7. Ask for user screenshot review when visual quality matters.

## Repository Scope

This repository is intended to contain the reusable skill and its maintained references.
Local competitor screenshots, copied third-party skills, and exploratory materials are intentionally excluded from version control.
