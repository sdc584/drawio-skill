---
name: drawio-template-pack
description: 基于论文风黑白线框风格的 draw.io 图模板技能：快速选模板、复用占位元素、统一图风与元素语义
---

## What I do

Help the user create, modify, or normalize draw.io diagrams by reusing bundled templates and following one consistent black-and-white thesis-style visual system.

## Bundled resources

- `@Drawio图风格模板.md` — 完整风格说明、元素作用、模板路径、出图规则。
- `@templates/总体架构图模板.drawio`
- `@templates/功能结构图模板.drawio`
- `@templates/功能模块划分图模板.drawio`
- `@templates/数据库E-R图模板.drawio`
- `@templates/用例图模板.drawio`
- `@templates/状态流转图模板.drawio`
- `@templates/业务时序图模板.drawio`
- `@templates/页面结构图模板.drawio`

## When to use me

Use when the user wants to:

- 新建或修改 `draw.io` / `.drawio` 图
- 根据既有论文配图风格统一新图
- 从模板快速出总体架构图、功能图、E-R 图、用例图、状态图、时序图、页面结构图
- 给现有图补齐元素语义、版式规则、模板说明

## Process

1. **Identify the diagram type first**
   - 先判断用户要画的是哪一类图，不要把架构图、流程图、时序图混成一个图种。
   - 若用户描述含糊，优先根据目标表达内容来归类：讲分层就选架构图，讲交互顺序就选时序图，讲状态变化就选状态图。

2. **Pick the nearest bundled template**
   - 优先复用 `@templates/` 下最接近的模板，不从纯空白画布起稿。
   - 选择后说明为什么选这个模板，以及哪些占位元素需要替换。

3. **Reuse placeholders instead of redrawing**
   - 保留模板现有节点样式，直接替换占位文本。
   - 节点不够时，复制同类节点后再改字；不要新画风格不一致的图元。
   - 删除节点时，连同相关连线一起删除，避免悬空箭头。

4. **Keep the visual system stable**
   - 维持黑白线框、白底黑边、大字号论文风。
   - 同一张图只保留一套主连线风格和一套字号层级。
   - 保持横平竖直、等宽等距、分层清楚，不额外引入阴影、渐变、图标化装饰。

5. **Use the guide for semantic correctness**
   - 遇到“这个元素表示什么”或“这类图该怎么摆”的问题，查 `@Drawio图风格模板.md`。
   - 明确告诉用户：参与者、用例、实体、关系、属性、生命线、状态框、页面节点等分别承担什么语义。

6. **Polish before finishing**
   - 完成后检查：图种是否选对、元素是否同类同样式、箭头方向是否一致、文案是否简洁、布局是否对齐。
   - 如果这次产出了可重复复用的新结构，应同步更新模板或说明文档，而不只是改当前单张图。

## Auto template routing

When the user does not explicitly name a template, select automatically using the following decision rules:

1. **If the user is describing layers, deployment, or overall technical composition**
   - Keywords: `总体架构`、`系统架构`、`技术架构`、`分层`、`部署`、`客户端/服务端/数据库`
   - Choose: `@templates/总体架构图模板.drawio`

2. **If the user is decomposing system functions from top to bottom**
   - Keywords: `功能结构`、`功能树`、`模块分解`、`一级功能`、`二级功能`
   - Choose: `@templates/功能结构图模板.drawio`

3. **If the user is grouping functions by role, subsystem, or responsibility in columns**
   - Keywords: `模块划分`、`角色功能`、`职责划分`、`按角色分类`、`横向分栏`
   - Choose: `@templates/功能模块划分图模板.drawio`

4. **If the user is modeling business objects, attributes, and relationships**
   - Keywords: `E-R图`、`实体关系`、`数据库设计`、`实体`、`属性`、`关系`
   - Choose: `@templates/数据库E-R图模板.drawio`

5. **If the user is expressing actor-to-function relationships**
   - Keywords: `用例图`、`角色行为`、`参与者`、`系统功能关系`
   - Choose: `@templates/用例图模板.drawio`

6. **If the user is expressing lifecycle changes or state transitions**
   - Keywords: `状态流转`、`生命周期`、`订单状态`、`审批状态`、`工单状态`
   - Choose: `@templates/状态流转图模板.drawio`

7. **If the user is expressing interaction order over time across multiple participants**
   - Keywords: `时序图`、`交互过程`、`调用链`、`请求响应`、`前端后端数据库`
   - Choose: `@templates/业务时序图模板.drawio`

8. **If the user is expressing page hierarchy, navigation, or information architecture**
   - Keywords: `页面结构`、`页面树`、`信息架构`、`页面分组`、`小程序页面`
   - Choose: `@templates/页面结构图模板.drawio`

## Tie-break rules

- If the description includes both `角色` and `功能列表`, prefer `功能模块划分图模板` over `用例图模板`.
- If the description includes both `流程` and `交互对象`, prefer `业务时序图模板` over `状态流转图模板`.
- If the description includes both `状态` and `动作`, ask whether the user wants to show `状态变化` or `参与者交互`; default to `状态流转图模板` when the focus is lifecycle.
- If the description includes both `页面` and `功能`, prefer `页面结构图模板` when the focus is hierarchy; prefer `功能结构图模板` when the focus is capabilities.
- If no template is a perfect match, choose the nearest one by structure first, then adjust labels and node count without changing the overall visual grammar.

## Template selection map

- `@templates/总体架构图模板.drawio` — 技术分层、部署层级、系统总体结构
- `@templates/功能结构图模板.drawio` — 系统总功能树、一级/二级功能分解
- `@templates/功能模块划分图模板.drawio` — 按角色或职责分栏的功能清单图
- `@templates/数据库E-R图模板.drawio` — Chen 风格实体关系图
- `@templates/用例图模板.drawio` — 角色与系统行为关系图
- `@templates/状态流转图模板.drawio` — 生命周期、审批/订单/工单状态变化
- `@templates/业务时序图模板.drawio` — 用户、前端、后端、数据库之间的交互时序
- `@templates/页面结构图模板.drawio` — 页面树、信息架构、前端页面层级

## Output expectations

When using this skill, provide:

- 选中的模板文件路径
- 为什么选这个模板
- 主要替换了哪些占位元素
- 是否新增/删除了哪些节点与连线
- 当前图是否仍符合统一风格

## Rules

- Prefer editing a bundled template over drawing from scratch.
- Keep diagram labels concise and mostly in Chinese unless the project already uses English technical labels.
- Preserve template page settings unless the content volume clearly requires resizing.
- For E-R diagrams, keep Chen notation and do not silently switch to crow's foot.
- For sequence diagrams, distinguish request arrows and response arrows clearly.
- If no exact template matches, choose the nearest one and state the adjustment strategy.
