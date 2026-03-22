# Draw.io 图风格模板

本模板基于现有图源整理，目标是让后续新图与项目中已有图保持同一套论文风、黑白线框风和版式习惯。

## 0. 快速使用

- 先判断图种，再从 `templates/` 中挑最近的一类模板，不建议从纯空白开始画。
- 打开模板后，优先直接替换占位文字；节点不够时复制同类节点，不要重新画一套新样式。
- 删除占位元素时，连同相关连线一起删，避免残留悬空箭头。
- 出图前统一检查：图种是否选对、元素语义是否正确、字号是否统一、连线风格是否统一、布局是否对齐。

## 0.1 模板速查

- `templates/总体架构图模板.drawio`：适合技术分层、部署层级、总体架构。
- `templates/功能结构图模板.drawio`：适合系统总功能树、模块分解。
- `templates/功能模块划分图模板.drawio`：适合按角色/职责横向分栏列功能。
- `templates/数据库E-R图模板.drawio`：适合实体、关系、属性建模。
- `templates/用例图模板.drawio`：适合角色与系统行为关系表达。
- `templates/状态流转图模板.drawio`：适合生命周期、审批单、订单状态变化。
- `templates/业务时序图模板.drawio`：适合用户-前端-后端-数据库交互过程。
- `templates/页面结构图模板.drawio`：适合页面树、信息架构、页面分组。

## 0.2 自动选模板决策

- 如果你要表达“系统有哪些层、各层有哪些组件、上下层怎么交互”，选 `templates/总体架构图模板.drawio`。
- 如果你要表达“系统功能从总到分怎么拆”，选 `templates/功能结构图模板.drawio`。
- 如果你要表达“不同角色/子系统分别负责哪些功能”，选 `templates/功能模块划分图模板.drawio`。
- 如果你要表达“实体、属性、关系”这类数据库概念模型，选 `templates/数据库E-R图模板.drawio`。
- 如果你要表达“谁可以使用哪些系统功能”，选 `templates/用例图模板.drawio`。
- 如果你要表达“一个对象会经历哪些状态变化”，选 `templates/状态流转图模板.drawio`。
- 如果你要表达“用户、前端、后端、数据库之间按时间顺序怎么交互”，选 `templates/业务时序图模板.drawio`。
- 如果你要表达“页面、页面分组、功能点的树形层级”，选 `templates/页面结构图模板.drawio`。

冲突时优先这样判断：

- 同时出现“角色”和“功能列表”，优先选“功能模块划分图模板”，不是“用例图模板”。
- 同时出现“流程”和“多个交互对象”，优先选“业务时序图模板”，不是“状态流转图模板”。
- 同时出现“页面”和“功能”，如果重点是层级关系，选“页面结构图模板”；如果重点是功能拆分，选“功能结构图模板”。

## 1. 统一风格基线

- 整体风格：黑白为主，白底黑边，不依赖彩色区分语义。
- 线条粗细：主体框优先 `strokeWidth=2`；E-R 图中的属性/关系线可降到 `1.2~1.5`。
- 形状偏好：以矩形、椭圆、菱形、圆柱、UML 标准图元为主，不用阴影、渐变、圆角装饰。
- 文字策略：中文为主，字号偏大，保证论文截图后仍清晰；普通结构图常用 `17~25`，E-R 图常用 `10~12`。
- 连线策略：同一张图内只保留一种主连线风格，避免同时混用过多折线、曲线和箭头类型。
- 对齐策略：强调横平竖直、模块等宽、层级分明、居中或等距排布。

## 2. 通用样式令牌

### 2.1 通用节点

```text
whiteSpace=wrap;html=1;strokeWidth=2;
```

适用：普通模块框、分组标题框、说明框。

### 2.2 左对齐说明块

```text
whiteSpace=wrap;html=1;strokeWidth=2;align=left;spacingLeft=10;
```

适用：功能列表、职责列表、分点说明框。

### 2.3 分层容器

```text
whiteSpace=wrap;strokeWidth=2;verticalAlign=top;
```

适用：总体架构图、网络拓扑图中的层级容器。

### 2.4 曲线无箭头连接

```text
curved=1;startArrow=none;endArrow=none;
```

适用：同层模块串联、页面结构关系、层内并列元素关系。

### 2.5 折线无箭头连接

```text
edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;startArrow=none;endArrow=none;
```

适用：功能结构图、树状分解图。

### 2.6 正交无箭头连接

```text
edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;startArrow=none;endArrow=none;
```

适用：大画布功能模块划分图、横向分区图。

### 2.7 实线消息箭头

```text
verticalAlign=bottom;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;endArrow=block;
```

适用：时序图中的请求、调用、提交动作。

