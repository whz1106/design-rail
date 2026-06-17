# 组件和模块规则

设计或修改重复出现的 app 模块时使用这些规则。

每个部分定义：模块作用、必须保持稳定的内容、禁止局部重造的内容。

## 组件库复用原则

进入实现前，先判断项目里有哪些可复用组件。

检查顺序：

1. 当前 surface 附近已有组件
2. `src/components/ui`
3. `src/renderer/components/ui`
4. `components/ui`
5. `package.json` 里的 UI 组件库
6. 项目已有 theme token 和 CSS variables

实现优先级：

1. 复用已有业务组件
2. 复用项目 `ui` 组件入口
3. 复用已安装组件库 primitives
4. 做轻量 wrapper
5. 最后才自定义组件

不要重写已有基础控件：

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

如果确实需要新增组件或组件库，必须先说明：

- 为什么已有组件不够
- 会影响哪些 surface
- 是否会引入第二套视觉语言
- 是否需要用户确认依赖安装

## App Shell

作用：

- 为整个产品提供持久桌面框架

必须：

- 保持稳定左侧导航 + 主工作区结构
- 保持 workspace 视觉主导
- shell actions 位置可预测
- shell styling 安静，可跨页面复用

禁止：

- 为单个功能重做 shell
- 让 shell 看起来像网页
- 在 shell 里加入装饰 banner 或推广区

## Sidebar And Navigation

作用：

- 帮助用户切换持久产品区域

必须：

- 导航稳定、可预测
- 使用紧凑 row，保持 icon 尺寸和 label 节奏一致
- 分组清晰
- selected state 可见但不喧闹

禁止：

- 把导航做成 card layout
- 为了解决局部页面问题移动全局导航
- 无功能原因使用装饰性 icon 或 badge

## Main Workspace

作用：

- 承载当前任务和主要内容

必须：

- 当前任务优先于周围 chrome
- 保持一个清晰主工作流
- 用 whitespace 分隔功能区域
- supporting content 比主任务更安静

禁止：

- 用装饰内容填空
- 把一个任务拆成太多等权重 panel
- 没有结构分隔地混合无关工作流

## Input Areas

作用：

- 支持写作、命令输入、配置输入或提交

必须：

- 按意图分组相关控件
- 主提交或确认 action 明显
- 支持键盘和指针使用
- helper text 简短且和状态相关
- 优先复用项目 composer/input 组件

禁止：

- 把输入相关控件散到多个无关区域
- 在模式和位置已能解释控件时加多余 label
- 普通输入时尺寸不可预测地变化

## Lists And Tables

作用：

- 高效呈现可扫描的重复对象

必须：

- row height 和 spacing 一致
- hover、selected、disabled、empty、loading 状态明确
- metadata 视觉次级
- 文本截断不破坏扫描节奏
- 优先复用已有 list/table primitives

禁止：

- 无明确内容理由把密集列表改成大卡片
- 在一个 list 内混用多套 border grammar
- 只靠颜色表达状态

## Cards And Content Modules

作用：

- 分组信息、模板、专家、项目、摘要

必须：

- 轻边框、克制框架
- card spacing 和 radius 一致
- 只有分组能提升理解时才使用 card
- 优先轻量模块呈现
- 复用现有 Card 或组件库 Card

禁止：

- 默认把每个页面 section 都做成 card
- 叠加重阴影和厚容器
- 没有强结构理由时 card 套 card

## Detail Views

作用：

- 深入展示一个记录、对象或模块

必须：

- 明确 title、metadata、main content、actions 顺序
- 内容易扫描
- alignment 和 spacing rhythm 稳定

禁止：

- actions 散落在页面各处
- 无关控件混入主阅读流
- 过度装饰 detail surface

## Dialogs, Menus, Popovers

作用：

- 处理一个范围明确的交互或次级任务

必须：

- overlay 聚焦
- 必要时使用清晰标题
- 保留 close、cancel、destructive 语义
- 匹配已有 border、radius、spacing、menu rhythm
- 优先复用项目或组件库 dialog/menu/popover

禁止：

- 一个 overlay 塞入无关工作流
- 用 overlay 替代应该成为页面的大任务
- 放入本该属于文档的长说明

## Settings And Forms

作用：

- 让用户可预测地配置产品行为

必须：

- 按意图分组 settings
- 使用合适控件类型
- forms 紧凑、可扫描
- advanced controls 视觉次级
- 优先复用 form/input/select/switch primitives

禁止：

- 把 settings 做成推广页
- grouped form rows 足够时使用过大 card
- destructive actions 和普通 controls 混在一起

## Status Feedback

作用：

- 传达 loading、empty、success、warning、failure、progress

必须：

- 状态文案短而直接
- loading 和 empty 时保持周围模块结构
- across pages 使用一致 semantic treatment
- 优先复用 badge、alert、toast、progress primitives

禁止：

- 每个模块发明不同 empty-state 风格
- 用装饰插图替代有用状态文案
- 让 error state 比必要更喧闹
