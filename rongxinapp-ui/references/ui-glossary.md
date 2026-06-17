# UI Glossary

This glossary turns the current reference screenshots into a shared design language for humans and coding agents.

Goal:

- help humans describe UI changes without relying only on screenshots
- help agents map requests to stable module and layout terms
- reduce vague language like "make it cleaner" or "more advanced"

Use this glossary with:

1. `DESIGN.md`
2. `workflow.md`
3. `component-rules.md`

## How To Use

When discussing a UI task, try to describe it with:

1. `surface type`
2. `structure terms`
3. `visual traits`
4. `interaction traits`
5. `do / avoid guidance`

Example:

```text
This should stay a project workspace surface inside the existing app shell.
Keep the persistent left navigation and broad primary workspace.
Use lightweight module cards, low-contrast borders, and a quiet utility row.
Avoid turning it into a promotional dashboard or a heavy card grid.
```

## 1. Product-Level Terms

- `桌面 AI 工作台（desktop AI workbench）`
  - A desktop-first AI product with stable navigation, persistent tools, and task-oriented work areas.

- `代理协作工作区（agent-assisted workspace）`
  - A workspace where the user coordinates tasks, tools, knowledge, or automation with AI assistance.

- `本地推理工作台（local inference workbench）`
  - A workbench-style app that includes local model execution, runtime controls, and model management surfaces.

- `工具型产品界面（tool-like product surface）`
  - A product surface focused on getting work done rather than telling a story or promoting a feature.

## 2. Surface Vocabulary

These terms answer: `这是什么页面 / 模块？`

### Core Shell Surfaces

- `应用外壳（app shell）`
  - The persistent outer product frame: left navigation, global actions, main content container, overlays.
  - Seen strongly in both Codex and WorkBuddy.

- `左侧导航区（left navigation）`
  - The persistent left-side area for switching core product sections.

- `主工作区（primary workspace）`
  - The visually dominant area where the current task happens.

- `上下文面板（context panel）`
  - A secondary region for related information, settings, status, or detail without replacing the main task area.

- `详情面板（detail panel）`
  - A focused detail surface for a selected object, task, or item.

### Home And Task Surfaces

- `助手首页（assistant home surface）`
  - A home workspace centered around the main AI interaction entry point.
  - WorkBuddy home is a clear example.

- `项目工作区（project workspace）`
  - A workspace surface for project-level actions, lists, templates, and summaries.

- `项目列表页（project list surface）`
  - A page for scanning available projects with lightweight metadata and actions.

- `自动化页面（automation surface）`
  - A surface for listing, configuring, or launching automations, templates, and recurring tasks.

- `专家目录页（expert directory surface）`
  - A discovery page for agents, experts, roles, or skill-based profiles presented as scannable content modules.

- `模板库页面（template gallery surface）`
  - A page presenting reusable task templates, usually in card or module form.

### Utility Surfaces

- `设置界面（settings surface）`
  - A structured configuration surface with grouped preferences and low-noise form patterns.

- `插件 / 技能目录（plugin or skill directory surface）`
  - A searchable listing surface for extensions, tools, or skills.
  - Codex plugin and skill screens are clear references.

- `账户菜单（account menu）`
  - A small personal menu for account, usage, settings, logout, and related actions.

- `筛选浮层（filter popover）`
  - A compact overlay used for status, date, or category filtering without leaving the current page.

- `操作菜单（action menu / dropdown menu）`
  - A scoped overlay listing a small set of contextual actions.

### Local Inference Surfaces

- `模型管理页（model management surface）`
  - A surface for browsing, selecting, enabling, or removing models.

- `本地推理控制面板（local inference control panel）`
  - A settings or workspace panel for inference mode, runtime, temperature, context length, and execution options.

- `运行时状态面板（runtime status panel）`
  - A small status module showing runtime state, availability, memory, or execution readiness.

- `推理参数区（inference parameter panel）`
  - A grouped control area for inference parameters and execution behavior.