### 2.8 虚线返回箭头

```text
verticalAlign=bottom;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;dashed=1;dashPattern=2 3;endArrow=block;
```

适用：时序图中的返回结果、反馈响应。

## 3. 各类图模板

说明：下面每一类都已经生成了对应的 `.drawio` 模板文件。模板文件保留了参考图的画布参数和页面设置，并预放了通用占位元素，打开后直接改字、增删节点即可复用。

通用使用方式：

- 先保留现有占位布局，只替换成你的真实模块名、角色名、状态名或页面名。
- 节点不够就直接复制同类节点，再修改文字，能更稳定保持统一样式。
- 删除不需要的占位元素时，连同关联连线一起删，避免残留悬空箭头。

## 3.1 总体架构图模板

参考文件：`图源文件/图4-1_系统总体架构图.drawio`、`图源文件参照/图4-2 系统网络拓扑图.drawio`

模板文件：`templates/总体架构图模板.drawio`

- 适用场景：章节总览、技术架构、部署层级、逻辑分层。
- 版式结构：自上而下分层，每层一个大容器，层内模块横向排布。
- 视觉关键词：分层、整齐、稳重、留白足。

建议结构：

```text
顶层标题/数据层
中间服务层/通信层
底层客户端/表现层
```

元素模板：

- 层容器：`whiteSpace=wrap;strokeWidth=2;verticalAlign=top;`
- 普通模块：`whiteSpace=wrap;strokeWidth=2;`
- 数据库：`shape=cylinder3;boundedLbl=1;backgroundOutline=1;size=10;strokeWidth=2;whiteSpace=wrap;`
- 层内连接：`curved=1;startArrow=none;endArrow=none;`
- 层间交互：`curved=1;startArrow=none;endArrow=block;`

元素作用：

- 层容器：表示一个技术层或逻辑层，是整张图的分层骨架。
- 普通模块：表示该层中的核心子模块、服务或组件。
- 数据库：表示持久化存储、主数据源或资源池。
- 层内连接：表示同层模块之间的协同或并列关系。
- 层间交互：表示跨层调用、数据传递或上下游关系。

落图规则：

- 每层不超过 3~5 个核心模块。
- 层标题置于容器上沿，容器内部保留统一边距。
- 如图内存在上下双向交互，使用成对箭头，不在同一根线上混合说明过多语义。

## 3.2 功能结构图模板

参考文件：`图源文件/图4-2_系统功能结构图.drawio`

模板文件：`templates/功能结构图模板.drawio`

- 适用场景：系统总功能分解、一级/二级功能树、章节 4 的功能总览。
- 版式结构：顶部一个系统总框，中间一排一级模块，下方接各自说明块。
- 视觉关键词：树状、对称、清晰、论文式大字号。

元素模板：

- 总框/一级模块：`whiteSpace=wrap;html=1;strokeWidth=2;fontSize=25;`
- 说明块：`whiteSpace=wrap;html=1;strokeWidth=2;fontSize=23;align=left;spacingLeft=10;`
- 连线：`edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;startArrow=none;endArrow=none;`

元素作用：

- 总框：表示整个系统或本章讨论对象。
- 一级模块：表示一级功能域或一级模块分类。
- 说明块：表示一级模块下的具体子功能列表。
- 连线：表示从属、分解或归类关系。

落图规则：

- 一级模块保持同宽、同高、等距。
- 说明块内部用换行列点，不使用项目符号图标。
- 连线统一走竖向折线，不要混入曲线。

## 3.3 功能模块划分图模板

参考文件：`图源文件/图4-4_系统功能模块划分图.drawio`

模板文件：`templates/功能模块划分图模板.drawio`

- 适用场景：按角色、按职责、按子系统对功能做大画布划分。
- 版式结构：顶部总框，下面横向并列多个角色区或模块区，再向下接说明块。
- 视觉关键词：横向分栏、结构平铺、清单式说明。

元素模板：

- 顶部总框：`whiteSpace=wrap;html=1;strokeWidth=2;fontSize=17;`
- 分区框：`whiteSpace=wrap;html=1;strokeWidth=2;fontSize=17;`
- 功能说明块：`whiteSpace=wrap;html=1;strokeWidth=2;fontSize=17;align=left;spacingLeft=10;`
- 连线：`edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;startArrow=none;endArrow=none;fontSize=17;`

元素作用：

- 顶部总框：表示整个系统或总功能主题。
- 分区框：表示角色、子系统或职责域。
- 功能说明块：表示该分区下承载的详细功能点。
- 连线：表示系统到分区、分区到功能的归属关系。

落图规则：

