# UI Communication Glossary

This document is a human-agent communication layer for UI work.

It exists to help:

- users describe UI changes without relying only on screenshots
- agents map requests to stable page, module, and detail terms
- both sides discuss problems and tradeoffs using the same vocabulary

Use this file with:

1. `DESIGN.md`
2. `workflow.md`
3. `component-rules.md`
4. `ui-glossary.md`

## How To Use

Describe UI feedback with this order:

1. `surface`
2. `module`
3. `issue`
4. `adjustment`
5. `decision`

Example:

```text
Keep this inside the existing library surface.
The search and filter row is fine, but the document cards feel too heavy.
The main issues are card emphasis too strong and scanning rhythm too loose.
Please soften the card framing, tighten vertical spacing, and reduce secondary action prominence.
If needed, ask me whether I want this area to stay card-first or shift closer to a list-first layout.
```

When the user gives vague visual feedback, do not repeat the vague wording back.
Translate it into one or two likely UI issues, then confirm the translation.

Example:

```text
User: 这个页面还是不太对，不像参考图。

Agent:
我先不把它理解成颜色问题。
更像是这三个方面还没有对齐：
1. 卡片感偏重
2. 信息密度偏松
3. 主视觉重心不够集中
如果你同意，我就按这三个方向继续收紧，而不是重做整个页面。
```

Use `screenshot-reading.md` whenever screenshots or reference products are part of the discussion.

## Visual Contrast Axes

These axes are more useful than generic style words.
Prefer using them during UI discussion.

- `卡片感偏重 / 卡片感偏轻`
- `边框存在感强 / 弱`
- `留白偏松 / 偏紧`
- `信息密度高 / 低`
- `层级清晰 / 发散`
- `主操作突出 / 收敛`
- `输入区主导 / 内容区主导`
- `内容居中 / 内容铺开`
- `界面偏工作台 / 偏仪表盘`
- `界面偏工具化 / 偏展示化`
- `表面偏平 / 偏分层`
- `控件圆角偏强 / 偏克制`
- `模块更聚焦 / 更分散`
- `视觉更安静 / 更喧闹`

## Module-Level Terms

Use these terms when discussing app-like AI workspaces, chatbot surfaces, local task tools, and reference screenshots.

- `输入组合器（composer）`
  - The main prompt or task input area.

- `输入工具栏（input toolbar）`
  - The row of controls inside or near the composer.

- `模式切换器（mode switcher）`
  - A segmented control for changing work modes.

- `快捷动作胶囊（action chips）`
  - Compact prompt or capability shortcuts around the composer.

- `权限选择器（permission selector）`
  - A control that changes tool, file, or workspace permissions.

- `连接器选择器（connector selector）`
  - A control for selecting connected services or integrations.

- `技能选择器（skill selector）`
  - A control for selecting reusable skills, capabilities, or agents.

- `侧栏推广卡片（sidebar promo card）`
  - A promotional or status card placed inside the sidebar.

- `工作区头部（workspace header）`
  - The top area of the main workspace.

- `空态主视觉（empty-state focal）`
  - The central visual, title, or prompt shown before real content exists.

- `状态徽标（status badge）`
  - A small status indicator for plan, progress, permission, or connection state.

## Difference-Level Terms

Use these terms to describe why the current UI does not match the target direction.

- `主视觉弱（weak visual center）`
  - The page lacks a clear first focal point.

- `模块抢焦点（module competes for attention）`
  - A secondary module looks as important as the primary task area.

- `卡片过重（card weight too heavy）`
  - Card borders, fills, shadows, or spacing make the module feel too loud.

- `边框过强（border presence too strong）`
  - Borders are more visible than the hierarchy requires.

- `扫描节奏松（scan rhythm too loose）`
  - Spacing is too open for efficient work scanning.

- `控件语言不统一（control language inconsistent）`
  - Buttons, inputs, selectors, or chips do not feel from the same system.

- `局部网页感（local web-page feel）`
  - One area feels like a marketing or dashboard webpage instead of the app.

