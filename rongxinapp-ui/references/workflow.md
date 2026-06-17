# UI Change Workflow

Follow this workflow for any UI-related change.

This workflow is mandatory for both developers and coding agents.

## 1. Trigger Conditions

This workflow applies whenever a task changes:

- layout
- spacing
- typography
- component styling
- navigation
- dialogs, menus, or popovers
- lists, cards, settings, or other visible modules
- any renderer-facing interaction surface

UI work must not be treated as a generic coding task.

## 2. Read The Design Contract First

Before editing, read:

1. `design.md`
2. `component-rules.md`
3. `implementation-rules.md`

Do not edit UI first and rationalize the change later.

## 3. Identify The Target Surface

Before implementation, identify:

- the user task supported by the surface
- the module type being changed
- the closest existing pattern in the app
- the visual hierarchy that must remain stable
- the theme and shell constraints that already exist

If an existing pattern fits, extend that pattern instead of inventing a new one.

## 4. Classify The Change

Classify the task before implementation:

- `Small change`: local spacing, copy, alignment, state, or control adjustment
- `Module change`: meaningful adjustment to one existing module or surface
- `New module`: new page section, new module, or new interaction pattern

The larger the change, the more explicit the design direction must be.

## 5. Run A UI Confirmation Loop

Before implementation, the agent must confirm the UI direction with the user.
This is a hard gate.
The agent must not implement UI changes in the same response that first analyzes screenshots or proposes design direction.

This is required for:

- all `module changes`
- all `new modules`
- any `small change` that affects style, hierarchy, layout, color, typography, or pattern choice
- any task that includes a current screenshot, reference screenshot, or vague visual feedback

This confirmation loop exists to avoid silent UI interpretation drift.

The agent must not jump from "I understand the task" directly to editing code when design choices are still ambiguous.
If screenshots or reference images are involved, read them through `screenshot-reading.md` before proposing changes.

### 5A. Agent Must Return A Structured UI Reading

Before proposing a change, the agent should describe the task using this structure:

```text
Current surface:
Target module:
Main issues:
Suggested adjustments:
Reference direction:
Reference reading:
Current mismatch:
Need your decision on:
```

Minimum required fields:

- `Current surface`
- `Target module`
- `Main issues`
- `Suggested adjustments`

Use `Reference direction` when relevant:

- pattern family
- shell family
- card/list direction
- cool-white or warm-off-white direction
- centered-composer or utility-first direction

If a screenshot is involved, the agent must include `Reference reading` when a reference screenshot exists.
If both the current app screenshot and a reference screenshot exist, the agent must include `Current mismatch`.

Do not skip directly from screenshots to implementation.
After returning the structured reading, stop and wait for user confirmation.

### 5B. Agent Must Confirm The Following When Relevant

The agent should explicitly confirm:

- `where` the change applies
- `what` module is being changed
- `why` the current UI is weak or inconsistent
- `how` the UI should improve
- `whether` the user wants the change to stay close to an existing pattern
- `whether` the user wants a cooler or warmer visual base when color direction matters
- `whether` the user prefers denser scanning or more open spacing when density matters
- `whether` the current problem is mainly structure, hierarchy, surface treatment, or density when screenshots are involved

### 5C. Decision Questions Should Stay Focused

The agent should ask only the decisions that matter for the current change.

Good examples:

- keep this card-first, or move closer to a list-first layout?
- keep the centered composer dominant, or raise utility controls?
- stay with a cool-white base, or shift toward a warmer off-white base?
- keep current density, or open the spacing up?
- align to the existing pattern, or intentionally introduce a new local variation?
- this looks heavier than the reference mainly because of card framing and loose spacing; do you want me to keep the skeleton and just tighten those two?

Bad examples:

- vague questions like "what do you prefer?"
- broad aesthetic questions without naming the surface or module
- asking for color choices when color is not the real issue

### 5D. Do Not Implement Until The Direction Is Clear

If the user has not confirmed the direction, the agent should:

- refine the UI reading
- narrow the design options
- ask for the missing decision

Do not implement while the core direction is still ambiguous.
For screenshot-driven UI tasks, "direction is clear" means the user has confirmed one of the proposed adjustment paths or has explicitly described the desired path using the provided terms.
General approval like `make it better` is not enough.

### 5E. Required Screenshot Confirmation Pattern

When screenshots are involved, use this sequence:

1. identify the target surface and module
2. read the reference screenshot using `screenshot-reading.md`
3. compare the current UI against the reference screenshot
4. name the likely cause of the mismatch
5. propose conservative, medium, and strong adjustment paths when appropriate
6. ask 1-3 focused decision questions
7. wait for the user's answer

The agent should prefer the smallest confirmed adjustment.
Do not start implementation until step 7 is complete.

## 6. Write A Design Direction

For small UI changes, write one sentence:

```text
Design direction: [what changes], while preserving [existing structure or hierarchy].
```

For module changes or new modules, define:

- layout structure
- module role
- primary and secondary actions
- empty, loading, error, and selected states
- how the change stays consistent with the current product language

If no existing pattern applies, do not silently invent one. State the proposed direction first.

The design direction should reflect the confirmed UI reading from the previous step.

## 7. Implement Conservatively

Implementation rules:

- reuse existing components first
- reuse tokens and nearby layout grammar first
- keep changes scoped to the target surface
- preserve app shell stability
- avoid one-off styling when a reusable pattern should exist

A UI change should feel like an extension of the current system, not a local redesign.

## 8. Review Against Product Rules

Before finishing, check the change against:

- `design.md`
- `component-rules.md`
- `implementation-rules.md`

Reject the change if it:

- introduces a new local style language
- breaks shell or hierarchy consistency
- makes the surface feel more like a webpage or template dashboard than a desktop product

## 9. Verify Real States

Minimum verification:

- main state
- empty state
- loading state
- error state
- selected or active state where applicable
- long Chinese and English text
- common desktop window sizes
- dark or light theme expectations for the surface
- final UI review across skeleton, hierarchy, surface treatment, density, control language, and product consistency

Passing TypeScript or build checks does not prove UI completion.

Do not rely on code review alone to claim visual quality.
The preferred visual verification loop is user-screenshot driven:

1. the agent implements the confirmed change
2. the user opens the app and provides an updated screenshot when visual quality matters
3. the agent compares the updated screenshot against the confirmed direction and any reference screenshot
4. the agent proposes the next smallest adjustment if the result still misses the target

The agent should not require itself to launch Playwright for normal UI review.
If no updated screenshot or user visual confirmation is available, mark visual verification as pending user review.

### 9A. Final UI Review Template

When finishing a UI change, summarize the result with this structure:

```text
UI review:
- Skeleton:
- Hierarchy:
- Surface treatment:
- Density:
- Control language:
- Product consistency:
- Visual verification:
```

The review should be concrete.
Do not write generic claims such as `looks cleaner` or `more modern`.
Name what changed and what product language was preserved.
For `Visual verification`, use one of:

- `confirmed by updated user screenshot`
- `pending user screenshot review`
- `pending user visual confirmation`

## 10. Definition Of Done

A UI task is done only when:

- the feature works
- the target surface still feels like the same product
- no unnecessary new pattern was introduced
- code reuse and structure remain reasonable
- key states were checked
- the user-facing direction was clear before implementation

If the UI works but looks inconsistent with the product language, it is not done.