- 横向分区建议从左到右保持统一网格。
- 每个说明块的高度按条目数增减，但宽度尽量统一。
- 若画布很宽，优先扩宽页面，不要硬压缩字体。

## 3.4 数据库 E-R 图模板

参考文件：`图源文件/图4-3_系统数据库E-R图.drawio`

模板文件：`templates/数据库E-R图模板.drawio`

- 适用场景：概念模型、实体关系说明、数据库设计章节。
- 图种标准：采用 Chen 风格，不用 crow's foot 表结构风。
- 视觉关键词：图元语义明确、线细、字稳、无色彩干扰。

元素模板：

- 实体：`whiteSpace=wrap;html=1;rounded=0;strokeWidth=1.5;fontFamily=Noto Sans SC;fontSize=12;fontStyle=1;`
- 关系：`shape=rhombus;whiteSpace=wrap;html=1;strokeWidth=1.5;fontFamily=Noto Sans SC;fontSize=11;`
- 属性：`ellipse;whiteSpace=wrap;html=1;aspect=fixed;strokeWidth=1.2;fontFamily=Noto Sans SC;fontSize=10;`
- 连线：`endArrow=none;html=1;strokeWidth=1.2;`

元素作用：

- 实体：表示核心业务对象，如用户、订单、设备。
- 关系：表示两个或多个实体之间的业务联系。
- 属性：表示实体或关系的描述字段。
- 连线：表示属性属于哪个实体，或哪个实体参与了某个关系。

落图规则：

- 实体名加粗，属性名正常字重。
- 主键属性使用下划线表达，不额外加颜色或图标。
- 属性围绕实体放射排布，关系菱形置于实体之间。
- E-R 图字号单独成套，不与流程图的 17~25 号字体混用。

## 3.5 用例图模板

参考文件：`图源文件参照/图3-1(c) 管理端用例图.drawio`

模板文件：`templates/用例图模板.drawio`

- 适用场景：需求分析、角色职责、系统边界前的行为梳理。
- 版式结构：左侧演员，右侧纵向排列多个用例椭圆。
- 视觉关键词：UML 标准、朴素、列表式展开。

元素模板：

- 参与者：`shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;outlineConnect=0;strokeColor=#000000;`
- 用例：`ellipse;whiteSpace=wrap;html=1;fillColor=#ffffff;strokeColor=#000000;fontSize=12;`
- 连接：`endArrow=block;endFill=1;html=1;strokeWidth=1;strokeColor=#000000;`

元素作用：

- 参与者：表示系统外部的使用角色或外部系统。
- 用例：表示系统对外提供的一项功能或行为。
- 连接：表示某个参与者会发起、参与或使用该功能。

落图规则：

- 单角色用例图时，演员固定在左侧一列，用例垂直展开。
- 每个用例椭圆大小尽量一致，长文本优先靠增宽处理。
- 若未来需要 `include` / `extend`，建议单独补充标注，不要直接破坏当前简洁风格。

## 3.6 状态流转图模板

参考文件：`图源文件参照/图4-5 订单状态流转图.drawio`

模板文件：`templates/状态流转图模板.drawio`

- 适用场景：订单状态、审批状态、维修工单状态、生命周期说明。
- 版式结构：顶部起始点，下接首状态，再向左右或向下分支到后续状态。
- 视觉关键词：状态清单框、触发动作标签、路径清楚。

元素模板：

- 起始点：`ellipse;fillColor=strokeColor;`
- 状态框：`whiteSpace=wrap;strokeWidth=2;`
- 流转线：`curved=1;startArrow=none;`

元素作用：

- 起始点：表示业务流程或生命周期的开始。
- 状态框：表示系统在某一时刻的稳定状态。
- 流转线：表示状态之间的转换路径，线上的文字表示触发动作或条件。

落图规则：

- 状态框内建议固定 4 行：状态名称 / 状态码 / 可执行操作 / 操作角色。
- 连线标签写“触发动作”或“条件事件”，不要只写“流转”。
- 主路径优先垂直向下，取消、拒绝等分支可向侧边展开。

## 3.7 业务时序图模板

参考文件：`图源文件/图5-1_登录与权限控制流程图.drawio`、`图源文件/图5-2_预约冲突控制流程图.drawio`

模板文件：`templates/业务时序图模板.drawio`

- 适用场景：登录鉴权、预约创建、审批流、借还业务、接口交互说明。
- 版式结构：参与者从左到右，交互步骤从上到下。
- 视觉关键词：生命线、请求/返回区分、自调用处理步骤。

元素模板：