- `结构正确但表面不对（correct skeleton, wrong surface treatment）`
  - The layout is acceptable, but cards, borders, fills, or controls need adjustment.

## Decision-Level Terms

Use these terms to narrow implementation choices.

- `保持骨架只调样式（keep skeleton, adjust styling only）`
- `轻量重排（light rebalance）`
- `局部重做（local rebuild）`
- `向参考图靠近一档（move one step closer to reference）`
- `只迁移控件语言（adopt control language only）`
- `只收紧密度（tighten density only）`
- `减轻卡片重量（reduce card weight）`
- `降低次级操作存在感（lower secondary action prominence）`
- `提高主视觉权重（raise primary visual weight）`

## Translate User Phrases

Use these patterns to keep discussion concrete.

- `更干净`
  - likely means: less border weight, fewer competing accents, tighter hierarchy

- `更高级`
  - likely means: more restrained control language, less template feel, stronger spacing discipline

- `更像参考图`
  - likely means: closer skeleton, closer card/list weight, closer density, closer visual center

- `太乱了`
  - likely means: hierarchy scattered, utility controls competing with content, spacing rhythm inconsistent

- `太重了`
  - likely means: cards too filled, borders too dark, shadows or tinted surfaces too obvious

- `太空了`
  - likely means: density too low, modules too separated, not enough scan rhythm

- `太挤了`
  - likely means: controls too close, hierarchy compressed, insufficient whitespace between functional groups

Agent response pattern:

```text
我先把这句话翻译成更具体的 UI 问题：
- [issue 1]
- [issue 2]

如果这个翻译对，我会优先改 [module]，并保持 [existing pattern] 不变。
```

## 1. Surface Vocabulary

These terms answer: `这是哪个页面类型？`

- `应用外壳（app shell）`
  - The stable outer frame of the product.

- `助手首页（assistant home surface）`
  - A home surface centered on task entry, prompting, or AI initiation.

- `项目页（project dashboard surface）`
  - A page for scanning projects, recent items, or project-level content modules.

- `项目工作区（project workspace surface）`
  - A task area where one project or board is actively being used.

- `技能发现页（skill discovery surface）`
  - A surface for browsing reusable skills, experts, or capabilities.

- `插件目录页（plugin directory surface）`
  - A surface for browsing extensions, connectors, or integrations.

- `连接器目录页（connector catalog surface）`
  - A listing surface focused on external tools, APIs, or connected services.

- `定时任务页（scheduled task surface）`
  - A setup or management surface for recurring automation.

- `资料库页（library surface）`
  - A page for browsing files, documents, and generated assets.

- `设置页（settings surface）`
  - A structured configuration surface with grouped preferences.

- `详情页（detail surface）`
  - A focused view for one selected item, record, or object.

- `搜索结果页（search results surface）`
  - A surface optimized for scanning matched items.

- `空态入口页（empty-state entry surface）`
  - A page where the main role is to guide the user into the first action.

## 2. Surface Mapping

These mappings help agents identify likely modules for each page type.

- `assistant home surface`
  - `left navigation`
  - `workspace header`
  - `centered composer`
  - `action chips`
  - `recent task rail`

- `project dashboard surface`
  - `page header`
  - `recent carousel or recent row`
  - `view controls`
  - `project card grid`
  - `secondary filters`

- `skill discovery surface`
  - `page header`
  - `category tabs or segmented controls`
  - `featured card row`
  - `skill grid`
  - `create button`

- `plugin directory surface`
  - `page header`
  - `search field`
  - `connector sections`
  - `connector cards`
  - `section-level actions`

- `scheduled task surface`
  - `page header`
  - `explanatory modules`
  - `automation entry rows`
  - `primary creation button`

- `library surface`
  - `page header`
  - `filter row`
  - `search field`
  - `view toggle`
  - `document cards or file cards`

- `settings surface`
  - `settings navigation`
  - `profile block`
  - `plan card`
  - `usage chart`
  - `settings section blocks`

## 2A. Pattern Families

