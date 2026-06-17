---
name: design-rail-ui
description: 用于会影响产品一致性的前端 UI 任务，包括 app 界面、可见组件、布局、样式、导航、弹窗、卡片、设置、列表、表单、颜色、字体、截图参考界面、组件库复用和其他 renderer-facing surface。
---

# Design Rail UI

Design Rail UI 是一套给 coding agent 和开发者共用的前端 UI 工作流。

它的目标不是让 agent 自由发挥设计，而是让 UI 修改保持同一套产品语言：先读图，先确认，再按最小范围实现。

## 什么时候使用

只要任务会影响可见 UI，就使用这个 skill：

- 页面、模块、组件
- 间距、排版、颜色、字体、表面处理
- 导航、弹窗、菜单、popover
- 卡片、列表、设置、表单
- 参考截图、当前截图、视觉风格调整
- 组件库复用、组件替换、组件封装
- 任何 renderer-facing surface

以下情况不用：

- 后端-only 修改
- 不影响 UI 的内部重构
- 不改变渲染结果的纯技术修复

## 必读文件

提出 UI 改法前必须读：

1. `references/design.md`
2. `references/workflow.md`
3. `references/component-rules.md`
4. `references/ui-communication-glossary.md`
5. `references/screenshot-reading.md`

涉及代码实现时还必须读：

- `references/implementation-rules.md`

需要更多页面模式、颜色家族、结构术语时再读：

- `references/ui-glossary.md`

## 硬门槛

识别到 UI 任务后，不允许直接实现。

只要任务涉及截图、参考图、视觉风格、布局、层级、密度、颜色、组件处理或组件库复用，确认就是必需步骤。

实现前必须完成：

1. 识别当前 `surface`
2. 识别目标 `module`
3. 说清主要 `issues`
4. 提出计划中的 `adjustments`
5. 提出聚焦的设计决策问题
6. 等待用户明确确认后再改代码

以下情况必须先确认：

- `module change`
- `new module`
- 用户提供了当前截图或参考截图
- 小改动但影响布局、层级、颜色、字体、模式选择、密度、组件库使用

没有确认，就不能实现。

如果用户提供截图，必须先返回截图差异报告和改法选项，然后停下来等待用户确认。

## 截图任务必须输出

当用户提供当前截图、参考截图或模糊视觉反馈时，先输出：

```text
当前 surface（Current surface）:
目标 module（Target module）:
参考图阅读（Reference reading）:
当前差异（Current mismatch）:
可能原因（Likely cause）:
推荐改法路径（Recommended adjustment paths）:
需要你确认（Need your decision on）:
```

然后停止，等待用户确认。

不能在第一次截图分析的同一轮里直接改文件，除非用户已经明确确认了改法。

## 组件库复用协议

Design Rail 不绑定某一个组件库。每个项目可以使用自己的组件库，例如 HeroUI、shadcn/ui、Radix、Headless UI 或内部组件系统。

进入实现前，agent 必须先检查当前项目的组件环境：

1. 查看 `package.json` 是否已有 UI 组件库
2. 查看项目组件入口，例如 `src/components/ui`、`src/renderer/components/ui`、`components/ui`
3. 查看目标页面附近是否已有相似组件、卡片、行、弹窗、输入区、toolbar
4. 先复用项目已有组件，再考虑直接使用已安装组件库
5. 新增组件库或新造基础控件前必须问用户

实现优先级：

1. 项目已有业务组件
2. 项目已有 `components/ui` 或类似 UI 入口
3. 已安装组件库的 primitives
4. 基于已有组件的小封装
5. 自定义组件，且必须说明为什么不能复用

禁止默认重写：

- Button
- Input
- Select
- Dialog / Modal
- Tabs
- Dropdown
- Tooltip
- Card
- Badge
- Switch / Checkbox
- Table / List primitives

## 执行流程

### 1. 分类改动

先把任务分类：

- `small change`
- `module change`
- `new module`

然后识别：

- 当前 surface
- 目标 module
- 最近的已有模式
- app shell 和层级约束
- 可复用组件和组件库入口

完整流程见 `references/workflow.md`。

### 2. 运行确认循环

实现前必须返回结构化 UI reading：

```text
当前 surface（Current surface）:
目标 module（Target module）:
观察到的问题（Observed issues）:
建议改法（Proposed improvements）:
模式方向（Pattern direction）:
颜色方向（Color direction）:
密度方向（Density direction）:
组件复用（Component reuse）:
需要你确认（Need your decision on）:
```

最低必须包含：

- `当前 surface（Current surface）`
- `目标 module（Target module）`
- `观察到的问题（Observed issues）`
- `建议改法（Proposed improvements）`

如果涉及截图，还必须包含：

- `参考图阅读（Reference reading）`
- `当前差异（Current mismatch）`
- `可能原因（Likely cause）`
- `推荐改法路径（Recommended adjustment paths）`
- `需要你确认（Need your decision on）`

然后停下来等待用户确认。

### 3. 只在方向明确后实现

用户确认后：

- 写一句简短的 `Design direction`
- 遵守 `workflow.md`
- 遵守 `component-rules.md`
- 涉及代码时遵守 `implementation-rules.md`
- 优先复用当前项目组件和已安装组件库

不要静默创造新的局部 UI 模式。

## 沟通规则

讨论 UI 时不要停留在模糊词：

- `更干净`
- `更高级`
- `更现代`
- `更好看`

必须翻译成：

1. `surface`
2. `module`
3. `issue`
4. `adjustment`
5. `decision`

非平凡 UI 任务还要确认：

6. `pattern direction`
7. `color direction`
8. `density direction`
9. `component reuse`

## 术语路由

使用 `references/ui-communication-glossary.md` 处理：

- 页面名
- 模块名
- 组件名
- 问题名
- 调整动词
- 确认模板
- 模糊反馈翻译

使用 `references/screenshot-reading.md` 处理：

- 截图阅读顺序
- 当前截图和参考截图对比
- visual contrast pairs
- screenshot-to-decision prompts

使用 `references/ui-glossary.md` 处理：

- 更广泛的 pattern family
- surface 和结构术语
- 视觉和交互词汇
- 中性颜色方向

## 完成标准

UI 任务完成必须同时满足：

- 功能可用
- surface 仍然像同一个产品
- 没有引入不必要的新模式
- 代码结构合理
- 已检查关键状态
- 实现前设计方向已被确认
- 已按 skeleton、hierarchy、surface treatment、density、control language、product consistency 做最终 review
- 视觉验收由用户更新截图确认，或明确标记为 `pending user review`

详细验收流程见 `references/workflow.md`。
