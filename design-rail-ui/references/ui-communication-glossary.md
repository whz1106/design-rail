# UI 沟通术语表

这个文件是人和 agent 之间的 UI 沟通层。

它帮助：

- 用户不用只靠截图描述 UI 问题
- agent 把模糊反馈映射到稳定术语
- 双方用同一套词讨论问题和取舍

配合以下文件使用：

1. `design.md`
2. `workflow.md`
3. `component-rules.md`
4. `screenshot-reading.md`
5. `ui-glossary.md`

## 使用方式

描述 UI 反馈时按这个顺序：

1. `surface`
2. `module`
3. `issue`
4. `adjustment`
5. `decision`

示例：

```text
保持在现有 library surface 内。
search and filter row 可以保留，但 document cards 视觉太重。
主要问题是 card emphasis too strong 和 scanning rhythm too loose。
请减轻 card framing，收紧 vertical spacing，并降低 secondary action prominence。
如果需要，问我是保持 card-first 还是更接近 list-first。
```

用户给模糊反馈时，agent 不要重复模糊词，而要翻译成 1-2 个可能 UI 问题并确认。

示例：

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

有截图或参考产品时，必须使用 `screenshot-reading.md`。

## 视觉对比轴

这些比泛泛的风格词更有用：

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
- `组件复用充分 / 局部重造过多`

## Surface 术语

- `应用外壳（app shell）`
  - 产品稳定外框，包括全局导航和主工作区关系。

- `助手首页（assistant home surface）`
  - 以任务输入、prompt、AI 启动为中心的首页。

- `项目页（project dashboard surface）`
  - 用于扫描项目、最近内容、项目模块的页面。

- `项目工作区（project workspace surface）`
  - 一个项目或任务板正在被使用的工作区。

- `技能发现页（skill discovery surface）`
  - 浏览技能、专家、能力的页面。

- `插件目录页（plugin directory surface）`
  - 浏览插件、连接器、集成的页面。

- `连接器目录页（connector catalog surface）`
  - 展示外部工具、API、服务连接的列表页。

- `定时任务页（scheduled task surface）`
  - 设置和管理周期自动化任务的页面。

- `资料库页（library surface）`
  - 浏览文件、文档、生成资产的页面。

- `设置页（settings surface）`
  - 结构化配置偏好的页面。

- `详情页（detail surface）`
  - 聚焦一个对象、记录或模块的页面。

- `搜索结果页（search results surface）`
  - 为扫描搜索匹配项优化的页面。

- `空态入口页（empty-state entry surface）`
  - 主要任务是引导用户开始第一步的页面。

## 常见页面映射

- `assistant home surface`
  - `left navigation`
  - `workspace header`
  - `centered composer`
  - `action chips`
  - `recent task rail`

- `project dashboard surface`
  - `page header`
  - `recent carousel / recent row`
  - `view controls`
  - `project card grid`
  - `secondary filters`

- `skill discovery surface`
  - `page header`
  - `category tabs / segmented controls`
  - `featured card row`
  - `skill grid`
  - `create button`

- `plugin directory surface`
  - `page header`
  - `search field`
  - `connector sections`
  - `connector cards`
  - `section-level actions`

- `library surface`
  - `page header`
  - `filter row`
  - `search field`
  - `view toggle`
  - `document cards / file cards`

- `settings surface`
  - `settings navigation`
  - `profile block`
  - `plan card`
  - `usage chart`
  - `settings section blocks`

## Pattern Families

- `centered home workspace`
  - 安静左侧导航、宽主工作区、居中 composer、action chips、轻 utility indicators。

- `project browsing workspace`
  - page header、recent row、project card grid、view controls、次级 metadata。

- `capability discovery workspace`
  - page header、category switcher、featured cards、skill grid、create action。

- `capability catalog workspace`
  - page header、search field、connector sections、connector cards、skill sections。

- `board-style task workspace`
  - context sidebar、task rail、workspace header、centered composer、action chips。

- `settings analytics workspace`
  - settings navigation、profile block、plan card、usage chart、section-level controls。

- `library browsing workspace`
  - page header、filter controls、search row、view toggle、document cards。

- `automation onboarding workspace`
  - page header、instructional hero block、automation entry rows、primary creation action。

## Module 术语

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

### 输入和任务模块

- `输入组合器（composer）`
- `输入工具栏（input toolbar）`
- `快捷动作胶囊（action chips）`
- `权限选择器（permission selector）`
- `连接器选择器（connector selector）`
- `技能选择器（skill selector）`
- `提交按钮（submit control）`
- `工作区选择器（workspace selector）`

### 内容模块

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
- `模板卡片（template card）`
- `预览卡片（preview card）`
- `精选区（featured section）`