- `执行日志区（execution log surface）`
  - A scannable log surface for model events, task execution, or runtime diagnostics.

## 3. Structure Vocabulary

These terms answer: `这个页面怎么搭起来的？`

### Shell And Layout

- `稳定应用骨架（stable app shell structure）`
  - A repeated product frame that should not change between pages.

- `左导航 + 主内容布局（left-navigation plus main-workspace layout）`
  - A dominant layout pattern for many desktop AI workbench products.

- `宽主画布（broad primary canvas）`
  - A wide, open main content area with clear task priority.

- `面板式布局（panel-based layout）`
  - A layout built from clear surfaces and grouped panels rather than free-floating content.

- `工作区优先布局（workspace-first layout）`
  - A layout where the core task area is more visually important than supporting chrome.

- `标题 + 操作区页头（title-and-actions header）`
  - A page header composed of title, short supporting copy, and one or two clear actions.

- `搜索与筛选工具行（search-and-filter utility row）`
  - A compact row containing search, filter, sorting, or view controls.

### Content Structures

- `轻量卡片栅格（lightweight card grid）`
  - A grid of visually restrained content cards, not a marketing bento grid.

- `模块卡片区（module card section）`
  - A grouped area containing reusable content modules, templates, or expert cards.

- `列表优先布局（list-first layout）`
  - A structure optimized for scanning repeated items quickly.

- `单列详情流（single-column detail flow）`
  - A detail page with strong vertical reading order rather than many competing panels.

- `分组内容区（grouped content regions）`
  - Separate content sections with clear spacing and headings, without reinventing the page shell.

### Overlay Structures

- `局部浮层（scoped overlay）`
  - An overlay attached to a specific local task, such as filtering or choosing a source.

- `轻量下拉菜单（lightweight dropdown menu）`
  - A compact vertical menu with quiet separators, mild radius, and simple icon-text rows.

- `分段筛选菜单（sectioned filter popover）`
  - A popover with grouped filter categories such as state and time range.

## 4. Visual Vocabulary

These terms answer: `它看起来像什么？`

### High-Level Product Style

- `桌面工作台气质（desktop workbench feel）`
  - Calm, stable, utility-first, non-promotional.

- `低干扰界面（low-noise interface）`
  - An interface that avoids decorative visual clutter and keeps task focus high.

- `非营销化表面（non-promotional product surface）`
  - A product surface that does not look like a landing page or campaign page.

- `克制的产品界面（restrained product UI）`
  - A UI with controlled styling, no unnecessary flourish, and clear task hierarchy.

### Surface And Framing

- `低对比表面分层（low-contrast surface layering）`
  - Hierarchy created with subtle surface shifts rather than strong color blocks.

- `克制的面板包裹（restrained panel framing）`
  - Panels and cards are present but quiet, with subtle edges and controlled emphasis.

- `轻边框层级（muted border hierarchy）`
  - Borders help structure content without becoming decorative.

- `轻量模块卡片（lightweight module cards）`
  - Cards with soft radius, light border, low visual weight, and clear scanning purpose.

- `柔和圆角（soft radius treatment）`
  - Rounded corners that feel polished but not playful or bubbly.

- `开阔内容画布（spacious content canvas）`
  - Broad content areas with enough whitespace to separate functionally distinct modules.

### Density And Rhythm

- `紧凑控件密度（compact control density）`
  - Controls are space-efficient and productivity-oriented.

- `舒适扫描节奏（comfortable scanning rhythm）`
  - Repeated items are easy to scan due to steady spacing, predictable metadata placement, and low-noise structure.

- `安静的导航样式（quiet navigation styling）`
  - The navigation is visually present but does not compete with the main task area.

- `轻量内容呈现（lightweight content presentation）`
  - Information modules feel product-like and useful, not decorative and over-framed.

## 5. Interaction Vocabulary

These terms answer: `它是怎么被使用的？`

- `持久导航（persistent navigation）`
  - Main product navigation remains stable across surfaces.

- `单一主操作流（single-primary-action flow）`
  - Each major surface has one obvious next action instead of many equally loud options.

