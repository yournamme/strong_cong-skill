# Solution and Progress Templates

Use these templates when the user asks for a PCB plan, BOM, schematic guidance, layout guidance, or progress tracking.

For a **new design**, always put the "Quick Overview Block" immediately before "Practical PCB Solution" in the same message. For a **board modification**, use "Board Modification Output" instead of regenerating "Practical PCB Solution" from scratch.

## Quick Overview Block (方案速览) — New Design Only

Always the first thing in the message, before any detailed section. Keep it short enough to read in a few seconds.

```markdown
## 方案速览
- 项目:
- 一句话总结:
- 板子大小(估算):
- 层数:
- 供电方式:
- 用到的核心方案:
  -
- 能实现的功能:
  -
- 暂不支持:
  -
- 关键假设/权衡:
  -
- 这版本建议你重点检查的点:
  -
- 版本: vN
```

## Practical PCB Solution

```markdown
# PCB方案 vN

## 1. 目标
- 用途:
- 成功标准:
- 默认假设:

## 2. 系统框图
Use a simple Mermaid block when helpful, for example:
    flowchart LR
      A[Power Input] --> B[Regulator]
      B --> C[MCU]
      C --> D[Sensor/Driver/Interface]

## 3. 模块划分
| 模块 | 功能 | 建议方案 | 注意点 |
|---|---|---|---|
| 电源 | | | |
| 主控 | | | |
| 接口 | | | |
| 调试 | | | |

## 4. 当前方案可实现功能
### 正常使用功能
- 

### 调试/维护功能
- 

### 暂不支持/边界限制
- 

## 5. 关键器件选型
| 器件 | 推荐型号 | 封装 | 用途 | 选择理由 | 替代方案 | 必须复核 |
|---|---|---|---|---|---|---|

## 6. 电源树和电流估算
| 电源轨 | 来源 | 负载 | 估算电流 | 风险 |
|---|---|---|---|---|

## 7. 连接器和引脚计划
| 接口 | 引脚 | 信号 | 电压 | 备注 |
|---|---|---|---|---|

## 8. 原理图绘制顺序
1. 
2. 
3. 

## 9. PCB布局布线策略
- 板框/安装:
- 接口位置:
- 电源区:
- 主控区:
- 噪声/大电流区:
- 测试点:
- 丝印:

## 10. 风险和复核项
- Datasheet:
- 封装:
- 库存/价格:
- 电源/热:
- 可焊性:
- 下单规则:

## 11. 待确认问题
| 问题 | 为什么需要确认 | 确认方式 |
|---|---|---|

## 12. 方案自检记录
| 检查项 | 结果 | 备注 |
|---|---|---|
| 完整性 | | |
| 一致性 | | |
| 可制造/可焊接 | | |
| 可调试性 | | |
| 未确认项处理 | | |

## 13. 下一步
```

## Board Modification Output (基于现有板卡修改)

Use this instead of "Practical PCB Solution" whenever the user is modifying an existing board (their own prior revision, an open-source reference design, a dev board). Lead with what changed; do not re-derive the whole board.

```markdown
# 板卡改动方案 vN

## 改动速览
- 基线来源: (板子名称/仓库链接/版本, 依据的资料: 原理图文件/PDF/照片/BOM)
- 本次改动目标:
- 改动影响范围: 原理图 / 布局 / BOM / 功能 / 尺寸 (标出实际涉及哪些)

## 改动详情
| 编号 | 位置/模块(具体到位号/网络/连接器) | 原方案 | 改为 | 原因 | 影响范围 | 需要复核 |
|---:|---|---|---|---|---|---|

## 其余部分保持原样
-

## 本次改动的风险和复核项
-

## 待确认问题
| 问题 | 为什么需要确认 | 确认方式 |
|---|---|---|

## 下一步
```

Rules for filling this in:

- "位置/模块" must name the exact reference designator, net name, connector, or footprint — never a vague area like "电源部分" or "接口那里".
- Only expand a full block diagram / full BOM / full layout section when the change is broad enough to need it (e.g., swapping the MCU family). For a localized change (e.g., swap one regulator, add one connector, widen one trace), the change table plus "其余部分保持原样" is the whole deliverable.
- If the user hasn't provided the baseline artifact yet (schematic, PDF, photo, repo link, or existing `pcb-design-plan.md`), ask for it before producing this output — do not guess at an unseen board's current state.

## Discussion Round Update (本轮讨论更新)

