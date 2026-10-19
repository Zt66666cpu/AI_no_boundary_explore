# 赛道 B · 无界探索 —— 飞书《学习指导》正文（存档）

> 来源：<https://pcnuxhluoos7.feishu.cn/wiki/ZJsgwD38iiNgvGkioVocxBAjnGh>
> 上级页：《无界杯赛题学习指导和入门指南》 <https://pcnuxhluoos7.feishu.cn/wiki/NqfCwy9HSiZjxDkQiLwcdoHznWc>
> 抓取方式：真实浏览器渲染 + 内部滚动容器（`DIV.bear-web-x-container`）分步滚动触发懒加载｜抓取日期：2026-10-19
> 说明：文档共 6 节，已全部取到（01～06）。我们队伍只参加赛道 B，未抓 A（观行知意）/ C（慧眼巧手）的对应子页。

---

## B 无界探索 学习指导

### 01 · 赛题与学习路线

Agent · 任务规划 · 开放世界探索

B 题的主角是你设计的智能体。它从空背包出发，在仿真开放世界里采集资源、制作工具，逐步完成木制、石器和铁器任务。它需要看懂当前状态、决定下一步行动，也要发现刚才的行动有没有成功。

入门时，我们建议先观察一次「画面 → 动作 → 新画面」的过程。可以让 Coding Agent 帮你安装 MineDojo、运行官方示例，看看角色如何移动、环境如何返回画面。后面的短视频解释 Agent、工具和记忆等概念，进阶课会实现一个 Agent 循环；论文再把这些想法展开到任务规划、技能积累与开放世界探索。

赛道资源：赛题说明 PDF · Wiki Agent

### 02 · GitHub 与实践代码

**MineDojo 官方代码** → <https://github.com/MineDojo/MineDojo>

MineDojo 的官方示例会创建仿真环境，让角色向前移动和跳跃。可以用 Coding Agent 帮你跑起来，改改动作，观察画面变化。

注意，MineDojo 不支持 Windows 系统！但这不会阻碍我们学习的脚步，请参考以下内容，尝试跑通 MineDojo。

Windows：可以尝试 WSL2＋Ubuntu，在 Windows 中运行 Linux 环境。MineDojo 对 python 的版本有一定要求（见 MineDojo 的官方文档），推荐在 WSL2 安装一个 Miniconda 来管理隔离的 python 环境。

### 03 · 入门视频

| 视频 | 链接 | 说明 |
|---|---|---|
| 从 LLM 到 Agent Skill | <https://www.bilibili.com/video/BV1E7wtzaEdq/> | 马克的技术工作坊 · 介绍大语言模型、上下文、工具调用、MCP、Agent 与 Skill 之间的关系。 |
| Skill、MCP、RAG 与 Agent | <https://www.bilibili.com/video/BV1ojfDBSEPv/> | 飞天闪客 · 解释 Skill、MCP、RAG、Agent 和 OpenClaw 的基本概念与用途。 |

### 04 · 进阶课程

| 课程 | 链接 | 说明 |
|---|---|---|
| Agent 的概念、原理与构建模式 | <https://www.bilibili.com/video/BV1TSg7zuEqR/> | 马克的技术工作坊 · 结合简化版编程助手，讲解 ReAct 循环、工具调用以及计划与执行。 |
| Hugging Face 中文 Agent 课程 | （见文档内链） | 「思考、行动与观察」；配合「工具介绍」和「简单 Agent 实现」，阅读提示、调用与观察记录之间的衔接。 |

### 05 · 论文选读

**阅读方法（原文）**：

> 如何读论文 → <https://www.bilibili.com/video/BV1H44y1t75x/>（跟李沐学 AI · 介绍论文的阅读顺序，以及概览、理解方法和深入研读的不同读法。）
>
> 我们推荐按 **ReAct、Voyager、MineDojo** 的顺序了解：ReAct 的思考—行动—观察循环最贴近入门代码；Voyager 展示了技能如何积累和复用；MineDojo 则介绍本题所用环境背后的任务与资源。
>
> 第一次读论文可以从李沐的短视频开始，再看论文摘要、方法图和一段任务轨迹。把英文原文和图交给 AI，请它用中文讲清过程，并在官方代码里定位对应实现。带着「这一步为什么这样设计」去读，比逐句翻译更容易抓住方法。

**三篇论文条目**：

1. **ReAct｜思考、行动与观察**（推理、行动与观察）
   - 论文原图 · Figure 1 · PDF 第 2 页 ｜ 推理、行动与观测的交替过程
   - 说明：ReAct 将推理和行动交替展开：模型选择下一步，工具或环境返回观察，再继续决策。方法图和示例轨迹展示了反馈如何影响下一次行动。
   - 论文 PDF → <https://pcnuxhluoos7.feishu.cn/wiki/WJMlwNBPJi656HkDVqkc9HAknxc>