- `渐进式信息展开（progressive disclosure）`
  - Secondary information or filters appear only when needed rather than all at once.

- `局部次要操作（inline secondary actions）`
  - Secondary actions remain close to the related content without disrupting the main layout.

- `稳定操作位置（stable action placement）`
  - Similar actions appear in predictable places across different pages.

- `搜索优先发现（search-first discovery）`
  - Search is a first-class discovery mechanism for large sets of items.

- `筛选浮层交互（filter-popover interaction）`
  - Filtering happens in a compact overlay rather than a full page settings experience.

- `选择驱动详情（selection-driven detail flow）`
  - Selecting an item reveals or changes details elsewhere, without rebuilding the entire page.

- `工作区中心交互（workspace-centric interaction）`
  - The user spends most time in the main task area; all other surfaces support that core flow.

### Local Inference Interaction Terms

- `参数驱动执行（parameter-driven execution）`
  - The user adjusts execution behavior through grouped controls before or during model use.

- `运行时感知控制（runtime-aware controls）`
  - Controls reflect whether a runtime or model is available, busy, or missing.

- `本地模型选择流程（local model selection flow）`
  - A user flow for choosing the active local model before execution.

- `资源敏感交互（resource-sensitive interaction）`
  - The UI makes compute or memory state visible enough to guide behavior.

## 6. Reference-Derived Pattern Notes

This section captures reusable pattern families derived from the current references without binding the glossary to any single product.

### Shell And Navigation Family

Primary traits:

- stable app shell
- quiet left navigation
- clear main workspace priority
- restrained settings and utility surfaces

Useful for describing:

- desktop AI workbench shells
- settings framing
- scoped menus and overlays

### Centered Home Workspace Family

Primary traits:

- centered task-entry surface
- broad open workspace
- dominant composer
- lightweight supporting actions

Useful for describing:

- assistant home surfaces
- task-entry pages
- broad light-theme workspaces

### Capability Catalog Family

Primary traits:

- searchable directory layout
- connector or plugin sections
- lightweight install/add actions
- scan-first information density

Useful for describing:

- plugin directories
- connector catalogs
- skill discovery pages

### Project And Library Family

Primary traits:

- recent rows or recent carousels
- card-first or mixed card/list browsing
- search and filter utility rows
- broad content canvas with calm grouping

Useful for describing:

- project dashboards
- library surfaces
- document browsing pages

### Automation Onboarding Family

Primary traits:

- explanatory hero block
- simple automation entry rows
- one strong creation action
- low-noise instructional layout

Useful for describing:

- scheduled task surfaces
- workflow setup pages
- recurring automation entry points

### Neutral Color Families

#### Cool White Family

- `主背景（primary canvas）`
  - around `#ffffff`

- `次级表面（secondary surface）`
  - around `#f7f7f7`

- `文本主色（primary text tone）`
  - around `#000000` to `#080808`

- `边界与分割（divider and border tone）`
  - around `#d2d2d2` to `#d4d4d4`

Color reading:

- cooler, cleaner, and more whitespace-driven
- better for calm, open, low-drama workspaces

#### Warm Off-White Family

- `主背景（primary canvas）`
  - around `#f8f8f7`

- `次级表面（secondary surface）`
  - around `#ebebeb`

- `高亮白卡片（highlight card white）`
  - around `#ffffff`

- `文本主色（primary text tone）`
  - around `#000000` to `#0d0d0d`

- `边界与分割（divider and border tone）`
  - around `#d8d8d7` to `#dddddc`

Color reading:

- slightly warmer, softer, and more operational
- better for utility-heavy pages and capability surfaces

## 7. Do / Avoid Language

These phrases are suitable for real human-agent discussion.

### Useful "Do" Phrases