These mappings keep the communication layer generic and reusable.

- `centered home workspace`
  - `quiet left navigation`
  - `broad workspace container`
  - `centered composer`
  - `action chips`
  - `light utility indicators`

- `project browsing workspace`
  - `page header`
  - `recent carousel row`
  - `project card grid`
  - `view controls`
  - `secondary project metadata`

- `capability discovery workspace`
  - `page header`
  - `category switcher`
  - `featured cards`
  - `skill grid`
  - `create action`

- `board-style task workspace`
  - `context sidebar`
  - `task rail`
  - `workspace header`
  - `centered composer`
  - `action chips`

- `settings analytics workspace`
  - `settings navigation`
  - `profile block`
  - `plan card`
  - `usage chart`
  - `section-level controls`

- `capability catalog workspace`
  - `page header`
  - `search field`
  - `connector sections`
  - `connector cards`
  - `skill sections`

- `automation onboarding workspace`
  - `page header`
  - `instructional hero block`
  - `automation entry rows`
  - `primary creation action`

- `library browsing workspace`
  - `page header`
  - `filter controls`
  - `search row`
  - `view toggle`
  - `document cards`

## 3. Module Vocabulary

These terms answer: `具体是哪个模块？`

### Shell Modules

- `左侧导航（left navigation）`
- `导航分组（navigation group）`
- `近期任务栏（recent task rail）`
- `任务侧栏（task rail）`
- `侧边底部身份区（sidebar identity footer）`
- `全局顶部栏（global top bar）`
- `工作区容器（workspace container）`
- `上下文侧栏（context sidebar）`

### Header Modules

- `页面头部（page header）`
- `标题行（title row）`
- `说明区（supporting description）`
- `标题操作区（header actions）`
- `面包屑（breadcrumb row）`
- `模式切换器（mode switcher）`

### Typography And Copy Modules

- `显示标题（display heading）`
- `页面标题（page title）`
- `区块标题（section title）`
- `模块标题（module title）`
- `正文文案（body copy）`
- `辅助文案（supporting copy）`
- `说明文字（helper text）`
- `元信息文字（meta text）`
- `按钮文案（action label）`
- `占位文案（placeholder copy）`
- `空态文案（empty-state copy）`
- `错误文案（error copy）`

### Utility Modules

- `工具条（toolbar）`
- `工具行（utility row）`
- `搜索筛选行（search and filter row）`
- `排序控制区（sorting controls）`
- `视图切换器（view toggle）`
- `分段切换（segmented control）`

### Content Modules

- `卡片栅格（card grid）`
- `卡片行（card row）`
- `近期轮播行（recent carousel row）`
- `列表区（list section）`
- `列表项（list item）`
- `内容卡片（content card）`
- `项目卡片（project card）`
- `连接器卡片（connector card）`
- `技能卡片（skill card）`
- `文档卡片（document card）`
- `连接器分组（connector section）`
- `连接器列表（connector list）`
- `模板卡片（template card）`
- `预览卡片（preview card）`
- `轮播行（carousel row）`
- `精选区（featured section）`

### Task And Input Modules

- `输入容器（input composer）`
- `中心输入入口（centered composer）`
- `提示输入框（prompt field）`
- `快捷动作胶囊（action chips）`
- `能力胶囊（capability chips）`
- `附件操作区（attachment actions）`
- `发送区（send controls）`
- `任务条目（task entry row）`
- `任务状态行（task status row）`
- `自动化入口行（automation entry row）`

### Detail And Settings Modules

- `详情面板（detail panel）`
- `元信息行（meta row）`
- `设置导航（settings navigation）`
- `设置分组块（settings section block）`
- `计划卡片（plan card）`
- `使用情况图表（usage chart）`
- `表单分组（form group）`
- `字段行（field row）`
- `字段标签（field label）`
- `字段说明（field description）`
- `输入分组（input group）`
- `校验提示（validation message）`
- `保存栏（save bar）`
- `偏好项（preference row）`
- `危险操作区（danger zone section）`

