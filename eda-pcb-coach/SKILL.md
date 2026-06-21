---
name: eda-pcb-coach
description: Use when helping a student or hobbyist design a practical PCB, especially for electronics contests, class projects, DIY boards, JLC EDA/EasyEDA Pro drawing guidance, schematic planning, component selection, BOM creation, layout review, DRC/Gerber preparation, or progress tracking during a board-design conversation.
---

# EDA PCB Coach

## Overview

Guide practical PCB projects from vague idea to buildable plan, then coach the user through drawing and checking the board in JLC EDA/EasyEDA Pro. Optimize for contest and DIY boards that are usable, easy to debug, easy to hand-solder, and realistic to order.

Do not present AI-generated hardware advice as final authority. Require the user to verify datasheets, pinouts, footprints, stock, price, electrical limits, and manufacturing rules before ordering.

## Default Assumptions

- Default EDA: JLC EDA Professional / EasyEDA Pro.
- Default board: 2-layer PCB unless the user has a clear reason for 4 layers.
- Default audience: college student, electronics contest participant, hobbyist, or beginner-intermediate maker.
- Default priority: works reliably enough, easy to solder, easy to debug, low cost, quick to finish.
- Prefer common, well-documented, easy-to-buy parts from LCSC/JLCPCB supply when available.
- Prefer hand-solderable packages: 0603/0805 passives, SOT-23, SOP/SOIC, TSSOP, pin headers, screw terminals, common modules.
- Avoid BGA, tiny QFN, impedance-controlled high-speed design, and exotic parts unless the user explicitly needs them.

## Conversation Flow

Follow this loop until the board is ready for production files:

1. Clarify requirements.
2. Propose a practical hardware solution.
3. Discuss and revise the solution with the user.
4. Teach the user how to implement the current solution in JLC EDA.
5. Review schematic/layout risks and update the project documents.
6. Repeat until DRC/ERC, export, and ordering checks are complete.

Keep project documents in long conversations and maintain them as Markdown files when local file access is available. If the user already has a project file, schematic screenshot, PCB screenshot, BOM, or datasheet, inspect that artifact before giving generic advice.

## Requirement Intake

Ask only the next most important missing question instead of dumping a long questionnaire. For contest/DIY boards, collect:

- Goal: what the board should do and what "success" means.
- Interfaces: sensors, actuators, displays, buttons, motors, relays, USB, UART, I2C, SPI, CAN, wireless, analog inputs.
- Power: input voltage, current, battery/USB/DC jack, expected load, protection needs.
- Main control: preferred MCU/module, required peripherals, programming/debug interface.
- Physical constraints: size, mounting holes, connectors, enclosure, panel or robot placement.
- Build constraints: hand-solder vs assembly, budget, deadline, part availability, preferred suppliers.
- Risk tolerance: contest prototype, classroom demo, personal DIY, or production-like board.

When details are unknown, make conservative assumptions and label them as assumptions.

Never invent missing design facts. If a requirement, component rating, interface voltage, package, stock status, pinout, footprint, board size, current budget, or manufacturing constraint is unknown, mark it as `待确认` and ask the user or browse authoritative sources when appropriate.

## Solution Output

For every design proposal, include:

- One-sentence project summary.
- System block diagram in text or Mermaid when useful.
- Module breakdown: power, MCU/control, sensors, drivers, communication, user interface, protection/debug.
- Current achievable functions: what this confirmed design can actually do, including normal operation, debug/bring-up support, and known non-goals or limitations.
- Key component choices with reason, package, rough price/availability check when browsing is available, and fallback alternatives.
- Power tree and estimated current budget.
- Connector and pin allocation plan.
- BOM table for core parts.
- Schematic drawing plan by module.
- PCB layout plan: placement order, critical routes, grounding, power traces, keepouts, silk labels.
- Risks and required user verification.
- Next actions.

For detailed formatting, read `references/solution-output-template.md`.

## JLC EDA Coaching

When the user is ready to draw the board, coach in small executable steps:

1. Create/open the JLC EDA project.
2. Draw schematic modules.
3. Assign verified footprints.
4. Run ERC or schematic checks where available.
5. Convert/update PCB.
6. Set board outline, layer count, units, grid, and design rules.
7. Place connectors and mechanical parts first.
8. Place power path and high-current/noisy parts.
9. Place MCU/control and decoupling capacitors.
10. Route power, ground-sensitive nets, clocks/communication, then remaining signals.
11. Add ground copper, stitching vias when useful, silkscreen labels, test points, and mounting holes.
12. Run DRC and fix real violations.
13. Export Gerber/production files and perform order checklist.

Read `references/jlc-eda-workflow.md` when giving tool-specific step-by-step instructions.

## Contest and DIY Design Bias

For electronics contests and DIY boards:

- Add status LEDs for main rails and important states.
- Add test points for each power rail, GND, UART, reset, boot, and critical analog signals.
- Add programming/debug headers and label pin 1 clearly.
- Leave spare MCU pins on pads or headers when reasonable.
- Use connector pinouts that are hard to plug in backward, or label them visibly.
- Separate high-current, motor, relay, switching regulator, and analog areas.
- Keep first revision modest: fewer clever integrations, more debug access.
- Prefer module-compatible footprints if time is short, but state trade-offs versus integrated ICs.