- 保持现有应用外壳（Preserve the existing app shell）
- 保持左侧导航稳定（Keep the left navigation stable）
- 让主工作区继续占主导（Keep the primary workspace visually dominant）
- 使用轻量模块卡片（Use lightweight module cards）
- 保持中心输入入口清晰（Keep the centered composer clearly dominant）
- 保持低对比表面分层（Keep low-contrast surface layering）
- 使用搜索与筛选工具行（Use a search-and-filter utility row）
- 使用连接器目录模式组织外部能力（Use connector-catalog patterns for external capabilities）
- 把次要操作做成局部浮层（Move secondary actions into a scoped overlay）
- 保持紧凑控件密度（Maintain compact control density）
- 用分组内容区组织页面（Organize the page into grouped content regions）

### Useful "Avoid" Phrases

- 不要把这个页面做成营销页（Do not turn this into a marketing-style page）
- 不要重新发明导航结构（Do not reinvent the navigation model）
- 不要把列表改成重卡片网格（Do not turn this list into a heavy card grid）
- 不要让 action chips 抢输入区焦点（Do not let action chips compete with the main composer）
- 不要为了现代感加入夸张装饰（Do not add exaggerated decoration just to feel modern）
- 不要让次级信息抢主任务焦点（Do not let secondary content compete with the primary task）
- 不要引入新的局部设计系统（Do not introduce a new local design system）

## 8. Human-Agent Prompt Fragments

These are ready-to-use phrases for future UI conversations.

### Shell And Workspace

- 这个页面应该保持在现有 `应用外壳（app shell）` 内，不要改导航范式。
- 把内容放在 `主工作区（primary workspace）`，不要让辅助信息抢焦点。
- 继续使用 `左导航 + 主工作区布局（left-navigation plus main-workspace layout）`。

### Lists, Cards, And Modules

- 这里更适合做成 `轻量模块卡片（lightweight module cards）`，不是营销式大卡片。
- 这个 surface 应该保持 `舒适扫描节奏（comfortable scanning rhythm）`。
- 用 `分组内容区（grouped content regions）` 组织，不要堆砌容器。
- 这里更像 `连接器目录页（connector catalog surface）`，应该优先强调搜索、扫描和加装动作。
- 这里更像 `技能发现页（skill discovery surface）`，卡片可以轻一点，但不要失去分类和精选层级。

### Utility And Overlays

- 把筛选做成 `筛选浮层（filter popover）`，不要单独开整页设置。
- 次要操作放在 `局部浮层（scoped overlay）` 或行内次要操作里。
- 保持 `稳定操作位置（stable action placement）`。
- 如果这是 `定时任务页（scheduled task surface）`，优先用解释型入口行，不要直接堆很多复杂表单。
- 如果这是 `资料库页（library surface）`，优先保留 `搜索与筛选工具行（search-and-filter utility row）` 和视图切换。

### Local Inference Extensions

- 这里可以新增一个 `本地推理控制面板（local inference control panel）`，但仍然要留在同一套 app shell 里。
- 模型选择应当是 `本地模型选择流程（local model selection flow）`，不要单独发明一套新布局。
- 状态展示更适合 `运行时状态面板（runtime status panel）`，而不是大面积装饰模块。

## 9. Recommended Core Terms

If you only remember a smaller set, start with these:

- 应用外壳（app shell）
- 左侧导航（left navigation）
- 主工作区（primary workspace）
- 设置界面（settings surface）
- 项目工作区（project workspace）
- 助手首页（assistant home surface）
- 技能发现页（skill discovery surface）
- 插件目录页（plugin directory surface）
- 连接器目录页（connector catalog surface）
- 定时任务页（scheduled task surface）
- 资料库页（library surface）
- 专家目录页（expert directory surface）
- 自动化页面（automation surface）
- 轻量模块卡片（lightweight module cards）
- 中心输入入口（centered composer）
- 快捷动作胶囊（action chips）
- 低对比表面分层（low-contrast surface layering）
- 克制的面板包裹（restrained panel framing）
- 紧凑控件密度（compact control density）
- 渐进式信息展开（progressive disclosure）
- 局部浮层（scoped overlay）
- 稳定操作位置（stable action placement）
- 本地推理控制面板（local inference control panel）
