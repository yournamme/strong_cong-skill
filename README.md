# strong_cong-skill

这里收录我自己常用的 Skills。每个 Skill 都使用独立文件夹保存，可以按需单独安装。

希望对大家能有所帮助。

## Skill 目录

| 名称 | 一句话介绍 | 详情与下载 |
| --- | --- | --- |
| [eda-pcb-coach](./eda-pcb-coach) | 面向电子竞赛、课程项目和 DIY 的 PCB 设计陪练，支持从零设计或已有板改版，覆盖方案讨论、嘉立创 EDA 绘制、检查、打板与文档追踪。 | [查看 Skill](https://github.com/yournamme/strong_cong-skill/tree/main/eda-pcb-coach) |
| [laicong-writer](./laicong-writer) | 赖聪个人写作风格与共情型内容创作 Skill，把零散想法整理成真诚、有温度、又保留个人味道的中文表达。 | [查看 Skill](https://github.com/yournamme/strong_cong-skill/tree/main/laicong-writer) |
| [planning-with-doc](./planning-with-doc) | 用一份 `开发任务拆解.md` 串起方案讨论、任务拆解、执行追踪和变更记录，适合多轮 AI 协同开发项目。 | [查看 Skill](https://github.com/yournamme/strong_cong-skill/tree/main/planning-with-doc) |
| [dev-idea-selector](./dev-idea-selector) | 开发副业选题路由：从 Obsidian 全库（钱/知识/健康/时间/内容生产）按实用价值筛出 3-5 个开发候选，你拍板后交给 vibe_coding 去开发。 | [查看 Skill](https://github.com/yournamme/strong_cong-skill/tree/main/dev-idea-selector) |
| [article-to-video](./article-to-video) | 图文转视频：把一篇公众号文章自动转成短视频制作四件套（口播稿、UI卡片、分镜+生图提示词、拍摄包）。 | [查看 Skill](https://github.com/yournamme/strong_cong-skill/tree/main/article-to-video) |

## eda-pcb-coach

`eda-pcb-coach` 是一个面向学生、电子竞赛参与者和硬件爱好者的 PCB 设计陪练 Skill。它不会只丢给你一张电路图，而是会根据你的目标、接口、电源、尺寸、预算和焊接能力，逐步整理出能实际落地的方案，并指导你在嘉立创 EDA 专业版（EasyEDA Pro）中完成原理图和 PCB。

无论你是从零开始做一块新板，还是要基于已有原理图、PCB、BOM 或开源参考板做改版，它都会先确认基线和改动范围；方案会以便于讨论的草案形式持续迭代，而不是一开始就把未经核实的内容当成定稿。

### 它能做什么？

- 把模糊的项目想法整理成可执行的 PCB 设计需求。
- 区分“从零设计”和“已有板改版”：改版时围绕具体器件、网络或封装列出变更与影响，不把整块板重新推导一遍。
- 规划电源、主控、传感器、驱动、通信、保护和调试模块。
- 辅助选择常用、易采购、适合手焊的器件，并生成核心 BOM。
- 给出电源树、接口与引脚分配、原理图绘制顺序和布局布线策略。
- 分步骤指导嘉立创 EDA 专业版的原理图、封装、PCB、铺铜、ERC/DRC 和 Gerber 导出。
- 按完整模块讲解绘制与检查流程，方便在每一轮方案讨论后继续推进，而不会被零碎步骤打断。
- 针对竞赛和 DIY 板增加测试点、状态灯、下载调试口、丝印和首版调试建议。
- 在长对话中维护 `pcb-design-plan.md` 和 `pcb-progress.md`，记录已确认方案与实际绘制进度。

> AI 给出的硬件方案只能作为设计辅助。打板前请以器件数据手册、封装尺寸、引脚定义、电气额定值和板厂规则为准，并自行复核。

### 如何使用

安装后，可以直接对 Agent 说：

```text
请使用 eda-pcb-coach，帮我设计一块用于电子竞赛的 PCB。先了解我的需求，再给出方案，并一步一步教我在嘉立创 EDA 专业版里画出来。
```

也可以针对已有项目使用：

```text
请使用 eda-pcb-coach，检查我的原理图截图、PCB 截图和 BOM，找出供电、封装、布局布线和可调试性方面的问题。
```

如果工具支持 `$skill-name` 语法，也可以写：

```text
使用 $eda-pcb-coach 帮我规划并绘制一块 STM32 传感器采集板。
```

## laicong-writer

`laicong-writer` 是一个面向中文个人表达的写作陪伴 Skill。它适合把日常笔记、QQ/朋友圈/空间动态、自媒体草稿、学习反思、成长计划、关系感受和 AI 工具学习心得，整理成更好读、更有共鸣、但依然像“赖聪”本人会写出来的版本。

它不会把文字磨成千篇一律的鸡汤或标准作文，而是会尽量保留原文里有生命力的口语、调侃和不那么完美的真实感，再补上场景、情绪线索、读者共鸣和一个能落地的小行动。

### 它能做什么？

- 把零散的念头、聊天片段和随手记录，扩写成完整但不生硬的中文内容。
- 润色 QQ 空间、朋友圈、视频文案与自媒体草稿，让表达更有共情和可读性。
- 整理学习反思、执行计划、AI 工具学习记录与成长笔记，理清主线但不过度“写作文”。
- 把个人经历变成能让相似处境的人感到被理解的分享，并给出一个小而可执行的落点。
- 在保留“啊、嗯、那个、man、哈哈哈哈”等个人语言质感的前提下，减少碎片感和重复表达。

### 如何使用

安装后，可以直接对 Agent 说：

```text
请使用 laicong-writer，帮我把这段零散的学习反思整理成一篇适合发 QQ 空间的文字。结构清楚一点，但保留我原来的味道，也希望能帮到遇到类似问题的人。
```

也可以给它更具体的场景：

```text
使用 laicong-writer，按我的风格把下面这段关于拖延和刷手机的碎片想法扩写成一篇自媒体文案。不要太鸡汤，先写出我真实卡住的感觉，最后给一个今天就能做的小动作。
```

如果工具支持 `$skill-name` 语法，也可以写：

```text
用 $laicong-writer 帮我把这些碎片整理成一篇更共情、结构更顺、但还是像我自己的分享。
```

## planning-with-doc

`planning-with-doc` 是一套面向项目开发的文档化协作 Skill，尤其适合电子信息工程比赛、课程项目，以及需要多个 AI agent 分阶段协作的开发过程。它把方案讨论、任务拆解、执行日志、变更记录和异常处理都收敛到同一份 `开发任务拆解.md` 里，让新会话接手时能直接回溯项目发生过什么、做到哪一步。

### 它能做什么？

- 把模糊想法收敛成够用、能落地的 MVP 方案。
- 根据项目规模选择简单模式或完整任务拆解模式，避免过度拆分。
- 把任务写到新会话/新 agent 可以直接接手执行的详细程度。
- 用 🤖/🔍/🤝/🧑 标注任务执行者和检查点，区分 AI 可连续推进、需要用户确认、需要用户配合和必须用户亲自完成的节点。
- 在同一份 `开发任务拆解.md` 中追加执行日志、变更日志和异常记录，保留完整历史。

四个任务标记的含义：

| 标记 | 含义 | 执行方式 |
| --- | --- | --- |
| 🤖 | AI 独立完成，风险低 | AI 自查/自测通过后记录日志，可以继续下一个任务 |
| 🔍 | AI 独立完成，但这是关键检查点 | AI 做完后必须汇报验收结果，建议等用户确认后再继续 |
| 🤝 | 需要用户配合或验证 | AI 先完成能做的部分，再停下来让用户提供信息、实测结果或决策 |
| 🧑 | 用户亲自完成 | AI 只能给步骤、清单和检查标准，不能替用户完成，例如采购、接线、烧录、实机操作 |

### 如何使用

安装后，可以直接对 Agent 说：

```text
请使用 planning-with-doc，帮我把这个课程项目先讨论成一个可落地方案，再拆成开发任务，并生成一份开发任务拆解.md。
```

也可以针对已有项目继续推进：

```text
使用 planning-with-doc，读取我项目里的开发任务拆解.md，看看现在做到哪一步了，然后从最早的未完成任务继续。
```

如果工具支持 `$skill-name` 语法，也可以写：

```text
用 $planning-with-doc 帮我维护这个项目的开发任务拆解.md，不要额外开 progress 文件。
```

## dev-idea-selector

`dev-idea-selector` 是一个"开发副业选题路由"Skill。它解决的不是"怎么开发"，而是"**该开发什么**"。很多用 AI 搞开发的人卡在第一步：网上看别人做的小工具、小游戏、硬件项目，感觉"很容易做、又有用"，但轮到自己想一个就想不出来。这个 Skill 把"凭感觉想选题"变成"AI 按标准筛选题"。

它的第一标准是**实用价值**：解决一个真实存在的小麻烦，省时间、省钱、帮你做判断。内容势能是第二位的，只是顺带好处。它特别适合两条线互相喂的场景：AI 开发产出实用工具，开发过程本身变成自媒体内容，内容的反馈又变回下一个开发灵感。这个 Skill 负责整条线最前面的"选"这一环。

### 它能做什么？

- 从四个灵感源采集候选：Obsidian 素材池（最优先）、自己反复遇到的麻烦、市场已验证的需求品类、自媒体内容反馈。
- 用三条过滤线筛选题：是否解决一个真实的小麻烦、是否 1-2 周能出 MVP、是否有实用价值（能省时间/省钱/帮做判断）。三把都中才进候选；能变内容是可选的加分项，不再是硬性要求。
- 结合用户底子（嵌入式、单片机、电赛、硬件、AI agent）做匹配加分。
- 产出 3-5 个统一格式的开发候选（做什么/给谁用/解决什么麻烦/ MVP 多大/实际怎么用/能变成内容吗/怎么算有价值），让用户拍板。
- 持续维护一份 `开发选题池.md`（像自媒体的选题池一样，按系列分组、标状态、拍过的划掉），候选没被选中的保留待定，以后还能捡回来。

### 如何使用

安装后，可以直接对 Agent 说：

```text
请使用 dev-idea-selector，帮我挖开发灵感，筛出 3-5 个候选给我选。
```

也可以先丢想法再筛：

```text
使用 dev-idea-selector，这是我手头几个想法，帮我按三条过滤线选哪个先做。
```

如果工具支持 `$skill-name` 语法，也可以写：

```text
用 $dev-idea-selector 帮我选下一个该开发什么。
```

拍板之后，把选中的选题交给 `planning-with-doc`（方案讨论→任务拆解→开发）或 vibe_coding 工作流继续，完成后再把成品/过程变回内容，闭环回到灵感源。

## article-to-video

`article-to-video` 是一个"图文转视频"内容生产 Skill。它把公众号图文和短视频当成同一套素材的两种切法：**视频给故事+卡片，图文给细节+清单**。把一篇公众号文章丢进去，它会按你验证过的 4 步转化法，产出可直接开工的短视频四件套——口播稿、UI 卡片、分镜+生图提示词、拍摄包。

它不会帮你录音、剪映或发布，那些仍是人肉环节；它把最耗脑的"从文章到脚本"这一跳自动化，让文章变成视频的第一步不再是开一个空白文档。

### 它能做什么？

- 从一篇公众号文章里只抽一个"一句话能讲痛"的问题，一条视频只救一个问题。
- 按钩子→共情→3 要点→金句的四段式结构生成 ≤220 字口播稿，分段带字数预算（钩子≤30 / 共情≤40 / 要点合计≤90 / 金句≤25），并标注每段实际字数。
- 把每个要点凝成 ≤15 字的 UI 卡片文案，优先复用原文小标题。
- 生成 5-6 个分镜 + 即梦/生图提示词（竖屏 9:16、浅色纯色背景、上方留白、无文字），内置角色锚点图机制保证多张图人物形象统一。
- 输出带双链占位和时间线模板的拍摄包骨架（生图 → 录音 → 剪映 → 发布）。
- 觉得稿子浅时自动走"内容深化三层"（为什么/规律/观众能带走什么）补深度，红线是不堆方法论名词。

### 如何使用

安装后，可以直接对 Agent 说：

```text
请使用 article-to-video，把这篇公众号文章转成一条 B 站竖屏短视频的四件套。
```

粘贴文章全文后，它会按流程产出口播稿、UI 卡片、分镜提示词和拍摄包；如果文章里有多个可讲的问题，它会列出来让你挑一个，不自行合并。

如果工具支持 `$skill-name` 语法，也可以写：

```text
用 $article-to-video 把这篇笔记变成口播稿和分镜。
```

## 安装方式

### 方式一：让 Agent 自动安装

把下面这句话直接发给支持 Skill 的 Agent：

```text
帮我安装这个 skill：https://github.com/yournamme/strong_cong-skill/tree/main/laicong-writer
```

将链接中的 `laicong-writer` 替换成目录中任一 Skill 名称，即可安装对应 Skill。

### 方式二：手动安装

先克隆仓库：

```bash
git clone --depth 1 https://github.com/yournamme/strong_cong-skill.git
```

然后把需要的 Skill 整个文件夹复制到所用 Agent 的 Skills 目录。不要只复制 `SKILL.md`，因为部分 Skill 还包含 `agents/` 和 `references/` 等配套文件。

常见目录：

| 工具 | Skills 目录 |
| --- | --- |
| Codex | `~/.codex/skills/` |
| Claude Code | `~/.claude/skills/` |
| 通用 Agent Skills | `~/.agents/skills/` |

Windows PowerShell（以 Codex 为例）：

```powershell
New-Item -ItemType Directory -Force "$HOME\.codex\skills" | Out-Null
Copy-Item -Recurse -Force ".\strong_cong-skill\laicong-writer" "$HOME\.codex\skills\laicong-writer"
```

macOS / Linux（以 Codex 为例）：

```bash
mkdir -p ~/.codex/skills
cp -R ./strong_cong-skill/laicong-writer ~/.codex/skills/laicong-writer
```

安装完成后，重新打开 Agent 会话，再在提示词中调用对应 Skill。

## 目录结构

```text
strong_cong-skill/
├── eda-pcb-coach/
│   ├── SKILL.md
│   ├── agents/
│   │   └── openai.yaml
│   └── references/
│       ├── contest-diy-pcb-patterns.md
│       ├── jlc-eda-workflow.md
│       └── solution-output-template.md
├── laicong-writer/
│   ├── SKILL.md
│   ├── agents/
│   │   └── openai.yaml
│   └── references/
│       ├── examples.md
│       └── style-profile.md
├── planning-with-doc/
│   ├── SKILL.md
│   ├── agents/
│   │   └── openai.yaml
│   └── references/
│       └── task-doc-template.md
├── dev-idea-selector/
│   ├── SKILL.md
│   ├── agents/
│   │   └── openai.yaml
│   └── assets/
│       └── selection-pool-template.md
├── article-to-video/
│   └── SKILL.md
├── LICENSE
└── README.md
```

## License

本仓库使用 [MIT License](./LICENSE)。
