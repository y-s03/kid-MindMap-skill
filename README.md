# kid-MindMap-skill

将一个主题、零散思路或资料整理成简洁、清晰的思维导图。Skill 会先确认**视觉样式**和**导图类型**，再组织内容、绘制图片并检查排版。

这个 Skill 由本人和 ChatGPT 共同打造：本人负责提供导图模板、确定视觉风格与审美方向，ChatGPT 协助整理规则并实现。当前 Skill 仍在持续完善中。

## 可选样式与类型

视觉样式可选黑白无填充、柔和灰蓝、对应类型的示例图风格、内容自适应，也可以自定义配色和节点外观。内容自适应会根据文章主题选择有意义的图标与协调的颜色；用户指定的样式始终优先。

| 导图类型 | 适合表达 | 示例图片 |
| --- | --- | --- |
| 右向树状 | 从中心主题逐层展开的知识结构；默认推荐 | [查看](references/images/rightward-tree-example.png) |
| 左右平衡 | 从中心向两侧展开的分类与头脑风暴 | [查看](references/images/balanced-example.png) |
| 中心放射 | 围绕主题向四周发散的想法 | [查看](references/images/radial-example.png) |
| 组织结构图 | 部门、岗位或其他隶属层级 | [查看](references/images/org-chart-example.png) |
| 鱼骨图 | 问题的原因或对策 | [查看](references/images/fishbone-example.png) |
| 时间轴 | 按时间或阶段排列的事件 | [查看](references/images/timeline-grayblue-approved.png) |
| 许可流程图 | 带判断、分支和回退的申请或审批流程 | [查看](references/images/permit-flow-example.png) |
| 环形图 | 围绕主题的多个环节或循环关系 | [查看](references/images/ring-example.png) |
| 设计流程图 | 从目标分解到阶段、方法和具体任务 | [查看](references/images/design-flow-example.png) |

视觉样式和导图类型可以组合使用。新图只询问尚未确定的选项；修改同一张图时沿用已经确认的选择。选择“自动匹配”时，Skill 会先分析文章表达的关系；如果现有模板都不合适，会自行设计清晰的导图结构。

## 使用示例

在已加载此 Skill 的环境中输入：

> 使用 `$kid-MindMap-skill`，以“人工智能发展历程”为主题制作思维导图。

选择“柔和灰蓝＋时间轴”后，Skill 会按时间整理代表事件，制作并检查 PNG 图片；条件允许时也会保留可编辑的 SVG。

如果希望根据文章自动决定外观与结构，可以选择“内容自适应＋自动匹配”。Skill 会先判断九种模板是否适合文章；需要新的表达方式时，自行设计布局，并用内容相关的图标与配色辅助阅读。

## 导图类型示例

以下九张图片分别演示一种导图结构。示例内容仅用于说明布局；制作新图时，会根据主题和所选视觉样式重新绘制。

### 右向树状

![右向树状思维导图示例：健康生活](references/images/rightward-tree-example.png)

### 左右平衡

![左右平衡思维导图示例：旅行计划](references/images/balanced-example.png)

### 中心放射

![中心放射思维导图示例：个人成长](references/images/radial-example.png)

### 组织结构图

![组织结构图示例：项目团队](references/images/org-chart-example.png)

### 鱼骨图

![鱼骨图示例：项目延期](references/images/fishbone-example.png)

### 时间轴

![时间轴思维导图示例：人工智能发展历程](references/images/timeline-grayblue-approved.png)

### 许可流程图

![许可流程图示例：活动场地使用申请](references/images/permit-flow-example.png)

### 环形图

![环形图示例：社区阅读活动](references/images/ring-example.png)

### 设计流程图

![设计流程图示例：校园导览系统设计](references/images/design-flow-example.png)

## 文件结构

```text
.
├─ README.md                        仓库介绍与使用示例
├─ SKILL.md                         核心工作流程与默认样式
├─ agents/openai.yaml               显示名称与默认提示词
└─ references/
   ├─ diagram-types.md              各导图类型的布局规则
   └─ images/                       九种导图类型的 PNG 示例
```

`SKILL.md` 是技能入口；其他文件提供界面信息和按需读取的参考样式。[OpenAI 官方 Skill 文档](https://learn.chatgpt.com/docs/build-skills)说明了 Skill 的加载位置与调用方式。

> **兼容性提示：**当前保留了原定名称 `kid-MindMap-skill`。部分 Skill 校验器要求 `name` 只使用小写字母、数字和连字符；在这些环境中安装前，需将 `SKILL.md` 中的名称及 `agents/openai.yaml` 里的调用名统一改为 `kid-mindmap-skill`。
