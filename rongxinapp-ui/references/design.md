# UI Design Contract

This document is the source-of-truth design contract for app UI work in this repo.

Its purpose is not to inspire free-form design. Its purpose is to constrain UI changes so developers and coding agents keep the product visually and structurally consistent over time.

Use this document together with:

1. `workflow.md`
2. `component-rules.md`
3. `ts-react-rules.md`

## Purpose

This workflow exists to prevent:

- different agents from producing different product styles
- new modules from inventing new layout paradigms
- UI changes from drifting into generic dashboard or marketing-page patterns
- implementation shortcuts from damaging long-term design consistency

If a change improves functionality but noticeably breaks the product's visual language, it is not complete.

## Reference Style

The current v1 reference set combines two sources:

1. `Primary reference: Codex desktop app screenshots`
2. `Secondary reference: WorkBuddy light-theme screenshots`

These references define the product language at a structural level. They are not a requirement to copy exact colors pixel-for-pixel.

What is fixed:

- desktop workbench structure
- stable left navigation plus main workspace layout
- restrained panel styling
- calm information hierarchy
- compact but readable control density
- low-contrast surfaces and light borders
- consistent menu, popover, settings, and list behavior

What is flexible:

- exact color palette
- dark or light theme choice for a specific surface
- product-specific icons, illustrations, and copy

## Product Character

The UI should feel:

- calm
- structured
- tool-like
- desktop-first
- reliable
- low-drama
- precise

The UI should not feel:

- promotional
- playful for its own sake
- heavily decorative
- trend-driven
- card-heavy by default
- visually loud

## Product Language

The current v1 visual language should favor:

- stable navigation
- broad primary work areas
- restrained module framing
- compact but comfortable controls
- lightweight cards, menus, and popovers

This is a productivity-oriented UI, not a sparse brand page and not a generic dashboard template.

## Layout Language

The product should preserve a stable app shell:

- left navigation is persistent and predictable
- the main workspace is visually dominant
- secondary panels support the task rather than compete with it
- dialogs, popovers, and menus stay scoped and task-specific

Changes should preserve the existing relationship between:

- navigation
- workspace
- contextual controls
- overlays

Do not introduce a new layout grammar for one page unless it is first approved as a new reusable pattern.

## Surface Language

Surfaces should be:

- lightly separated
- rounded but not soft or playful
- bordered subtly rather than heavily shadowed
- consistent in spacing and internal rhythm

The preferred visual tools for hierarchy are:

- spacing
- typography
- alignment
- quiet borders
- surface elevation only where necessary

Do not rely on:

- loud gradients
- large saturated fills
- oversized shadows
- decorative illustrations used only to fill space

Use hierarchy through:

- spacing
- alignment
- type scale
- muted borders
- subtle surface shifts

## Typography And Density

Typography should support scanning and work sessions.

Do:

- keep headings compact and useful
- keep labels short
- use muted text for secondary metadata
- keep information density high enough for tool usage

Do not:

- use hero-style marketing headings in tool surfaces
- create large empty blocks with too little useful information
- make utility controls feel oversized
- turn explanations into long blocks of UI copy

## Color Strategy

Color is not the primary identity anchor for this system.

Use color to support:

- action priority
- selected state
- semantic status
- subtle product tone

Do not use color to compensate for weak structure.

Changing a palette is acceptable. Changing the structural language is not.

## Motion

Motion should clarify state, not perform personality.

Allowed by default:

- subtle hover feedback
- open or close transitions
- loading and progress communication
- scoped expand or collapse transitions

Disallowed by default:

- looping decorative animation
- moving backgrounds
- exaggerated entrance choreography

## Using Screenshot References

When screenshots are provided, use them to extract constraints rather than copy them blindly.

Extract:

- app type
- layout structure
- density
- surface model
- text hierarchy
- interaction model
- theme behavior

Do not extract:

- product-specific branding that does not belong to this app
- unrelated copy
- platform-specific window chrome unless the task explicitly needs it

When adapting a screenshot, define a short direction in this form:

```text
Use the reference for [layout / density / surface / control behavior], adapted to the existing app structure. Preserve [existing hierarchy / data flow / module pattern]. Avoid [non-matching patterns].
```

The goal is to make the result feel like the same product, not an imported screenshot.

## Hard Prohibitions

The following patterns are not allowed unless explicitly approved:

- marketing-page hero layouts inside the app
- decorative dashboard card grids used as filler
- introducing a new navigation model for one feature
- turning dense lists into large promo-style cards without functional need
- adding glow, glassmorphism, neon, or ornamental gradients as default style
- creating one-off control styles that do not match nearby surfaces
- adding extra visual complexity just to make a page feel "modern"

## Agent Usage Contract

Any agent working on UI must:

1. read this document before editing UI
2. identify the target surface in `component-rules.md`
3. follow `workflow.md` before implementing
4. obey `ts-react-rules.md` for code structure and reuse

If an agent cannot find a matching pattern, it must propose a short design direction before implementation instead of inventing a new UI style silently.

## Acceptance Standard

A UI change is acceptable when:

- it still feels like the same product
- it preserves the main task hierarchy
- it reuses existing surface language
- it does not introduce a new local design system
- it remains coherent in main, empty, loading, error, and selected states