- 生命线：`shape=umlLifeline;perimeter=lifelinePerimeter;whiteSpace=wrap;container=1;dropTarget=0;collapsible=0;recursiveResize=0;outlineConnect=0;portConstraint=eastwest;newEdgeStyle={"edgeStyle":"elbowEdgeStyle","elbow":"vertical","curved":0,"rounded":0};size=65;fontSize=17;`
- 请求消息：`verticalAlign=bottom;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;endArrow=block;fontSize=17;`
- 返回消息：`verticalAlign=bottom;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;dashed=1;dashPattern=2 3;endArrow=block;fontSize=17;`
- 自调用：`curved=1;endArrow=block;fontSize=17;`

元素作用：

- 生命线：表示一个交互参与者，如用户、前端、后端、数据库。
- 请求消息：表示发起调用、提交请求或向下游发送命令。
- 返回消息：表示处理结果、响应数据或反馈信息。
- 自调用：表示同一参与者内部的连续处理步骤。

落图规则：

- 参与者命名优先写真实系统角色，如 `Web前端`、`ReservationService`、`MySQL数据库`。
- 请求动作写动词短句或接口名，返回消息写结果值、状态或提示。
- 同一层级的消息间距保持统一，避免局部过密。

## 3.8 页面结构图模板

参考文件：`图源文件参照/图5-4 小程序端页面结构图.drawio`

模板文件：`templates/页面结构图模板.drawio`

- 适用场景：小程序页面树、后台页面树、前端信息架构。
- 版式结构：最左为系统入口，中间为页面分组，右侧为具体页面，再右侧为页面内功能点。
- 视觉关键词：长树形、大画布、统一字号、分组清楚。

元素模板：

- 一级入口/分组/页面/功能点：`whiteSpace=wrap;strokeWidth=2;fontSize=18;`
- 连接：`curved=1;startArrow=none;endArrow=none;fontSize=18;`

元素作用：

- 一级入口：表示系统总入口或产品根节点。
- 页面分组：表示按角色、业务域或模块划分的页面集合。
- 页面节点：表示一个实际页面或页面模块。
- 功能点：表示页面内的关键操作、子区域或能力项。
- 连接：表示页面归属、跳转链路或树形层级关系。

落图规则：

- 页面树很长时，优先增加画布高度，不要把节点挤到过密。
- 分组层级固定，避免同一节点同时连到不同抽象层。
- 页名建议写“中文名(路由名)”格式，便于设计与开发对照。

## 4. 选型建议

- 讲技术分层：用“总体架构图模板”。
- 讲系统功能总览：用“功能结构图模板”。
- 讲角色职责和功能清单：用“功能模块划分图模板”。
- 讲数据库概念设计：用“数据库 E-R 图模板”。
- 讲需求角色行为：用“用例图模板”。
- 讲订单/审批/维修状态变化：用“状态流转图模板”。
- 讲接口交互过程：用“业务时序图模板”。
- 讲前端页面树：用“页面结构图模板”。

## 5. 建议的出图顺序

1. 先定图种，不要混画成“半架构、半流程”。
2. 先摆主骨架，再填文案，不要先写满文字再找位置。
3. 先统一节点样式，再复制扩展，避免后期手工逐个修。
4. 一张图内只保留一套字号层级和一套主连线风格。
5. 出图前统一检查：对齐、等宽、箭头方向、换行、术语一致性。

## 6. 当前已生成的模板文件

- `templates/总体架构图模板.drawio`
- `templates/功能结构图模板.drawio`
- `templates/功能模块划分图模板.drawio`
- `templates/数据库E-R图模板.drawio`
- `templates/用例图模板.drawio`
- `templates/状态流转图模板.drawio`
- `templates/业务时序图模板.drawio`
- `templates/页面结构图模板.drawio`

## 7. 快速改图建议

- 先只改名称，不急着改布局；确认信息层级没问题后再挪位置。
- 同类节点用复制法扩展，能最大限度保持线宽、字号、对齐一致。
- 一张图里如果已经采用折线，就不要再混入一批曲线；反之亦然。
- 文案尽量短句化，节点内优先 2~4 行，不要堆成长段文字。
- 页面不够大时优先扩画布，不要靠缩小字号硬塞。

## 8. 出图前最终检查

- 图种是否准确：是不是把时序图画成流程图、把状态图画成功能图。
- 元素语义是否准确：实体、关系、属性、参与者、生命线、状态框有没有混用。
- 样式是否统一：线宽、字号、边框、箭头样式有没有前后不一致。
- 布局是否稳定：是否横平竖直、等宽等距、留白合理。
- 文案是否精炼：是否还有口语化、过长、重复描述。
- 论文友好性是否达标：黑白打印后是否仍然清楚可辨。

## 7. 后续可继续补的内容

如果后面需要，我可以继续补一份“论文配图命名规范 + 图题规范”说明。
