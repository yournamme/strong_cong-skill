# strong_cong-skill

这里收录我自己常用的 Skills。每个 Skill 都使用独立文件夹保存，可以按需单独安装。
希望对大家能有所帮助.

## Skill 目录

| 名称 | 一句话介绍 | 详情与下载 |
| --- | --- | --- |
| [eda-pcb-coach](./eda-pcb-coach) | 面向电子竞赛、课程项目和 DIY 的 PCB 设计教练，帮助你从想法梳理到嘉立创 EDA 绘制、检查和打板。 | [查看 Skill](https://github.com/yournamme/strong_cong-skill/tree/main/eda-pcb-coach) |

## eda-pcb-coach

`eda-pcb-coach` 是一个面向学生、电子竞赛参与者和硬件爱好者的 PCB 设计陪练 Skill。它不会只丢给你一张电路图，而是会根据你的目标、接口、电源、尺寸、预算和焊接能力，逐步整理出能实际落地的方案，并指导你在嘉立创 EDA 专业版（EasyEDA Pro）中完成原理图和 PCB。

### 它能做什么

- 把模糊的项目想法整理成可执行的 PCB 设计需求。
- 规划电源、主控、传感器、驱动、通信、保护和调试模块。
- 辅助选择常用、易采购、适合手焊的器件，并生成核心 BOM。
- 给出电源树、接口与引脚分配、原理图绘制顺序和布局布线策略。
- 分步骤指导嘉立创 EDA 专业版的原理图、封装、PCB、铺铜、ERC/DRC 和 Gerber 导出。
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

## 安装方式

### 方式一：让 Agent 自动安装

把下面这句话直接发给支持 Skill 的 Agent：

```text
帮我安装这个 skill：https://github.com/yournamme/strong_cong-skill/tree/main/eda-pcb-coach
```

### 方式二：手动安装

先克隆仓库：

```bash
git clone --depth 1 https://github.com/yournamme/strong_cong-skill.git
```

然后把 `eda-pcb-coach` 整个文件夹复制到所用 Agent 的 Skills 目录。不要只复制 `SKILL.md`，因为该 Skill 还包含 `agents/` 和 `references/`。

常见目录：

| 工具 | Skills 目录 |
| --- | --- |
| Codex | `~/.codex/skills/` |
| Claude Code | `~/.claude/skills/` |
| 通用 Agent Skills | `~/.agents/skills/` |

Windows PowerShell（以 Codex 为例）：

```powershell
New-Item -ItemType Directory -Force "$HOME\.codex\skills" | Out-Null
Copy-Item -Recurse -Force ".\strong_cong-skill\eda-pcb-coach" "$HOME\.codex\skills\eda-pcb-coach"
```

macOS / Linux（以 Codex 为例）：

```bash
mkdir -p ~/.codex/skills
cp -R ./strong_cong-skill/eda-pcb-coach ~/.codex/skills/eda-pcb-coach
```

安装完成后，重新打开 Agent 会话，再在提示词中调用 `eda-pcb-coach`。

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
├── LICENSE
└── README.md
```

## License

本仓库使用 [MIT License](./LICENSE)。