### Data And Analytics Modules

- `统计卡片（stats card）`
- `数据表格（data table）`
- `列头（column header）`
- `表格行（table row）`
- `行操作（row actions）`
- `图表区（chart section）`
- `趋势图（trend chart）`
- `时间范围切换（time-range switcher）`
- `摘要指标行（summary metrics row）`

### Overlay Modules

- `浮层菜单（popover menu）`
- `下拉菜单（dropdown menu）`
- `筛选浮层（filter popover）`
- `确认弹窗（confirmation dialog）`
- `复杂模态框（workflow modal）`

### Feedback Modules

- `状态提示条（status banner）`
- `内联提示（inline notice）`
- `空态模块（empty state module）`
- `加载骨架（loading skeleton）`
- `错误反馈块（error feedback block）`

## 4. Component Vocabulary

These terms answer: `模块里具体是哪种控件？`

- `主按钮（primary action）`
- `次按钮（secondary action）`
- `文本按钮（text action）`
- `图标按钮（icon button）`
- `危险按钮（destructive action）`
- `搜索框（search field）`
- `普通输入框（input field）`
- `多行输入框（multiline input）`
- `下拉选择器（dropdown selector）`
- `标签胶囊（tag pill）`
- `状态徽标（status badge）`
- `复选项（checkbox row）`
- `单选项（radio option）`
- `切换开关（toggle switch）`
- `日期选择器（date picker）`
- `页签（tabs）`
- `分页器（pagination controls）`
- `列表操作按钮（row actions）`
- `更多菜单入口（overflow menu trigger）`

## 5. State Vocabulary

These terms answer: `当前在什么状态？`

- `默认态（default state）`
- `悬停态（hover state）`
- `聚焦态（focus state）`
- `选中态（selected state）`
- `激活态（active state）`
- `禁用态（disabled state）`
- `加载态（loading state）`
- `空态（empty state）`
- `错误态（error state）`
- `成功态（success state）`
- `展开态（expanded state）`
- `折叠态（collapsed state）`
- `筛选后状态（filtered state）`
- `排序后状态（sorted state）`

## 6. Detail Vocabulary

These terms answer: `问题具体出在哪种细节上？`

### Spacing And Rhythm

- `外边距（outer spacing）`
- `内边距（inner padding）`
- `区块间距（section gap）`
- `行间距（line spacing）`
- `阅读节奏（reading rhythm）`
- `内容节奏（content rhythm）`

### Typography And Copy Details

- `字号层级（type scale hierarchy）`
- `字重层级（font-weight hierarchy）`
- `标题重量（heading weight）`
- `文案长度（copy length）`
- `说明密度（supporting copy density）`
- `占位语气（placeholder tone）`
- `按钮命名清晰度（action-label clarity）`

### Shape And Framing

- `圆角等级（radius scale）`
- `边框强度（border intensity）`
- `边框重量（border weight）`
- `阴影重量（shadow weight）`
- `卡片重量（card emphasis）`
- `表面对比（surface contrast）`

### Hierarchy And Density

- `视觉层级（visual hierarchy）`
- `信息优先级（information priority）`
- `操作优先级（action priority）`
- `主次关系（primary-secondary balance）`
- `信息密度（information density）`
- `可扫描性（scannability）`
- `视觉焦点（visual focus）`
- `视觉噪音（visual noise）`

### Alignment And Consistency

- `对齐（alignment）`
- `标题对齐（title alignment）`
- `图标权重（icon weight）`
- `文本长度控制（copy length control）`
- `结构一致性（structural consistency）`
- `模式一致性（pattern consistency）`

### Color And Surface Details

- `主背景色（primary background tone）`
- `次级表面色（secondary surface tone）`
- `中性灰层级（neutral gray scale）`
- `强调色节制（accent restraint）`
- `暖白基调（warm off-white base）`
- `冷白基调（cool white base）`

## 7. Issue Vocabulary

These terms answer: `这个模块哪里不对？`

