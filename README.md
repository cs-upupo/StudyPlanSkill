# StudyPlanSkill

用真实任务把学习推进下去，而不是继续收藏教程。

**StudyPlanSkill** 是一组面向 Codex 的中文学习教练技能。它不默认生成宏大的学习路线，而是把学习目标压进真实项目、源码切片、功能任务、作品、题目或可交付物里，再推进一个 30-90 分钟的小闭环：练习、验收、失败反馈、证据复盘。

仓库地址：[https://github.com/cs-upupo/StudyPlanSkill/tree/main](https://github.com/cs-upupo/StudyPlanSkill/tree/main)

## 技能

| 技能 | 什么时候用 | 产出 |
| --- | --- | --- |
| `learning-coach` | 已经决定要学习某个技能，或可以先用合理假设推进 | 一个真实锚点、一个 30-90 分钟练习、验收标准和回来后记录字段 |
| `focus-coach` | 不知道先做什么、方向太多、优先级不清、学不动或需要复盘执行 | 一个主线选择、主要取舍、成功标准和 24-72 小时内的验证动作 |

一句话区分：

```text
想学会一个东西：用 learning-coach
不知道先做什么：用 focus-coach
```

## 核心原则

- 不默认生成完整学习大纲。
- 不用长资源清单制造“已经开始学习”的幻觉。
- 优先绑定真实项目、源码入口、作品、题目、工作任务或可交付物。
- 每次只推进一个 30-90 分钟闭环。
- 练习必须有可观察验收标准。
- 用户必须带回证据：输出、错误、卡点、解释、录音、代码、错题或作品片段。
- 没有证据时，只写“回来后记录”字段；用户带回证据后，才写正式学习记录。
- 多轨道工作区只用于整理长期学习现场，不是同时学很多东西的理由。

## 工作流

```text
学习目标
  -> 真实锚点
  -> 一个最小动作
  -> 验收标准
  -> 失败时反馈
  -> 用户带回证据
  -> 复盘真实卡点
  -> 下一轮学习
```

例子：

```text
用户：
我想学 React，别给我一堆路线。

输出：
结论：
你现在不缺路线，缺一个能暴露卡点的项目动作。

下一步：
今天只做一个 60 分钟闭环：在一个最小 React 项目里写一个带 props 和 state 的任务列表组件。

练习：
任务：实现一个可增删的学习任务列表。
验收标准：能新增、删除、标记完成，并解释 state 如何变化。
失败时反馈：把代码、报错和你卡住的步骤发回来。

回来后记录：
根据真实输出判断下一课补 JSX、props、state 还是事件处理。
```

## 安装

把需要的技能目录复制到 Codex 技能目录：

```bash
~/.codex/skills/learning-coach
~/.codex/skills/focus-coach
```

也可以从 GitHub 安装：

```text
帮我安装这个技能：
https://github.com/cs-upupo/StudyPlanSkill/tree/main/learning-coach
```

```text
帮我安装这个技能：
https://github.com/cs-upupo/StudyPlanSkill/tree/main/focus-coach
```

安装后重启 Codex，并这样使用：

```text
用 learning-coach 帮我把 React 学习变成一个今天能完成的小闭环。
用 focus-coach 帮我判断本周最值得投入的方向。
```

## 示例提示词

```text
我想学 TypeScript / React / AI Agent，但不想再看泛泛教程，帮我找一个小闭环。
```

```text
我收藏了很多英语口语教程，但一开口就卡。帮我安排一个 60 分钟练习。
```

```text
我准备考试，刷题很多但分数不上去。帮我诊断下一步该怎么复习。
```

```text
我刚照着教程完成了一个小项目，但离开教程就不会做。下一步怎么办？
```

```text
我同时想学英语、写作、AI、剪辑和产品分析，但每天时间很少。用 focus-coach 帮我选一个本周最该验证的方向。
```

更多示例：

- [learning-coach 示例提示词](examples/prompts.md)
- [learning-coach 样例输出](examples/sample-outputs.md)
- [focus-coach 示例提示词](examples/focus-coach-prompts.md)
- [focus-coach 样例输出](examples/focus-coach-sample-outputs.md)

## 学习工作区

长期学习时，可以把一个目录当作学习工作区。工作区不是资料仓库，而是保存使命、真实任务、练习证据和复盘判断的地方。

单主题工作区：

```text
learning-workspace/
  MISSION.md
  RESOURCES.md
  GLOSSARY.md
  NOTES.md
  lessons/
  exercises/
  reference/
  assets/
  learning-records/
```

多轨道工作区：

```text
learning-workspace/
  MISSION.md
  TRACKS.md
  tracks/<track>/
  lessons/<track>/
  exercises/<track>/
  reference/<track>/
  learning-records/<track>/
  assets/
  sources/
```

写入规则：

- 懒创建。只有真正改善后续学习判断时才创建文件或目录。
- 新轨道先保持最小可用：更新 `TRACKS.md`，必要时创建 `tracks/<track>/MISSION.md`。
- `STUDY-PLAN.md`、`RESOURCES.md`、`NOTES.md`、课程、练习和记录都按首次真实使用创建。
- 只有有证据的学习结果才进入 `learning-records/`。
- `sources/` 只登记外部来源，不把大型源码仓库、课程全文或不可公开资料复制进工作区。

核心格式：

- [WORKSPACE-FORMAT.md](learning-coach/WORKSPACE-FORMAT.md)
- [TRACKS-FORMAT.md](learning-coach/TRACKS-FORMAT.md)
- [MISSION-FORMAT.md](learning-coach/MISSION-FORMAT.md)
- [LEARNING-RECORD-FORMAT.md](learning-coach/LEARNING-RECORD-FORMAT.md)
- [GLOSSARY-FORMAT.md](learning-coach/GLOSSARY-FORMAT.md)
- [RESOURCES-FORMAT.md](learning-coach/RESOURCES-FORMAT.md)

示例工作区：[examples/workspaces/minimal-multitrack](examples/workspaces/minimal-multitrack)

## 输出标准

`learning-coach` 合格输出：

- 有明确结论和下一步动作。
- 有真实锚点，而不是抽象知识点。
- 有一个 30-90 分钟能完成的任务。
- 有可观察验收标准。
- 有失败时反馈方式。
- 有“回来后记录”字段。
- 不在用户带回证据前写正式学习记录。

`focus-coach` 合格输出：

- 明确当前最重要的判断、瓶颈或取舍。
- 区分事实、假设、推测和不确定项。
- 在多目标场景中收敛到一个主线。
- 给出 24-72 小时内可执行、可验证动作。
- 涉及法律、医疗、金融、心理危机、健康安全、重大职业选择等高风险场景时，不给确定性结论，不替代专业意见。

典型失败输出：

- “这是 12 周完整路线。”
- “推荐这些教程、书和视频。”
- “你需要更自律。”
- “看懂了就算掌握。”
- “下一节继续讲下一章。”
- 用户明确要求轻量回答或不要写文件时，仍强行输出完整闭环或修改工作区。

## 验证

基础校验：

```bash
python path/to/quick_validate.py learning-coach
python path/to/quick_validate.py focus-coach
```

人工验证：

- [evals/smoke-prompts.md](evals/smoke-prompts.md)
- [evals/learning-coach-smoke-prompts.md](evals/learning-coach-smoke-prompts.md)
- [evals/focus-coach-smoke-prompts.md](evals/focus-coach-smoke-prompts.md)
- [evals/rubric.md](evals/rubric.md)
- [evals/learning-coach-rubric.md](evals/learning-coach-rubric.md)
- [evals/focus-coach-rubric.md](evals/focus-coach-rubric.md)

## 致谢

本项目在 [ai-learning-coach](https://github.com/chrichuang218/ai-learning-coach) 的基础上进行了更为严谨的二次约束，重点收紧了技能分工、证据复盘、工作区懒创建和高风险场景边界。

感谢 [LINUX DO](https://linux.do/) 社区的支持与讨论。

## 许可证

MIT