2. **Voyager｜技能积累与开放世界探索**（技能积累与环境探索）
   - 论文原图 · Figure 2 · PDF 第 2 页 ｜ 自动课程、技能库与迭代提示机制
   - 说明：Voyager 在开放世界中生成并执行代码，将成功行为保存为技能，再用于新的任务。关注技能库和迭代提示图，理解执行反馈、代码修正与技能复用。
   - 论文 PDF → <https://pcnuxhluoos7.feishu.cn/wiki/TgagwWvO6i4w53keLUWcTa8nnOb>
   - 项目 → <https://voyager.minedojo.org/>
   - 官方代码 → <https://github.com/MineDojo/Voyager>

3. **MineDojo｜环境、任务与知识**（环境、任务与知识）
   - 论文原图 · Figure 1 · PDF 第 2 页 ｜ 开放环境、智能体与互联网知识库
   - 说明：MineDojo 提供开放世界环境、任务与互联网知识资源。论文介绍任务类型和环境设计，可以结合官方示例理解观察、动作与仿真之间的数据往来。
   - 论文 PDF → <https://pcnuxhluoos7.feishu.cn/wiki/N1MEwSF37iulyjkSJiXc3i7knVc>
   - 项目 → <https://minedojo.org/>
   - 官方代码 → <https://github.com/MineDojo/MineDojo>

**读论文时给 AI 的提示词模板（原文）**：

> Prompt：
> 请结合这篇论文的方法图和相应正文，用中文解释输入、输出和各模块的作用。保留关键英文术语，公式中的符号请配一个小例子。标出解释对应的原文章节，并结合我提供的代码找到实现位置。

### 06 · 资料索引

- 赛题说明 PDF → <https://pcnuxhluoos7.feishu.cn/wiki/CCrywxMwciiPrxklufNcXltPn4g>
- ReAct · 思考、行动与观察 → <https://pcnuxhluoos7.feishu.cn/wiki/WJMlwNBPJi656HkDVqkc9HAknxc>
- Voyager · 技能积累 → <https://pcnuxhluoos7.feishu.cn/wiki/TgagwWvO6i4w53keLUWcTa8nnOb>
- MineDojo · 开放世界环境 → <https://pcnuxhluoos7.feishu.cn/wiki/N1MEwSF37iulyjkSJiXc3i7knVc>
- 返回学习指南 → <https://pcnuxhluoos7.feishu.cn/wiki/NqfCwy9HSiZjxDkQiLwcdoHznWc>

---

## 附：文档全部链接（原样）

| 文字 | URL |
|---|---|
| 赛题说明 PDF | https://pcnuxhluoos7.feishu.cn/wiki/CCrywxMwciiPrxklufNcXltPn4g |
| 从 LLM 到 Agent Skill | https://www.bilibili.com/video/BV1E7wtzaEdq/ |
| Skill、MCP、RAG 与 Agent | https://www.bilibili.com/video/BV1ojfDBSEPv/ |
| Agent 的概念、原理与构建模式 | https://www.bilibili.com/video/BV1TSg7zuEqR/ |
| 如何读论文 | https://www.bilibili.com/video/BV1H44y1t75x/ |
| ReAct 论文 PDF | https://pcnuxhluoos7.feishu.cn/wiki/WJMlwNBPJi656HkDVqkc9HAknxc |
| Voyager 论文 PDF | https://pcnuxhluoos7.feishu.cn/wiki/TgagwWvO6i4w53keLUWcTa8nnOb |
| Voyager 项目 | https://voyager.minedojo.org/ |
| Voyager 官方代码 | https://github.com/MineDojo/Voyager |
| MineDojo 论文 PDF | https://pcnuxhluoos7.feishu.cn/wiki/N1MEwSF37iulyjkSJiXc3i7knVc |
| MineDojo 项目 | https://minedojo.org/ |
| MineDojo 官方代码 | https://github.com/MineDojo/MineDojo |
| Wiki Agent | https://wiki.uestcai.top/zh/agent.html |
| 返回学习指南（上级页） | https://pcnuxhluoos7.feishu.cn/wiki/NqfCwy9HSiZjxDkQiLwcdoHznWc |

> 未取到：ReAct 条目的「项目或原文 / 官方代码」两个链接（页面渲染中未暴露）；04 节 Hugging Face 中文 Agent 课程的内链。飞书目录树显示「目录（暂无内容）」，无同级 A/C 学习指导节点暴露。