- `层级太平（hierarchy too flat）`
- `主入口不够明确（primary action not clear enough）`
- `次要操作太抢（secondary actions too prominent）`
- `模块太重（module too heavy）`
- `卡片存在感过强（card emphasis too strong）`
- `边框太显眼（borders too loud）`
- `信息密度过低（information density too low）`
- `信息密度过高（information density too high）`
- `间距过松（spacing too loose）`
- `间距过紧（spacing too tight）`
- `扫描节奏不稳（scanning rhythm inconsistent）`
- `视觉噪音过高（visual noise too high）`
- `对齐不稳（alignment feels unstable）`
- `标题太重（heading too heavy）`
- `标题不够立（heading not distinct enough）`
- `辅助文案过长（supporting copy too long at the text layer）`
- `文本层级不清（text hierarchy unclear）`
- `字段说明过多（field descriptions too verbose）`
- `表单节奏拖沓（form rhythm too slow）`
- `表格信息过挤（table density too cramped）`
- `图表区存在感不足（chart section not prominent enough）`
- `颜色对比过弱（color contrast too weak for hierarchy）`
- `颜色过冷或过白（surface feels too cold or too stark）`
- `颜色过暖或过灰（surface feels too warm or too muted）`
- `像营销模块（feels promotional）`
- `不像工作区组件（does not feel workspace-native）`
- `状态表达不清（state feedback unclear）`
- `模块边界不清（module boundaries unclear）`
- `说明文案过长（supporting copy too long）`
- `按钮优先级错误（action priority mismatch）`
- `局部 pattern 偏离现有产品语言（local pattern drifts from product language）`

## 8. Adjustment Vocabulary

These terms answer: `应该怎么调？`

- `收紧（tighten）`
- `放松（loosen）`
- `减弱（soften）`
- `强化（strengthen）`
- `统一（normalize）`
- `对齐到现有 pattern（align to existing pattern）`
- `降低存在感（reduce prominence）`
- `提升层级（raise hierarchy）`
- `降级为次要操作（demote to secondary action）`
- `突出主入口（clarify the primary action）`
- `改轻（lighten the treatment）`
- `改稳（make it feel steadier）`
- `减少视觉噪音（reduce noise）`
- `增强可扫描性（improve scannability）`
- `压缩文案（compress the copy）`
- `减轻标题重量（reduce heading weight）`
- `拉开文字层级（separate text hierarchy more clearly）`
- `简化字段说明（simplify field descriptions）`
- `统一表单节奏（normalize form rhythm）`
- `提高表格可扫描性（improve table scannability）`
- `让图表区更像辅助分析模块（make the chart section feel more like a supporting analytics module）`
- `往冷白方向调（shift toward a cooler white base）`
- `往暖白方向调（shift toward a warmer off-white base）`
- `减少装饰感（remove decorative treatment）`
- `保持工作区气质（keep the workspace-native feel）`

## 9. Decision Prompts

These prompts help agents ask useful follow-up questions instead of making random design decisions.

- `这里你更希望是列表优先还是卡片优先？`
  - `Do you want this area to stay list-first or become more card-first?`

- `这里要保留现在的信息密度，还是改得更开阔一些？`
  - `Should this keep its current density or become more spacious?`

- `这个操作应该保持主按钮，还是降级成次要操作？`
  - `Should this remain a primary action or be demoted to a secondary action?`

- `这里要更像工作区模块，还是更像内容展示卡片？`
  - `Should this feel more like a workspace module or more like a content card?`

- `你更在意扫描效率，还是更强的视觉区分？`
  - `Do you care more about scanning speed or stronger visual separation here?`

- `这里需要更轻的边界，还是更清晰的模块分割？`
  - `Should the framing become lighter, or do you want clearer separation between modules?`

- `这里的字体层级要更克制，还是更明显？`
  - `Should the typography hierarchy stay more restrained here, or become more pronounced?`

- `这里更接近冷白基调，还是暖白基调？`
  - `Should this lean closer to a cool white base or a warm off-white base?`

