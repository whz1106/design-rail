# TypeScript 和 React UI 实现规则

这些规则约束 UI 代码实现，防止视觉不一致变成代码不一致。

## 项目边界

应该：

- UI 工作保持在 renderer-facing UI layer
- 通过已有 service、wrapper、store、hook 和其他层通信
- 遵守项目已有 import 和文件组织方式
- 让页面组件作为 composition layer

不应该：

- 从展示组件直接伸到无关 process layer
- 在 presentation component 里复制 service access logic
- 为了快速完成把业务逻辑塞进 UI

## 组件库发现

实现前必须检查当前项目组件环境：

- `package.json` 中是否已有 UI 组件库
- 是否存在 `src/components/ui`
- 是否存在 `src/renderer/components/ui`
- 是否存在 `components/ui`
- 当前页面附近是否已有相似组件
- 是否已有 theme token、CSS variables 或 Tailwind theme

常见组件库包括但不限于：

- HeroUI
- shadcn/ui
- Radix UI
- Headless UI
- Ant Design
- MUI
- 内部 design system

不要假设必须使用某个组件库。以当前项目为准。

## 组件实现优先级

实现 UI 时按这个顺序：

1. 复用已有业务组件
2. 复用项目 `components/ui` 组件
3. 复用已安装组件库 primitives
4. 做轻量 wrapper，统一产品默认 props
5. 自定义组件

自定义组件只在没有合适 primitive 时使用。

新增 npm 组件库前必须先问用户，并说明：

- 为什么当前组件不够
- 是否会和现有视觉系统冲突
- 会新增哪些依赖
- 是否需要全局 provider、CSS 或 theme 配置

## 组件设计

应该：

- 组件只负责一个 module 或 reusable primitive
- 大 surface 拆成清晰子组件
- 重复模式提取为可复用组件
- reusable UI 使用明确 TypeScript props
- wrapper 只封装真实重复规则，不为一次性样式抽象

不应该：

- 一个复杂 surface 写成单个巨大组件
- 在 render body 里隐藏大量局部子组件
- 为纯局部视觉状态新增 global state
- 手写已有 Button、Input、Dialog、Tabs、Dropdown、Card

## 复用优先

创建新 UI 前检查：

- 是否有相似 layout pattern
- 是否有相似 row / card pattern
- 是否有 existing dialog / menu primitive
- 是否有 token 或 variable 支持 surface treatment
- 是否有组件库 primitive 可满足需求

如果已有模式足够接近，复用或扩展它。

不要因为局部更快就创造新视觉模式。

## 样式

应该：

- 使用已有 tokens、CSS variables 和附近 spacing grammar
- radius、border、surface color、typography 与邻近 surface 对齐
- 优先语义 token，而不是 raw hex
- 保持桌面窗口缩放行为
- 让组件库 props 和 theme token 共同驱动视觉

不应该：

- 有 semantic token 时仍写死 raw visual values
- 为一个 surface 添加无关 global CSS
- 创建不匹配可复用系统的一次性样式
- 在工具 surface 使用 oversized marketing typography

## 语义颜色

如果项目使用 HeroUI 风格语义色或等价 token 系统，按角色使用：

- `background`：基础画布
- `surface`：card、panel、modal
- `foreground`：主文本和 icon
- `accent`：主操作和强调
- `success`：成功状态
- `warning`：警告状态
- `danger`：破坏性动作和严重错误
- `field`：输入框和表单控件
- `separator`：分隔线和轻边框

规则：

- accent 少用
- neutral surfaces 占主导
- 通过 semantic tokens 表达 contrast 和 hierarchy
- 不为单个组件硬编码颜色
- 明暗主题通过同一语义角色保持一致

示例：

```tsx
<div className="bg-background text-foreground">
  <button className="bg-accent text-accent-foreground">Save</button>
</div>
```

## 状态和稳定性

应该：

- transient state 尽量局部
- 可直接派生的值在 render 中派生
- loading、selection、data refresh 期间布局稳定
- empty、loading、error、selected 状态明确设计

不应该：

- 为可直接派生的值加 effect
- 让 loading text 或 async state 导致不必要 layout shift
- 没理由地把状态逻辑散到多个 sibling components

## 交互和可访问性

应该：

- 使用 semantic interactive elements
- icon-only action 提供可理解名称
- 保留键盘行为
- focus 可见
- 状态和错误不能只靠颜色表达

不应该：

- 应该用 button/link 时使用 clickable container
- 删除 focus treatment 但不替换
- 把重要控制含义藏在装饰里

## 验证

完成 UI 实现前检查：

- TypeScript 是否编译
- 目标 module 是否在上下文中渲染
- 主控件是否更新真实 UI 状态
- 中英文长文本是否溢出
- empty、loading、error、selected 状态是否连贯
- 代码是否仍然遵守同一 UI 系统
- 是否复用了已有组件或明确说明无法复用

视觉质量优先通过用户截图 review，而不是默认要求 agent 跑浏览器自动化。

不把 Playwright 作为默认 UI review 机制。

如果用户提供更新截图，先对比确认的设计方向和参考图，再提出进一步修改。

如果没有更新截图，说明视觉验收 `pending user review`。
