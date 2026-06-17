# TypeScript And React UI Rules

These rules define implementation constraints for UI code.

They exist to prevent visual inconsistency from becoming code inconsistency.

## Project Boundaries

Do:

- keep UI work in the renderer-facing UI layer
- communicate with other layers through existing services and wrappers
- reuse existing selectors, stores, hooks, and service boundaries
- follow established import and file-organization patterns

Do not:

- reach directly into unrelated process layers from visual components
- duplicate service access logic inside presentation components
- move business logic into UI code just to finish a screen quickly

## Component Design

Do:

- keep components focused on one module or reusable primitive
- split large surfaces into clear subcomponents
- keep top-level views as composition layers
- make repeated patterns reusable instead of re-copying markup
- use explicit TypeScript props for reusable UI

Do not:

- write one monolithic page component for a complex surface
- define hidden local subcomponents inside render bodies when module-level components are clearer
- create new global state for purely local visual state

## Reuse First

Before creating new UI code, check whether the repo already has:

- a similar layout pattern
- a similar row or card pattern
- an existing dialog or menu primitive
- a token or variable for the needed surface treatment

If an existing pattern is close enough, reuse or extend it.

Do not create a new visual pattern just because it is faster locally.

## Styling

Do:

- use existing tokens, CSS variables, and nearby spacing grammar
- keep radius, border, surface color, and typography aligned with neighboring surfaces
- prefer consistent utility usage over ad hoc local style inventions
- preserve desktop resizing behavior
- when the project uses a semantic color system, map UI roles to semantic tokens instead of raw hex values

Do not:

- introduce raw visual values when semantic tokens already exist
- add unrelated global CSS for one surface
- create one-off styles for a component that should match a reusable system pattern
- use oversized marketing-style typography in tool surfaces

## Semantic Color Usage

If the project uses HeroUI-style semantic colors or an equivalent token system, prefer role-based color usage:

- `background` for the base canvas
- `surface` for cards, panels, and modals
- `foreground` for primary text and icons
- `accent` for primary actions and emphasis
- `success` for confirmations and completed states
- `warning` for cautionary states
- `danger` for destructive actions and critical errors
- `field` for inputs and interactive form controls
- `separator` for subtle dividers and outlines

Rules:

- use accent colors sparingly
- keep neutral surfaces dominant
- let semantic tokens drive contrast and hierarchy
- do not hard-code component colors when the token system already provides the role
- keep light and dark theme behavior consistent through the same semantic roles

Prefer code like:

```tsx
<div className="bg-background text-foreground">
  <button className="bg-accent text-accent-foreground">Save</button>
</div>
```

## State And Stability

Do:

- keep transient state local when possible
- derive cheap values during render
- preserve stable layout during loading, selection, and data refresh
- ensure empty, loading, error, and selected states are explicitly designed

Do not:

- add effects for values that can be derived directly
- allow loading text or async state to cause avoidable layout shifts
- scatter state logic across multiple sibling components without reason

## Interaction And Accessibility

Do:

- use semantic interactive elements
- provide names for icon-only actions
- preserve expected keyboard behavior
- keep focus visible
- make state and errors understandable without relying only on color

Do not:

- use clickable containers where buttons or links should exist
- remove focus treatment without replacement
- hide important control meaning behind decoration alone

## Verification

Before finishing UI implementation, check:

- TypeScript still compiles
- the changed module renders in context
- primary controls update real UI state
- long localized text does not overflow
- empty, loading, error, and selected states remain coherent
- the code still follows the same UI system rather than introducing a new local one

For visual quality, prefer user-screenshot review over agent-run browser automation.
Do not require Playwright as the default UI review mechanism.
If the user provides an updated screenshot, compare it against the confirmed design direction and reference screenshot before proposing more changes.
If no updated screenshot is available, state that visual verification is pending user review.