### 表单和设置模块

- `设置导航（settings navigation）`
- `设置分组（settings section）`
- `表单行（form row）`
- `字段组（field group）`
- `开关行（toggle row）`
- `危险操作区（danger zone）`
- `计划卡片（plan card）`
- `用量图表（usage chart）`

### Overlay 模块

- `弹窗（dialog / modal）`
- `菜单（menu）`
- `下拉（dropdown）`
- `气泡层（popover）`
- `提示（tooltip）`
- `确认弹窗（confirmation dialog）`

## 组件库术语

- `项目组件入口（project component entrypoint）`
  - 例如 `src/components/ui`、`src/renderer/components/ui`、`components/ui`。

- `组件库 primitive（library primitive）`
  - 组件库提供的基础控件，例如 Button、Input、Dialog、Tabs、Card。

- `业务组件（product component）`
  - 项目内已经带有业务语义和产品风格的组件。

- `轻量 wrapper（thin wrapper）`
  - 在组件库 primitive 外包一层，用来固定默认 props、token、radius、variant。

- `局部重造（local recreation）`
  - 不复用已有组件，直接手写一套相同控件。默认禁止。

## 差异级术语

- `主视觉弱（weak visual center）`
  - 页面缺少清晰第一视觉焦点。

- `模块抢焦点（module competes for attention）`
  - 次级模块看起来和主任务一样重要。

- `卡片过重（card weight too heavy）`
  - card border、fill、shadow 或 spacing 让模块过于显眼。

- `边框过强（border presence too strong）`
  - border 比层级需要的更明显。

- `扫描节奏松（scan rhythm too loose）`
  - 间距太开放，不利于工具型扫描。

- `控件语言不统一（control language inconsistent）`
  - button、input、selector、chip 不像同一系统。

- `局部网页感（local web-page feel）`
  - 某一区域像营销页或网页模板，不像 app。

- `结构正确但表面不对（correct skeleton, wrong surface treatment）`
  - 布局可接受，但 card、border、fill、control 需要调整。

- `组件复用不足（component reuse insufficient）`
  - 有现成组件却手写了新的基础控件或样式。

## 决策级术语

- `保持骨架只调样式（keep skeleton, adjust styling only）`
- `轻量重排（light rebalance）`
- `局部重做（local rebuild）`
- `向参考图靠近一档（move one step closer to reference）`
- `只迁移控件语言（adopt control language only）`
- `只收紧密度（tighten density only）`
- `减轻卡片重量（reduce card weight）`
- `降低次级操作存在感（lower secondary action prominence）`
- `提高主视觉权重（raise primary visual weight）`
- `复用现有组件（reuse existing components）`
- `新增轻量 wrapper（add thin wrapper）`
- `新增依赖前确认（confirm before adding dependency）`

## 用户短语翻译

- `更干净`
  - 可能是：边框减轻、accent 减少、层级更紧。

- `更高级`
  - 可能是：控件更克制、模板感更弱、spacing 更有纪律。

- `更像参考图`
  - 可能是：骨架、card/list 重量、密度、视觉重心更接近。

- `太乱了`
  - 可能是：层级发散、utility controls 抢焦点、spacing rhythm 不一致。

- `太重了`
  - 可能是：card fill 太强、border 太深、shadow 或 tinted surface 太明显。

- `太空了`
  - 可能是：密度太低、模块太分散、扫描节奏不足。

- `太挤了`
  - 可能是：控件过近、层级被压缩、功能组之间留白不足。

- `这个组件不像一套`
  - 可能是：没有复用已有组件或组件库 primitive，导致 control language inconsistent。

agent 响应模式：

```text
我先把这句话翻译成更具体的 UI 问题：
- [issue 1]
- [issue 2]

如果这个翻译对，我会优先改 [module]，并保持 [existing pattern] 不变。
组件实现上优先复用 [existing component / library primitive]。
```

## 确认问题模板

- `这个区域是保持当前骨架，只调 surface treatment，还是允许轻量重排？`
- `你更希望卡片减轻一档，还是整体向 list-first 靠近？`
- `这里更在意扫描速度，还是更强的模块分隔？`
- `composer 要继续做视觉重心，还是提高内容区权重？`
- `实现时复用现有 Button/Input/Card，还是允许封装一个新的产品组件？`
- `是否允许新增组件库依赖？如果不允许，我会只用现有组件。`

## 不合格表达

agent 不应该只说：

- `我会优化一下`
- `我会做得更现代`
- `我会参考截图`
- `我会调整样式`

agent 应该说：

```text
我会保持当前 skeleton，只降低 card weight 和 border presence，
密度收紧一档，控件复用现有 Button / Input / Card。
如果你确认这个方向，我再实现。
```
