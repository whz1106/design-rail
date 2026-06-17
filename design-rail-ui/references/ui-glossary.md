# UI 通用术语表

这个 glossary 把参考截图和常见 AI app 页面转成可复用设计语言。

它不是完整 design system，而是帮助人和 agent 讨论：

- 页面类型
- 页面骨架
- 模块组织
- 视觉差异
- 控件语言
- 组件复用

## 使用原则

优先使用中英文混合术语。

中文帮助团队沟通，英文帮助 agent 和代码语境对齐。

示例：

```text
这个 assistant home surface 的 composer 视觉权重偏弱。
建议保持 sidebar + workspace skeleton，只减轻 card weight，并收紧 density。
```

## Surface Families

### `centered home workspace`

适合：

- AI 助手首页
- chatbot 首页
- 新任务入口
- 空态工作台

典型结构：

- quiet left navigation
- broad workspace container
- centered composer
- action chips
- light utility indicators

常见问题：

- composer 不够主导
- action chips 过多抢焦点
- 空白太大但没有节奏
- sidebar promo card 太重

### `project browsing workspace`

适合：

- 项目列表
- 最近任务
- 资产浏览

典型结构：

- page header
- recent row
- view controls
- project card grid
- secondary metadata

常见问题：

- card grid 过重
- metadata 抢主标题
- 最近区域和主列表层级不清

### `capability discovery workspace`

适合：

- 技能发现
- 专家列表
- 模板市场
- 能力浏览

典型结构：

- page header
- category switcher
- featured section
- skill grid
- create action

常见问题：

- 过于营销页
- featured cards 太大
- category 和 grid 控件语言不一致

### `capability catalog workspace`

适合：

- 插件目录
- connector catalog
- 集成服务列表

典型结构：

- page header
- search field
- connector sections
- connector cards
- section-level actions

常见问题：

- connector card 像广告卡片
- search/filter row 过重
- section 之间分隔不稳定

### `settings analytics workspace`

适合：

- 设置页
- 账号页
- 订阅和用量页

典型结构：

- settings navigation
- profile block
- plan card
- usage chart
- settings section blocks

常见问题：

- settings 被做成宣传页
- plan card 抢过多注意力
- form rows 不够可扫描

### `library browsing workspace`

适合：

- 资料库
- 文件管理
- 文档浏览
- 生成物资产页

典型结构：

- page header
- filter controls
- search row
- view toggle
- document cards / list items

常见问题：

- document cards 太重
- density 太松
- search/filter 和内容区不成体系

## Layout Terms

- `app shell`
  - 稳定外壳，通常包含导航和主工作区。

- `sidebar + workspace`
  - 左侧导航或侧栏 + 主工作区结构。

- `centered composition`
  - 主要内容居中，常见于 assistant home。

- `split workspace`
  - 主工作区被拆成两个主要 panel。

- `context sidebar`
  - 跟当前任务相关的侧栏。

- `workspace container`
  - 主工作区容器。

- `visual center`
  - 用户第一眼关注的核心位置。

- `primary workflow`
  - 当前页面最重要的操作路径。

## Surface Treatment Terms

- `flat surface`
  - 几乎不使用 card 边框，靠间距和对齐表达结构。

- `light card`
  - 轻边框、低对比、少阴影的卡片。

- `heavy card`
  - 强边框、强填充、明显阴影或过大留白的卡片。

- `panel-like`
  - 更像工作区 panel，而不是内容卡片。

- `overlay-like`
  - 具有浮层感，通常用于 dialog、popover。

- `border-led`
  - 主要靠边框表达边界。

- `fill-led`
  - 主要靠背景填充表达边界。

## Density Terms

- `compact`
  - 紧凑，适合工具和列表扫描。

- `balanced`
  - 平衡，适合多数工作台 UI。

- `open`
  - 留白更大，适合入口页或低信息量状态。

- `scan-dense`
  - 信息密度较高，但仍可扫描。

- `scan-loose`
  - 扫描节奏偏松，可能显得空。

## Control Language Terms

- `restrained controls`
  - 克制控件，低噪声、不过分装饰。

- `rounded restrained`
  - 圆角存在但不过软。

- `border quiet`
  - 边框存在但不抢视觉。

- `primary action restrained`
  - 主按钮可见但不喧闹。

- `input presence strong`
  - 输入区视觉权重强。

- `input presence quiet`
  - 输入区更安静。

## Component Terms

- `component primitive`
  - Button、Input、Tabs、Dialog 等基础控件。

- `project component`
  - 项目内已有封装组件，通常带产品默认样式。

- `thin wrapper`
  - 对组件库 primitive 做轻封装，固定默认 props 和 token。

- `component entrypoint`
  - 项目组件入口，如 `components/ui`。

- `component mapping`
  - 把目标 UI 模块映射到已有组件，例如 composer -> AppInput + Button + Dropdown。

- `raw HTML recreation`
  - 已有组件可用时仍手写 div/button/input，默认不允许。

## Visual Issues

- `card weight too heavy`
  - 卡片边框、背景、阴影或 spacing 过重。

- `border presence too strong`
  - 边框比层级需要更明显。

- `hierarchy scattered`
  - 主次关系发散。

- `weak visual center`
  - 缺少清晰视觉重心。

- `scan rhythm too loose`
  - 间距过松，不利于工具使用。

- `control language inconsistent`
  - 控件不像同一套系统。

- `local web-page feel`
  - 局部像网页模板，不像 app。

- `component reuse insufficient`
  - 没有充分复用已有组件或组件库。

## Adjustment Verbs

- `减轻（soften）`
  - 降低边框、填充、阴影或视觉重量。

- `收紧（tighten）`
  - 减少松散 spacing，提高扫描节奏。

- `弱化（de-emphasize）`
  - 降低次级内容或 action 的存在感。

- `提高权重（raise prominence）`
  - 提高主模块、主输入或主 action 的视觉优先级。

- `对齐（align）`
  - 让模块或控件和已有系统一致。

- `复用（reuse）`
  - 使用已有组件、组件库 primitive 或 token。

- `封装（wrap）`
  - 基于已有 primitive 做轻量 wrapper。

## 推荐表达

用户可以说：

```text
这个 settings surface 的 plan card 太重。
我想保持当前骨架，只减轻 card weight 和 border presence。
组件实现上优先复用现有 Card 和 Button。
```

agent 应回复：

```text
当前 surface（Current surface）: settings surface
目标 module（Target module）: plan card
观察到的问题（Observed issues）:
- card weight too heavy
- border presence too strong

建议改法（Proposed improvements）:
- reduce card weight
- quiet borders
- keep current skeleton

组件复用（Component reuse）:
- reuse existing Card and Button if available

需要你确认（Need your decision on）:
1. keep light-card, or move flatter?
2. tighten density one step, or keep current spacing?
```

## 禁止表达

不要只说：

- `做得高级一点`
- `照着参考图`
- `优化 UI`
- `随便改好看点`

agent 也不能只回复：

- `我会优化样式`
- `我会让它更现代`
- `我会参考截图实现`

必须把反馈翻译成具体 surface、module、issue、adjustment、decision。
