# UI 设计契约

这是 Design Rail UI 的设计总纲。

它不是灵感文档，而是约束文档。目标是让开发者和 coding agent 在长期修改 UI 时保持视觉和结构一致。

配合以下文件使用：

1. `workflow.md`
2. `component-rules.md`
3. `implementation-rules.md`

## 目的

这个 workflow 用来防止：

- 不同 agent 做出不同产品风格
- 新模块随意发明新布局范式
- UI 漂移成通用 dashboard 或营销页
- 为了快速实现而破坏长期设计一致性
- 在已有组件库时仍然手写一套控件语言

如果一个改动功能可用，但明显破坏产品视觉语言，则不能算完成。

## 参考风格

当前 v1 参考方向来自几类产品截图：

- Codex 桌面 app 截图
- WorkBuddy light-theme 截图
- YouMind / Manus 等 AI 工作台和知识工作流界面

这些参考定义的是结构层面的产品语言，不要求逐像素复制颜色。

固定部分：

- 桌面工作台结构
- 稳定左侧导航 + 主工作区
- 克制的 panel styling
- 冷静的信息层级
- 紧凑但可读的控件密度
- 低对比 surface 和轻边框
- 一致的 menu、popover、settings、list 行为

可变部分：

- 具体色盘
- 明暗主题选择
- 产品自有图标、插图、文案
- 项目具体组件库

## 产品气质

UI 应该感觉：

- 冷静
- 结构化
- 工具化
- 桌面优先
- 可靠
- 克制
- 精确

UI 不应该感觉：

- 营销化
- 为了可爱而可爱
- 装饰过重
- 追逐潮流
- 默认卡片堆叠
- 视觉喧闹

## 产品语言

v1 视觉语言应偏向：

- 稳定导航
- 宽阔主工作区
- 克制模块框架
- 紧凑但舒适的控件
- 轻量 card、menu、popover

这是生产力工具，不是品牌落地页，也不是通用 dashboard 模板。

## 布局语言

保持稳定 app shell：

- 左侧导航持久、可预测
- 主工作区视觉主导
- 次级 panel 支持任务，不抢任务焦点
- dialog、popover、menu 保持任务范围内

修改必须保持以下关系：

- navigation
- workspace
- contextual controls
- overlays

不要为了一个页面引入新的布局语法，除非用户先确认它会成为可复用模式。

## Surface 语言

surface 应该：

- 轻分隔
- 圆角克制
- 用轻边框而不是重阴影
- 间距和内部节奏一致

层级优先通过以下方式表达：

- spacing
- typography
- alignment
- quiet borders
- 必要时的 subtle surface shifts

不要依赖：

- 大面积强渐变
- 高饱和填充
- 夸张阴影
- 只为填空而出现的装饰插图

## 字体和密度

字体服务于扫描和长时间工作。

应该：

- 标题紧凑、有用
- label 简短
- 次级信息使用 muted text
- 信息密度适合工具使用

不应该：

- 在工具界面使用营销页 hero 标题
- 做大块空白但信息很少
- 让 utility controls 过大
- 把说明文案写成长段 UI copy

## 颜色策略

颜色不是这个系统的主要身份锚点。

颜色用于支持：

- action priority
- selected state
- semantic status
- subtle product tone

不要用颜色弥补结构问题。

改变 palette 可以，改变结构语言不可以。

## 组件库策略

组件库是控件层约束，不是整体页面设计。

组件库可以统一：

- Button
- Input
- Select
- Tabs
- Modal / Dialog
- Dropdown
- Tooltip
- Card
- Badge
- Switch / Checkbox
- Table / List primitives

组件库不能替代：

- 页面骨架
- 信息层级
- 视觉重心
- 模块密度
- 产品气质
- 截图差异判断

因此，使用组件库时仍必须遵守 Design Rail workflow。

项目已有组件库时：

- 优先复用项目已有组件
- 不直接重写基础控件
- 不绕过 theme token 写死局部样式
- 新增组件库必须先得到用户确认

## 动效

动效用于说明状态，不用于表演个性。

默认允许：

- subtle hover feedback
- open / close transition
- loading / progress communication
- scoped expand / collapse

默认禁止：

- 循环装饰动画
- 会移动的背景
- 夸张入场动画

## 使用截图参考

有截图时，从截图中提取约束，不盲目复制。

提取：

- app type
- layout structure
- density
- surface model
- text hierarchy
- interaction model
- theme behavior
- control language

不要提取：

- 不属于本产品的品牌
- 无关文案
- 平台窗口 chrome，除非任务明确需要

适配截图时，用这种方向说明：

```text
使用参考图的 [layout / density / surface / control behavior]，
适配到当前 app 结构。
保持 [existing hierarchy / data flow / module pattern]。
避免 [non-matching patterns]。
```

目标是让结果像同一个产品，而不是导入一张截图。

## 硬禁止

除非用户明确批准，禁止：

- 在 app 内做营销页 hero layout
- 用装饰 dashboard card grid 填空间
- 为一个功能引入新的导航模型
- 把密集列表改成大 promo card
- 默认使用 glow、glassmorphism、neon、ornamental gradients
- 创造不匹配附近 surface 的 one-off 控件样式
- 为了“现代感”增加额外复杂度
- 项目已有组件库时重写基础控件
