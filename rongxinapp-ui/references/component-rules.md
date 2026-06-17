# Component Rules

Use these rules when designing or modifying recurring app modules.

Each section defines what the module is for, what must stay stable, and what should not be reinvented locally.

## App Shell

Role:

- provide the persistent desktop frame for the entire product

Must:

- preserve stable left navigation plus main workspace structure
- keep the workspace visually dominant
- keep shell actions in predictable locations
- keep shell styling quiet and reusable across pages

Must not:

- redesign the shell for one feature
- make the shell feel like a webpage
- introduce decorative banners or promotional sections into the shell

## Sidebar And Navigation

Role:

- help users switch between persistent product areas

Must:

- keep navigation stable and predictable
- use compact rows with consistent icon size and label rhythm
- keep grouping clear
- preserve selected state visibility without heavy visual noise

Must not:

- turn navigation into a card layout
- move global navigation controls to solve a local page problem
- use highly decorative icons or badges without functional reason

## Main Workspace

Role:

- host the current task and its primary content

Must:

- prioritize the current task over surrounding chrome
- keep one clear primary workflow
- use whitespace to separate functional regions
- keep supporting content quieter than the main task

Must not:

- fill empty space with decorative filler
- split one task into too many equally-weighted panels
- mix unrelated workflows without clear structural separation

## Input Areas

Role:

- support writing, command input, configuration input, or submission

Must:

- group related controls by intent
- keep the main submit or confirm action obvious
- support both keyboard and pointer use
- keep helper text short and state-specific

Must not:

- scatter input-related controls across multiple unrelated zones
- add unnecessary labels where pattern and placement already explain the control
- resize unpredictably during ordinary typing

## Lists And Tables

Role:

- present repeatable, scannable objects efficiently

Must:

- keep row height and spacing consistent
- use clear selected, hover, disabled, empty, and loading states
- keep metadata visually secondary
- support truncation without destroying scan rhythm

Must not:

- convert dense lists into large cards without a clear content reason
- mix multiple border grammars in one list
- rely on color alone for state

## Cards And Content Modules

Role:

- group related information, templates, experts, projects, or summaries

Must:

- use light borders and restrained framing
- keep card spacing and radius consistent
- use cards only when grouping improves comprehension
- prefer lightweight module presentation similar to the WorkBuddy references

Must not:

- make every page section a card by default
- stack heavy shadows and thick containers
- nest cards inside cards without a strong structural reason

## Detail Views

Role:

- show one record, object, or module in more depth

Must:

- establish clear order between title, metadata, main content, and actions
- keep the content easy to scan
- preserve strong alignment and spacing rhythm

Must not:

- scatter actions throughout the page
- mix unrelated controls into the main reading flow
- over-decorate the detail surface

## Dialogs, Menus, And Popovers

Role:

- handle one scoped interaction or secondary task

Must:

- keep overlays focused
- use clear titles when needed
- preserve close, cancel, and destructive semantics
- match existing border, radius, spacing, and menu rhythm

Must not:

- hold unrelated workflows in one overlay
- become a substitute for a full page when the task is large
- contain long explanatory prose that belongs in docs

## Settings And Forms

Role:

- let users configure product behavior predictably

Must:

- group settings by intent
- use appropriate control types
- keep forms scannable and compact
- keep advanced controls visually secondary

Must not:

- turn settings into a promotional surface
- use oversized cards where grouped form rows are enough
- mix destructive actions into ordinary controls without separation

## Status Feedback

Role:

- communicate loading, empty, success, warning, failure, and progress states

Must:

- keep status messaging short and direct
- preserve the surrounding module structure during loading and empty states
- use consistent semantic treatment across pages

Must not:

- invent a different empty-state style for every module
- replace useful status text with decorative illustration alone
- make error states visually louder than necessary
