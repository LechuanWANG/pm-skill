# UI 制作参考

用于制作、重构或评审 AI/SaaS 产品中的产品界面、页面、组件、交互状态和前端 polish。目标是让 UI 服务用户任务、产品结构和后续迭代。

## 目录

-   任务路由
-   产品界面原则
-   页面和流程
-   组件制作
-   文案和命名
-   可访问性和移动端
-   视觉 polish
-   验证清单

## 任务路由

先判断当前 UI 工作属于哪一类，只加载相关规则。

| 任务 | 主要关注 |
| --- | --- |
| 新页面、dashboard、settings、工作台 | 信息架构、布局模式、状态覆盖、响应式 |
| 表单、搜索、表格、列表、modal、导航 | 用户流程、错误处理、反馈位置、键盘操作 |
| 复用组件 | API、variant、size、状态模型、可访问性 |
| 视觉 polish | 层级、间距、对齐、圆角、阴影、触控、滚动、平台细节 |
| UI 文案 | 操作标签、错误、空状态、helper text、loading、success |
| UI 评审 | 任务完成度、状态缺口、可访问性、移动端、文案和视觉一致性 |

复杂 UI 制作按这个顺序推进：

```text
用户任务 -> 页面/流程结构 -> 组件和状态 -> 文案和反馈 -> 响应式和可访问性 -> 视觉 polish -> 浏览器验证
```

## 产品界面原则

-   先说明用户要完成的任务，再决定页面结构、组件和视觉层级。
-   每个主要界面都要有主操作、次操作、返回/取消路径和失败恢复路径。
-   信息密度匹配产品场景：dashboard 和运营工具偏紧凑，onboarding 和营销页偏舒展。
-   复杂功能使用渐进披露，把高级设置、批量操作和危险操作放到更明确的位置。
-   AI 输出区域要支持查看、编辑、接受、重试、纠正或回滚；用户要能理解 AI 当前状态。
-   重要反馈放在触发它的位置附近；表单错误、复制成功、保存失败优先做 inline feedback。

## 页面和流程

制作页面前先列出状态：

-   初始状态
-   loading 状态
-   empty 状态
-   error 状态
-   partial/分页状态
-   complete 状态
-   disabled/permission 状态
-   optimistic update 和 rollback 状态

常见模式：

-   表单：短表单 submit 时校验；中长表单 blur + submit；实时校验只用于密码强度、用户名可用性、字数限制等即时反馈字段。
-   表单错误：错误出现在字段下方，提交失败时滚动并聚焦到第一个错误字段，保留用户已输入内容。
-   表格：适合比较结构化数据。需要排序、筛选、结果数量、分页或加载更多，以及移动端策略。
-   列表：适合 feed、搜索结果、通知、消息。列表项结构保持一致，支持空、加载、错误、部分加载。
-   Modal：适合确认危险操作、短创建流程、快速预览。复杂多步流程使用页面或 route。
-   搜索：输入 debounce，支持清除、空结果、错误重试、键盘上下选择和 Enter 选中。

## 组件制作

共享组件要先定义契约，再写样式。

-   统一 prop 名称：`variant`、`size`、`disabled`、`loading`、`open`、`className`、`ref`。
-   多值维度使用 string union，例如 `size="sm" | "md" | "lg"`。
-   有限视觉差异用 variant；结构差异用 composition 或 compound components。
-   组件接受 `className`，合并现有样式工具，保留项目既有组件模式。
-   button 默认 `type="button"`，只有明确提交表单时使用 `type="submit"`。
-   图标继承 `currentColor`，同一产品界面使用同一套 icon 风格。

交互组件覆盖：

-   default
-   hover
-   focus
-   active/pressed
-   disabled
-   loading

数据组件覆盖：

-   empty
-   loading
-   error
-   partial
-   complete

loading 优先用贴近真实布局的 skeleton；通用 spinner 用于短暂、局部、结构难预测的等待。

## 文案和命名

-   操作标签要直接对应结果，例如 `Delete project`、`Save changes`、`Retry`。
-   错误文案说明发生了什么，以及用户下一步能做什么。
-   empty state 说明当前为什么为空，并给出自然的第一步操作。
-   helper text 用于提前减少错误，放在控件附近。
-   tooltip 用于解释低熟悉度图标或短约束；关键说明放在页面流程中。
-   AI 产品里的文案要区分系统状态、AI 思考/生成状态、用户可执行操作。

## 可访问性和移动端

-   所有 interactive element 可用 Tab 到达，焦点样式清晰可见。
-   icon-only button、link、toggle 有明确 `aria-label`。
-   表单 input 绑定 label，输入区域放在 `<form>` 中。
-   颜色只作为辅助状态提示，配合文字、图标、位置或形状。
-   文本对比度达到 WCAG 2.x AA；深浅色主题都要检查。
-   touch target 至少 44px；小图标按钮用 wrapper 或伪元素扩大点击区域。
-   移动端 input 字号至少 16px，保持 iOS Safari 输入时字号稳定。
-   hover 样式限定到支持 hover 的设备，触屏设备使用 active/focus 反馈。
-   固定在底部或边缘的移动端 UI 使用 safe-area inset。
-   动效尊重 `prefers-reduced-motion`。

## 视觉 polish

-   卡片、面板、工具栏和列表项使用稳定尺寸，hover、loading、错误状态保持布局稳定。
-   嵌套圆角保持视觉一致：外层圆角约等于内层圆角加间距。
-   图标按钮做光学校正，图标侧 padding 可以比文字侧少 2-4px。
-   文本容器限制宽度，正文控制在易读行长内；dashboard 内容可以更宽。
-   交互控件之间填满点击热区，减少列表、菜单、toast 中的空隙。
-   模态、抽屉、菜单关闭后焦点返回触发元素。
-   主题切换时处理 transition flash；SSR/CSR 项目处理 hydration flash。

## 验证清单

完成 UI 工作前做针对性验证：

-   桌面和移动端布局都能完成主流程。
-   文字完整显示，无遮挡，按钮标签长度可控。
-   loading、empty、error、disabled、permission 状态都有处理。
-   表单错误保留输入并能恢复。
-   键盘可操作主要控件和 modal。
-   图标按钮有可访问名称。
-   触屏交互稳定，输入字号和底部固定区域表现正常。
-   视觉 polish 覆盖对齐、圆角、间距、阴影和滚动稳定性。
-   使用浏览器截图或手动流程验证关键页面。