- `这里的表单说明要更完整，还是更短更快扫？`
  - `Should the form guidance be more complete here, or shorter and faster to scan?`

- `这里保留中心输入入口，还是把工具操作抬高？`
  - `Should the centered composer stay dominant, or should the utility actions become more prominent?`

- `这里是要延续现有 pattern，还是明确引入一个新的局部 pattern？`
  - `Should this align to the existing pattern, or are you intentionally introducing a new local pattern?`

## 10. Response Patterns

Agents should prefer returning feedback in this structure:

### Short Pattern

```text
Current surface:
Current module:
Main issues:
Suggested adjustments:
Need your decision on:
```

### Confirmation Pattern

Use this before implementation when the UI direction is not fully settled:

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

Guidance:

- `Pattern direction`
  - use a generic pattern family such as `centered home workspace`, `capability catalog workspace`, or `library browsing workspace`

- `Color direction`
  - use neutral color language such as `cool white base`, `warm off-white base`, or `keep current neutral palette`

- `Density direction`
  - say whether the module should become `denser`, `more open`, or `stay close to current density`

### Example

```text
Current surface: library surface
Current module: document card grid
Main issues: card emphasis too strong, secondary actions too prominent, scanning rhythm inconsistent
Suggested adjustments: lighten the card treatment, tighten spacing, demote secondary actions
Need your decision on: keep card-first layout or move closer to a list-first layout
```

### Reference-Aware Example

```text
Current surface: skill discovery surface
Current module: featured cards and skill grid
Reference direction: closer to the capability-discovery family
Main issues: card emphasis too strong, category hierarchy too weak
Suggested adjustments: lighten the featured cards, strengthen section headings, keep the grid scannable
Need your decision on: should this page feel more exploratory or more utility-driven?
```

### Confirmation Example

```text
Current surface: settings surface
Target module: settings section block and field descriptions
Observed issues: text hierarchy unclear, field descriptions too verbose, form rhythm too slow
Proposed improvements: reduce heading weight, shorten helper text, normalize spacing between preference rows
Pattern direction: settings analytics workspace
Color direction: keep current neutral palette
Density direction: slightly denser scanning
Need your decision on: do you want this settings area to stay more explanatory, or become faster and more compact to scan?
```

### Real-World Confirmation Examples

#### Example: Home Composer

```text
Current surface: assistant home surface
Target module: centered composer and action chips
Observed issues: supporting actions compete with the main entry, hierarchy is too flat
Proposed improvements: keep the composer dominant, reduce the prominence of action chips, tighten the spacing below the input area
Pattern direction: centered home workspace
Color direction: keep current neutral palette
Density direction: stay close to current density
Need your decision on: should this home surface remain strongly composer-first, or do you want the secondary actions to become more visible?
```

#### Example: Capability Page

```text
Current surface: plugin directory surface
Target module: connector sections and connector cards
Observed issues: card emphasis is too strong, scanning rhythm is uneven, add actions are not clear enough
Proposed improvements: lighten card framing, normalize connector section spacing, make add actions easier to scan
Pattern direction: capability catalog workspace
Color direction: warm off-white base
Density direction: slightly denser scanning
Need your decision on: should this page feel more like a lightweight catalog or a more structured utility directory?
```

#### Example: Library Page

```text
Current surface: library surface
Target module: search and filter row plus document cards
Observed issues: filter controls feel disconnected, document cards are too heavy, list-versus-card emphasis is unclear
Proposed improvements: tighten the utility row, reduce card emphasis, improve document scanning rhythm
Pattern direction: library browsing workspace
Color direction: cool white base
Density direction: denser scanning
Need your decision on: do you want this area to stay card-first, or move closer to a list-first browsing experience?
```

#### Example: Settings Page

```text
Current surface: settings surface
Target module: settings section block and field descriptions
Observed issues: helper text is too long, text hierarchy is weak, form rhythm feels slow
Proposed improvements: shorten field descriptions, separate title and helper hierarchy more clearly, tighten spacing between preference rows
Pattern direction: settings analytics workspace
Color direction: keep current neutral palette
Density direction: slightly denser scanning
Need your decision on: should this settings page stay more explanatory, or become more compact and faster to scan?
```