Use this from the second round onward, whenever the user pushes back on a draft (new design or board modification) that isn't confirmed yet. Do not re-output the full solution — this compact update is the whole deliverable for that round.

```markdown
## 本轮讨论更新
- 你的问题/关注点:
- 结论:
- 改动:
| 位置/模块 | 原方案 | 改为 | 原因 | 影响 |
|---|---|---|---|---|
- 方案速览/改动速览是否需要更新: (若有字段变化，把更新后的完整速览块重新贴一遍；否则写"无变化")
```

Switch back to a full "New Design Output" or "Board Modification Output" only when the user asks for the whole thing restated, when the diff has grown large enough that it's harder to read than a fresh version, or when the user approves the draft as a confirmed version.

## BOM Template

```markdown
| 序号 | 类型 | 型号/规格 | 封装 | 数量 | 用途 | 推荐来源 | 替代料 | 备注 |
|---:|---|---|---|---:|---|---|---|---|
| 1 | MCU | | | 1 | | | | |
```

## Project Documents

### `pcb-design-plan.md`

```markdown
# PCB设计方案

## 1. 项目目标和约束
- 用途:
- 成功标准:
- 默认假设:
- 尺寸/安装约束:
- 预算/工期:
- 制作方式:
- 基线来源(仅基于现有板卡修改时填写: 板子/仓库名称、版本、依据资料):

## 2. 当前确认方案
- 当前版本:
- 方案摘要:
- 已确认决定:
- 暂未采用的方案:

## 3. 当前方案可实现功能
### 正常使用功能
- 

### 调试/维护功能
- 

### 暂不支持/边界限制
- 

## 4. 系统模块划分
| 模块 | 功能 | 方案 | 注意点 |
|---|---|---|---|

## 5. 关键器件和BOM
| 序号 | 类型 | 型号/规格 | 封装 | 数量 | 用途 | 推荐来源 | 替代料 | 必须复核 |
|---:|---|---|---|---:|---|---|---|---|

## 6. 电源树和接口/引脚计划
| 项目 | 来源/连接 | 电压/电流 | 说明 | 风险 |
|---|---|---|---|---|

## 7. 原理图绘制计划
1.
2.
3.

## 8. PCB布局布线策略
- 板框/安装:
- 接口位置:
- 电源区:
- 主控区:
- 噪声/大电流区:
- 测试点:
- 丝印:

## 9. 风险点和待复核项
- Datasheet:
- 封装:
- 库存/价格:
- 电源/热:
- 可焊性:
- 下单规则:

## 10. 待确认问题
| 问题 | 为什么需要确认 | 确认方式 |
|---|---|---|

## 11. 方案自检记录
| 检查项 | 结果 | 备注 |
|---|---|---|
| 完整性 | | |
| 一致性 | | |
| 可制造/可焊接 | | |
| 可调试性 | | |
| 未确认项处理 | | |

## 12. 方案变更记录
> 基于现有板卡修改的项目，优先用下面的改动表记录每次变更，而不是整段文字重写；新设计项目的重大版本变化可以用简短的文字条目。

| 日期 | 位置/模块 | 原方案 | 改为 | 原因 | 影响范围 |
|---|---|---|---|---|---|
```

### `pcb-progress.md`

```markdown
# PCB绘制进度

> 只记录实际画板/执行进度。设计方案、BOM、芯片选型、电源树、接口定义等内容写到 `pcb-design-plan.md`。

## 当前状态
- 当前阶段:
- 正在做:
- 已完成:
- 待办:
- 阻塞/问题:
- 下一步:

## 进度日志

### YYYY-MM-DD HH:MM
- 本次完成:
- 当前问题:
- 下一步动作:
```

## Review Response Template

When reviewing a schematic or PCB screenshot/file, use:

```markdown
## 评审摘要
- 当前状态:
- 最大风险:
- 是否可以继续:

## 必须修
| 项目 | 为什么重要 | 怎么改 |
|---|---|---|

## 建议优化
| 项目 | 收益 | 建议改法 |
|---|---|---|

## 看起来没问题
- 

## 下一步检查
```

## Bring-Up Checklist

```markdown
## 首次上电检查
1. 检查焊接和器件方向。
2. 上电前测每路电源到GND的阻值。
3. 尽量用限流电源上电。
4. 确认输入电源正常。
5. 确认稳压输出正常。
6. 检查电源指示灯。
7. 连接或烧录MCU。
8. 按模块逐个测试。
9. 记录故障和飞线/改板点。
```
