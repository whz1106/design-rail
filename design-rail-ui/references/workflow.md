# UI 修改工作流

所有 UI 相关修改都必须遵守这个 workflow。

这个文件定义 agent 和用户如何从需求、截图、模糊描述走到明确改法，再进入实现。

## 1. 触发条件

只要任务会改变以下内容，就进入该流程：

- 布局
- 间距
- 字体
- 组件样式
- 导航
- dialog、menu、popover
- 列表、卡片、设置、表单
- 截图参考界面
- 组件库复用或组件替换
- 任何可见的 renderer-facing surface

UI 工作不能当成普通代码任务处理。

## 2. 先读设计约束

编辑前必须读：

1. `design.md`
2. `component-rules.md`
3. `implementation-rules.md`

不要先改 UI，再事后解释为什么合理。

## 3. 识别目标 surface

实现前必须识别：

- 这个 surface 支持的用户任务
- 要改的 module 类型
- 当前 app 中最接近的已有模式
- 必须保持稳定的视觉层级
- 当前 theme、app shell、组件库约束
- 是否已有可复用组件

如果已有模式能满足，优先扩展已有模式，不要发明新模式。

## 4. 分类改动

实现前先分类：

- `Small change`：局部间距、文案、对齐、状态、控件调整
- `Module change`：一个已有模块或 surface 的明显调整
- `New module`：新页面区块、新模块、新交互模式

改动越大，设计方向越要明确。

## 5. UI 确认循环

实现前必须和用户确认 UI 方向。

这是硬门槛。agent 不能在第一次分析截图或提出设计方向的同一轮里直接改代码。

以下情况必须确认：

- 所有 `module changes`
- 所有 `new modules`
- 任何影响样式、层级、布局、颜色、字体、模式选择的小改动
- 任何包含当前截图、参考截图或模糊视觉反馈的任务
- 任何涉及组件库选择、组件替换、基础控件重写的任务

确认循环用于避免 agent 静默解释用户意图并跑偏。

如果涉及截图或参考图，必须先读 `screenshot-reading.md`。

### 5A. 必须返回结构化 UI Reading

提出改法前，agent 必须按这个结构描述：

```text
当前 surface（Current surface）:
目标 module（Target module）:
主要问题（Main issues）:
建议调整（Suggested adjustments）:
参考方向（Reference direction）:
参考图阅读（Reference reading）:
当前差异（Current mismatch）:
组件复用（Component reuse）:
需要你确认（Need your decision on）:
```

最低必须包含：

- `当前 surface（Current surface）`
- `目标 module（Target module）`
- `主要问题（Main issues）`
- `建议调整（Suggested adjustments）`

当有参考截图时，必须包含 `参考图阅读（Reference reading）`。

当同时有当前 app 截图和参考截图时，必须包含 `当前差异（Current mismatch）`。

当涉及实现时，必须包含 `组件复用（Component reuse）`，说明会优先复用哪些已有组件或组件库 primitives。

输出结构化 reading 后停止，等待用户确认。

### 5B. 必须确认的问题

agent 应明确确认：

- `where`：改哪里
- `what`：改哪个 module
- `why`：当前 UI 弱在哪里
- `how`：计划如何改
- 是否保持已有模式
- 色彩方向是否需要冷白、暖白或保持当前 palette
- 密度是更紧凑还是更开放
- 当前问题主要是结构、层级、表面处理、密度还是控件语言
- 组件实现上复用已有组件，还是需要新增/封装组件

### 5C. 决策问题必须聚焦

好的问题：

- 这个区域保持 card-first，还是更接近 list-first？
- composer 继续做视觉重心，还是提高内容区权重？
- 保持 cool white base，还是转向 warm off-white base？
- 当前密度保持，还是收紧一档？
- 保持现有模式，还是明确引入一个新的局部变化？
- 这里比参考图更重，主要因为卡片框架和间距偏松；是否保持骨架，只收紧这两项？
- 这个按钮使用项目已有 Button，还是需要基于组件库封装一个 AppButton？

坏的问题：

- 你喜欢什么风格？
- 要不要更高级一点？
- 要不要换个颜色？
- 不说明 surface 和 module 的开放式审美问题

### 5D. 未确认不能实现

如果用户没有确认方向，agent 必须：

- 继续细化 UI reading
- 缩小设计选项
- 问缺失的决策问题

截图驱动任务中，`direction is clear` 的意思是：用户确认了一个改法路径，或使用提供的术语明确说明想要的路径。

`改好看点`、`更现代`、`照着截图改` 不算有效确认。

### 5E. 截图任务固定流程

涉及截图时按这个顺序：

1. 识别目标 surface 和 module
2. 用 `screenshot-reading.md` 阅读参考截图
3. 对比当前 UI 和参考截图
4. 命名差异的可能原因
5. 给出保守、中等、强改法路径
6. 提出 1-3 个聚焦决策问题
7. 等用户回答

默认选择最小的已确认改动。

第 7 步完成前不能开始实现。

## 6. 写设计方向

小改动写一句：

```text
Design direction: [改什么]，同时保持 [已有结构或层级]。
```

模块改动或新模块需要定义：

- layout structure
- module role
- primary / secondary actions
- empty、loading、error、selected states
- 如何保持当前产品语言
- 组件复用方案

没有现成模式可用时，不能静默发明。必须先说明拟定方向。

## 7. 保守实现

实现规则：

- 优先复用已有组件
- 优先复用已安装组件库
- 优先复用 tokens 和附近 spacing grammar
- 改动限制在目标 surface
- 保持 app shell 稳定
- 避免一次性整页重做
- 避免局部 one-off 样式

UI 改动应该像当前系统的自然延伸，而不是局部重新设计。

## 8. 对照产品规则 review

完成前检查：

- `design.md`
- `component-rules.md`
- `implementation-rules.md`

如果出现以下问题，不能认为完成：

- 引入新的局部风格语言
- 打破 shell 或层级一致性
- surface 看起来更像网页模板或 dashboard 模板
- 重写了已有基础控件
- 直接写死本该来自 token 或组件库的样式

## 9. 验证真实状态

最低验证：

- 主状态
- 空态
- 加载态
- 错误态
- selected / active 状态
- 中英文长文本
- 常见桌面窗口尺寸
- 明暗主题预期
- skeleton、hierarchy、surface treatment、density、control language、product consistency

TypeScript 或 build 通过，不代表 UI 完成。

视觉质量不能只靠代码 review 声明。

首选视觉验收循环是用户截图驱动：

1. agent 实现已确认改动
2. 用户打开 app，并在视觉质量重要时提供更新截图
3. agent 对比更新截图、确认方向和参考截图
4. 如果仍未达标，agent 提出下一步最小调整

普通 UI review 不要求 agent 默认启动 Playwright。

如果没有更新截图或用户视觉确认，必须标记为 `pending user review`。

### 9A. 最终 UI Review 模板

完成 UI 修改时，用这个结构总结：

```text
UI review:
- Skeleton:
- Hierarchy:
- Surface treatment:
- Density:
- Control language:
- Component reuse:
- Product consistency:
- Visual verification:
```

`Visual verification` 只能写：

- `confirmed by updated user screenshot`
- `pending user screenshot review`
- `pending user visual confirmation`

不要写泛泛的 `looks cleaner` 或 `more modern`。

## 10. 完成定义

UI 任务完成必须满足：

- 功能可用
- 目标 surface 仍然像同一个产品
- 没有引入不必要的新模式
- 组件复用和代码结构合理
- 关键状态已检查
- 实现前用户已确认方向
- 视觉验收已确认或明确 pending

如果功能可用但视觉语言不一致，则未完成。