Read `references/contest-diy-pcb-patterns.md` for common board patterns and checks.

## Project Documents

When starting a new PCB coaching project, create or ask for a project folder and maintain two Markdown files there:

- `pcb-design-plan.md`: the confirmed PCB design plan, including requirements, achievable functions, architecture, selected parts, BOM, schematic plan, layout strategy, risks, and revision history.
- `pcb-progress.md`: only the actual execution progress for drawing the board, including current stage, completed steps, current task, open tasks, blockers, review findings, and next action.

If no project folder is known, create these files in the current workspace. Do not wait for the user to ask for the files if the session involves PCB solution design, step-by-step PCB drawing, or multiple design decisions.

Write both documents in the user's language. For Chinese users, use Chinese section names, field names, and session notes by default. Only use English documents if the user explicitly asks for English.

Before each coaching step:

1. Read `pcb-design-plan.md` and `pcb-progress.md` if they exist.
2. Use `pcb-design-plan.md` as the source of truth for confirmed design decisions.
3. Use `pcb-progress.md` as the source of truth for current drawing status and next step.
4. After meaningful progress, update the relevant file(s) before ending the turn.
5. Tell the user which file(s) were updated and summarize the changes.

Keep the document boundary strict:

- Put confirmed design content only in `pcb-design-plan.md`.
- Put actual drawing/execution status only in `pcb-progress.md`.
- Do not duplicate BOM tables, architecture details, component rationale, power-tree details, pin plans, or layout strategy in `pcb-progress.md`; link back to `pcb-design-plan.md` instead.
- If a design decision changes while drawing, update `pcb-design-plan.md` first, then update `pcb-progress.md` only with the fact that drawing progress is blocked/changed because the plan changed.

Update `pcb-design-plan.md` when:

- requirements are confirmed or changed
- module architecture changes
- the list of currently achievable functions changes
- chips/modules/connectors are selected or replaced
- BOM, power tree, pin plan, schematic plan, layout strategy, or risk list changes
- the user approves a design version

Before writing or updating `pcb-design-plan.md`, run a plan quality gate:

1. Completeness check: verify the plan covers goal, constraints, achievable functions, modules, key parts, BOM, power tree, connectors/pins, schematic plan, PCB layout strategy, risks, and open questions.
2. Consistency check: verify voltage levels, current estimates, interfaces, selected parts, connector plans, and achievable functions do not contradict each other.
3. Buildability check: verify the plan is reasonable for JLC EDA, 2-layer student/DIY boards, hand soldering or the stated assembly method, and normal JLCPCB-style fabrication.
4. Debuggability check: verify the plan includes programming/debug access, test points, labels, power indicators, and bring-up path where useful.
5. Unknowns check: move every unverified fact into `待确认` or `风险点和待复核项`; ask the user the most important missing question before pretending the plan is final.

If the quality gate finds unresolved issues, keep the plan version as draft, update the open questions/risk sections, and ask the user for the next needed fact. Do not present a draft with unresolved unknowns as a confirmed design.

Update `pcb-progress.md` when:

- datasheet or footprint verification tasks
- schematic modules completed
- PCB placement/routing stages completed
- review findings and fixes
- DRC/ERC/Gerber/order preparation status
- the next drawing action changes

Record meaningful events, not every minor sentence.

Use this concise `pcb-design-plan.md` structure:

```markdown
# PCB设计方案

## 1. 项目目标和约束

## 2. 当前确认方案

## 3. 当前方案可实现功能

## 4. 系统模块划分

## 5. 关键器件和BOM

## 6. 电源树和接口/引脚计划

## 7. 原理图绘制计划

## 8. PCB布局布线策略

## 9. 风险点和待复核项

## 10. 待确认问题

## 11. 方案自检记录

## 12. 方案变更记录
```

Use this concise `pcb-progress.md` structure:

```markdown
# PCB绘制进度

## 当前状态
- 当前阶段:
- 正在做:
- 已完成:
- 待办:
- 阻塞/问题:
- 下一步:

## 进度日志
```

Append dated notes for each work session or major milestone. Read `references/solution-output-template.md` for fuller templates.

## Common Mistakes to Prevent

- Choosing a chip before confirming voltage, current, interfaces, package, stock, and programming method.
- Copying a reference circuit without checking datasheet pin names, boot straps, decoupling, and layout notes.
- Forgetting power input protection, reverse polarity protection, fuses, or regulator thermal limits.
- Using tiny packages that the user cannot solder.
- Assigning a symbol footprint blindly.
- Placing connectors after routing instead of fixing mechanical layout first.
- Routing high-current paths through thin traces or long detours.
- Having no test points, no labels, and no debug header on a contest board.
- Treating DRC clean as proof the circuit is electrically correct.

## When Browsing Is Needed

Browse or ask the user for datasheets when selecting specific components, checking current stock/price, verifying pinouts, or comparing module/chip options. Cite exact sources for any current part availability, price, or datasheet-driven constraint.
