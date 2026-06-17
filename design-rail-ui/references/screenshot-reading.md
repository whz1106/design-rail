# 截图阅读规则

当用户提供截图、参考图或模糊反馈时使用本文件。

常见触发：

- `不像参考图`
- `这里感觉不对`
- `不够高级`
- `太乱了`
- `太重了`
- `不像 Codex / WorkBuddy 那种感觉`

目标不是从审美词里猜完整重设计，而是把视觉反馈翻译成少量具体 UI 决策。

## 1. 固定读图顺序

不要从颜色开始。

按这个顺序读：

1. `surface`
2. `layout skeleton`
3. `visual center`
4. `module hierarchy`
5. `surface treatment`
6. `density`
7. `control language`
8. `component reuse`
9. `tone`

## 2. 读取维度

### 2A. Surface

先判断页面类型：

- `assistant home surface`
- `project workspace surface`
- `project dashboard surface`
- `settings surface`
- `library surface`
- `detail surface`
- `empty-state entry surface`

### 2B. Layout Skeleton

描述主结构：

- `single-column`
- `two-column`
- `three-column`
- `centered composition`
- `left-led composition`
- `split workspace`
- `sidebar + workspace`

好问题：

```text
这里要保持当前 sidebar + workspace 骨架，只调模块样式，对吗？
```

### 2C. Visual Center

识别页面视觉重心：

- `centered composer dominant`
- `list dominant`
- `card grid dominant`
- `detail panel dominant`
- `sidebar dominant`
- `utility controls dominant`

好问题：

```text
你想让视觉重心继续放在输入区，还是把内容区提得更高？
```

### 2D. Module Hierarchy

识别主次模块：

- `primary module`
- `secondary module`
- `supporting module`
- `background module`

如果多个模块抢同等注意力，说清：

- `hierarchy too flat`
- `hierarchy too scattered`

### 2E. Surface Treatment

描述模块框架方式：

- `flat`
- `light card`
- `heavy card`
- `panel-like`
- `overlay-like`
- `border-led`
- `fill-led`

好问题：

```text
这里更想要轻卡片感，还是更接近平面面板？
```

### 2F. Density

描述间距和扫描节奏：

- `compact`
- `balanced`
- `open`
- `scan-dense`
- `scan-loose`

好问题：

```text
这里的问题更像信息太松散，还是太挤？
```

### 2G. Control Language

描述控件语言：

- `rounded stronger`
- `rounded restrained`
- `border visible`
- `border quiet`
- `primary action loud`
- `primary action restrained`
- `input presence strong`
- `input presence quiet`

### 2H. Component Reuse

判断参考图中的控件是否能映射到当前项目组件：

- Button -> 项目 Button / 组件库 Button
- Input / Composer -> 项目输入组件 / 组件库 Input
- Tabs / Segmented -> 项目 tabs / 组件库 Tabs
- Dialog / Modal -> 项目 overlay / 组件库 Modal
- Card / Panel -> 项目 Card / 组件库 Card
- Badge / Status -> 项目 Badge / 组件库 Badge
- Dropdown / Menu -> 项目 Dropdown / 组件库 Menu

好问题：

```text
这个区域可以先复用现有 Card 和 Button，只调整密度和边框存在感。是否这样做？
```

### 2I. Tone

描述整体气质：

- `tool-like`
- `workbench-like`
- `editor-like`
- `dashboard-like`
- `promotional`
- `decorative`
- `calm`
- `sharp`
- `soft`

## 3. 使用对比轴，不停留在形容词

优先使用：

- `卡片感偏重 / 偏轻`
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

避免停在：

- `cleaner`
- `more advanced`
- `more modern`
- `nicer`
- `better looking`

## 4. 模糊反馈翻译

### 用户说：`不像参考图`

可能含义：

- 骨架不一致
- 层级不一致
- 卡片重量不一致
- 密度不一致
- 控件语言不一致

agent 跟进：

```text
我先不把它理解成颜色问题。更像是骨架、卡片重量和密度没有对齐参考方向。我先按这三项来复述。
```

### 用户说：`太丑了`

可能含义：

- 元素互相抢焦点
- 视觉重心不清
- spacing rhythm 断裂
- 组件语言不统一

