# good-writing

把写作当作发展思想的方法，而不仅是表达已有思想的工具。

`good-writing` v2.0.0 是基于 Paul Graham [《Good Writing》（2025 年 5 月）](https://www.paulgraham.com/goodwriting.html) 重构的 Agent Skill。适合从笔记发展文章，或深度修改随笔、观点稿和技术解释。支持中英文，保留作者的语言、声音和任务约束。

## v1 审查与重构

v1 已正确识别原文的主要机制和真实性边界，但在落地时加入了过多固定流程：

| v1 的问题 | v2 的处理 |
| --- | --- |
| 要求先修推理，再修句子，把二者分成阶段 | 改为表达与思想往返迭代，允许局部改写带来新的理解 |
| 强制论证图、主张分类及独立研究审查模式 | 删除这些必经步骤，聚焦写作本身 |
| 改写探索偏向压缩 | 同时允许适度缩短、扩展和重组，按思想需要选择 |
| 对原文较强的判断有所弱化或遗漏 | 在原文论证图中补全，并区分作者主张与可安全执行的方法 |
| 部分示例加入未经提供的实验背景，或加强因果表达 | 以明确给定的材料为边界重写示例，不用顺畅表达填补未知事实 |
| 主指令、独立清单及参考重复 | 合并必要检查，保留两份按需阅读的参考 |

v2 不把这套方法命名为 Graham 的固定步骤。工作循环、交付约定和示例是本 Skill 的实现设计；原文论证与这些设计分别标注。

## 如何工作

先形成对文章意图的暂时理解，再从读起来不顺的地方追问含义，尝试小幅改写、扩展或重组。重新阅读时，同时检查思想是否更清楚、表达是否更自然。新措辞可能揭示重复思想、遗漏关系或更合适的论点；发现这些问题后继续修改相应段落，而不是强制跑完固定步骤。

简短不是独立目标，复杂句也不是缺点。只校对时只校对；深度改稿时，涉及主张或含义的重要变化会明确交代。

原文讨论的紧密联系有适用范围：写作本身参与思想的发展。对于实验、建造以及转述他人观点的文字，表达质量不能据此判定工作或观点的质量。即使在适用范围内，内部一致也不保证事实为真。本 Skill 保留这些边界，但不另设论文审查或事实调查流程。

## 安装

在 Codex 中调用内置安装技能，并明确用户级安装位置：

```text
使用 $skill-installer，从 https://github.com/ZepinLi/good-writing/tree/main/good-writing 安装到 ~/.agents/skills/good-writing。
```

也可以手动克隆并复制内部的技能目录。目标目录应尚不存在：

```bash
git clone https://github.com/ZepinLi/good-writing.git
mkdir -p ~/.agents/skills
cp -R good-writing/good-writing ~/.agents/skills/good-writing
```

当前用户级发现路径及目录结构见 [OpenAI 官方技能文档](https://learn.chatgpt.com/docs/build-skills)。安装后可在下一轮使用；如果没有出现，重启 Codex。其他支持 Agent Skills 格式的宿主可以使用内部 `good-writing/` 目录，安装位置由各宿主决定。

这是一次版本安装；修改本地仓库不会自动更新已安装副本。需要更新时，重新同步内部技能目录。此仓库不包含后台同步任务。

## 使用

```text
使用 $good-writing 深度修改下面这篇文章。让表达与思想一起改善，保留我的语气，并简述重要的含义变化。
```

```text
使用 $good-writing，把这些笔记发展成一篇短文。允许写作帮助发现更清楚的观点，不要补造事实。
```

技能保留按描述自动匹配的默认行为，也支持通过 `$good-writing` 显式调用。默认交付可直接使用的文本；只有必要时才补充简短的改动说明或未解决的问题，不要求展示完整分析过程。

## 文件结构

```text
good-writing/
├── README.md
└── good-writing/
    ├── SKILL.md
    └── references/
        ├── paul-graham-argument-map.md
        └── revision-examples.md
```

内部 `good-writing/` 是完整、可单独安装的技能，不依赖仓库根目录 README。

## 来源与归属

主要思想来源为 Paul Graham 的 [《Good Writing》](https://www.paulgraham.com/goodwriting.html)。[原文论证图](good-writing/references/paul-graham-argument-map.md) 区分原文的观察、类比、较强主张及本 Skill 的执行选择；[改写示例](good-writing/references/revision-examples.md) 全部为本 Skill 编写的虚构材料，不是原文摘录。

本仓库不收录原文全文，也不将其文字归为本项目的创作。
