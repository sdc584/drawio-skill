# drawio-template-pack

一个面向 OpenCode 的 `draw.io` 模板技能包，用来快速复用论文风黑白线框图模板，并统一配图风格。

## 包含内容

- `SKILL.md`：skill 定义与使用流程
- `Drawio图风格模板.md`：图种选择、元素作用、风格规则、改图建议
- `templates/`：8 类可直接复用的 `.drawio` 模板

## 模板列表

- `templates/总体架构图模板.drawio`
- `templates/功能结构图模板.drawio`
- `templates/功能模块划分图模板.drawio`
- `templates/数据库E-R图模板.drawio`
- `templates/用例图模板.drawio`
- `templates/状态流转图模板.drawio`
- `templates/业务时序图模板.drawio`
- `templates/页面结构图模板.drawio`

## 使用方式

1. 将整个目录放到 OpenCode 的 skills 目录下。
2. 通过 skill 名称 `drawio-template-pack` 调用。
3. 根据 `Drawio图风格模板.md` 选择模板。
4. 打开对应模板后，直接替换占位文字，按需复制或删除同类节点。

## 适用场景

- 论文插图风格统一
- 快速新建 `draw.io` 图
- 将已有图规范化到统一黑白线框风格
- 从用户描述中自动路由到合适模板