agent 跟进：

```text
我先把它具体化：现在更像层级发散和模块语言不统一，不是单一颜色问题。你是希望先收紧层级，还是先减轻卡片和边框存在感？
```

### 用户说：`太重了`

可能含义：

- cards too heavy
- borders too dark
- fills too strong
- shadows too obvious

agent 跟进：

```text
这里我会优先理解成卡片感过重和边框存在感过强。你想把它收敛到轻卡片，还是更接近平面面板？
```

### 用户说：`太乱了`

可能含义：

- hierarchy too flat
- accents 太多
- spacing rhythm 不一致
- utility controls 抢内容焦点

agent 跟进：

```text
这里更像信息层级发散，不一定是模块太多。你想保留现有内容量，只把主次关系拉开，对吗？
```

### 用户说：`不够高级`

可能含义：

- 装饰感偏重
- 模板感偏重
- card framing 太明显
- spacing 和 alignment 不够克制

agent 跟进：

```text
我先把“不够高级”翻译成：模板感偏重、约束不够强、面板和控件语言不够克制。你更希望它往更安静的工具感走，对吗？
```

## 5. 当前截图和参考截图对比

同时有当前截图和参考截图时，只比较少量关键轴：

1. `skeleton`
2. `visual center`
3. `surface treatment`
4. `density`
5. `control language`
6. `component reuse`

示例：

```text
参考图阅读（Reference reading）:
- Skeleton: sidebar + workspace
- Visual center: centered composer dominant
- Surface treatment: light card with quiet borders
- Density: balanced, slightly compact
- Control language: restrained rounded controls

当前差异（Current mismatch）:
- Skeleton is close, but the visual center is weaker
- Card framing is heavier than the reference direction
- Spacing is looser, so the page scans less like a workbench
- Controls feel less unified than the reference
```

## 5A. 截图差异报告模板

用户同时提供当前 app 截图和参考截图时，改代码前必须返回：

```text
参考图阅读（Reference reading）:
- Surface:
- Skeleton:
- Visual center:
- Module hierarchy:
- Surface treatment:
- Density:
- Control language:
- Tone:

当前差异（Current mismatch）:
- Skeleton:
- Hierarchy:
- Surface treatment:
- Density:
- Control language:

可能原因（Likely cause）:
- [最小可能原因，例如 card weight、border presence、loose spacing、weak visual center、inconsistent controls]

组件复用（Component reuse）:
- Existing components:
- Library primitives:
- Need new wrapper:

推荐改法路径（Recommended adjustment paths）:
1. Conservative: keep the current skeleton and adjust only [surface / density / control language].
2. Medium: keep the main structure but rebalance [hierarchy / visual center / module grouping].
3. Strong: introduce a new local pattern only if the user approves it.

需要你确认（Need your decision on）:
1. [一个具体对比轴决策]
2. [一个具体对比轴决策]
```

默认推荐 conservative 或 medium。

只有当前骨架明显无法支持用户目标时，才建议 strong。

返回报告后必须停止，等待用户确认。

不要在第一次截图差异报告的同一轮里实现。

## 6. 截图到决策

提出实现前，把读图结果压缩成决策问题。

好模式：

```text
截图差异的主要问题不是功能结构，而是当前模块比参考方向更重、更松。
我建议保持当前骨架，减轻卡片重量，降低边框存在感，并收紧扫描节奏。
需要你确认（Need your decision on）:
1. stay light-card, or go flatter?
2. keep current density, or tighten it one step?
3. keep the input area secondary, or raise it visually?
```

坏模式：

```text
我理解了，我会让它更现代。
```

## 7. 硬规则

- 没检查结构和层级前，不要说截图问题主要是颜色。
- 能提供更窄的对比轴时，不要问开放式审美问题。
- 不要复述用户模糊形容词而不翻译成 UI issue。
- 不要从参考截图直接跳到实现。
- 不要把 `make it better`、`make it more modern`、`just follow the screenshot` 当成充分实现批准。
- 未确认 adjustment path、target module 和至少一个具体设计轴前，不允许实现。
- 未确认组件复用策略前，不要新增组件库或重写基础控件。