#### Example: Scheduled Task Page

```text
Current surface: scheduled task surface
Target module: instructional hero block and automation entry rows
Observed issues: the hero copy is carrying too much explanatory weight, entry rows do not clearly signal the next action
Proposed improvements: reduce copy length, clarify the primary creation path, make the entry rows feel more actionable
Pattern direction: automation onboarding workspace
Color direction: warm off-white base
Density direction: keep current density
Need your decision on: should this page feel more instructional, or more action-oriented from the first screen?
```

## 11. Ready-To-Use Sentences

Use these directly in human-agent conversations.

- `保持当前 app shell，不要改导航结构。`
  - `Keep the current app shell and do not change the navigation structure.`

- `这个模块更像轻量工作区卡片，不要做成营销卡片。`
  - `This module should feel like a lightweight workspace card, not a promotional card.`

- `这里的主问题是层级太平，主入口不够明确。`
  - `The main issue here is that the hierarchy is too flat and the primary action is not clear enough.`

- `请收紧这个模块的上下间距，提升可扫描性。`
  - `Please tighten the vertical spacing in this module and improve scannability.`

- `这个按钮太抢了，降级成次要操作。`
  - `This action is too prominent; demote it to a secondary action.`

- `这个筛选区可以保留，但请改成更轻的 filter row pattern。`
  - `The filtering can stay, but it should shift to a lighter filter row pattern.`

- `这里的说明文案过长，压缩成更短的 supporting copy。`
  - `The supporting copy is too long here; compress it into shorter supporting text.`

- `这里不像现有的 settings section，请对齐到现有设置页 pattern。`
  - `This does not feel like the existing settings section; align it to the current settings pattern.`

- `这里需要一个更安静的 utility row，不要和主内容竞争。`
  - `This needs a quieter utility row that does not compete with the main content.`

- `优先优化模块边界和信息优先级，不要先换视觉风格。`
  - `Prioritize module boundaries and information hierarchy before changing the visual style.`

- `这个页面的底色更适合冷白层次，不要做成太暖的灰白。`
  - `This surface should stay closer to a cool white layering rather than a warmer gray-white base.`

- `这个页面可以借暖白基调，但边框和卡片仍然要保持克制。`
  - `This page can borrow a warm off-white base, but the card and border treatment should remain restrained.`

- `这里先改文案层级和字段说明，不要急着加更多视觉装饰。`
  - `Prioritize the text hierarchy and field descriptions here before adding more visual styling.`

- `这个首页更接近 centered composer pattern，不要让辅助模块抢主入口。`
  - `This home surface should stay closer to a centered composer pattern; do not let supporting modules compete with the primary entry.`

- `这个能力页更接近 connector catalog pattern，先保证搜索、扫描和加装动作清楚。`
  - `This capability page should stay closer to a connector catalog pattern; prioritize search, scanning, and add/install actions.`

- `这个库页面更像 library surface，优先优化 filter row、search field 和 document card rhythm。`
  - `This page should feel closer to a library surface; prioritize the filter row, search field, and document card rhythm.`

- `这个技能发现页可以借轻卡片语法，但不要丢掉清晰的分类层级。`
  - `This skill discovery page can borrow a light card language, but it should keep a clear category hierarchy.`

- `这个定时任务页更适合 automation entry row pattern，不要直接堆复杂配置表单。`
  - `This scheduled task page should use automation entry rows rather than leading with dense configuration forms.`

## 12. Core Communication Rule

When unsure, do not describe a UI change as:

- `make it cleaner`
- `make it more advanced`
- `make it more modern`
- `make it look better`

Instead, describe it as:

1. `surface`
2. `module`
3. `issue`
4. `adjustment`
5. `decision`

That is the minimum standard for effective human-agent UI communication.

For any non-trivial UI task, the agent should also confirm:

6. `pattern direction`
7. `color direction`
8. `density direction`
