# Game Development Skills Collection

A comprehensive set of **11 professional-grade Codex skills** designed to streamline game design, balancing, systems planning, level creation, narrative development, and technical implementation.  
Each skill is a self‑contained module that guides Codex through a structured, evidence‑based workflow—producing ready‑to‑use artifacts such as GDDs, balance tables, level designs, architecture documents, and more.

## 📦 What’s Included

| Skill | Primary Purpose | Typical Output |
|-------|----------------|----------------|
| **game-design-doc** | Create full Game Design Documents (GDDs) | Structured Markdown GDD (vision, pillars, loops, systems, features, monetization, risks) |
| **game-system-design** | Design specific game systems (combat, economy, progression, social…) | System spec, core loops, feedback mechanisms, integration matrix |
| **level-design** | Layout single levels, maps, or missions | Textual description, ASCII map, pacing/difficulty curves, enemy/loot placement |
| **narrative-design** | Craft stories, characters, dialogue, characters, dialogue, and world‑building | Story bible, character profiles, dialogue scripts, plot flowcharts, environmental storytelling notes |
| **game-balance** | Tune numbers via modeling & probability | Formulas, spreadsheets, simulation results, balancing recommendations |
| **game-economy** | Design sustainable in‑game economies & monetization | Source/sink charts, conversion rates, pricing models, inflation/deflation controls |
| **probability-model** | Build loot‑drop, gacha, crit, and other random models | Probability distributions, EV/variance calculations, simulation scripts |
| **data-table-generator** | Generate CSV/Excel tables for items, enemies, abilities, and world‑building | Story bible, character profiles, dialogue scripts, plot flowcharts, environmental storytelling notes |
| **game-balance** | Tune numbers via modeling & probability | Formulas, spreadsheets, simulation results, balancing recommendations |
| **game-economy** | Design sustainable in‑game economies & monetization | Source/sink charts, conversion rates, pricing models, inflation/deflation controls |
| **probability-model** | Build loot‑drop, gacha, crit, and other random models | Probability distributions, EV/variance calculations, simulation scripts |
| **data-table-generator** | Generate CSV/Excel tables for items, enemies, abilities, quests | Ready‑to‑import data files with scaling curves, variance controls, formulas |
| **game-dev-arch** | Define technical architecture (ECS vs OOP, networking, rendering, moddability) | Architecture diagrams, tech decisions, integration guides |
| **game-feature-impl** | Turn designs into implementation plans | Feature breakdown, implementation steps, API contracts, code scaffolding/pseudocode |
| **game-performance** | Optimize CPU/GPU, memory, draw calls, frame‑rate | Profiling guide, optimization techniques, performance budgets |

> **Note:** Each skill also includes a suggested scripts/, eferences/, and ssets/ directory layout (with example file names) so you can easily add reusable tools, templates, and reference material later.

## 🛠️ How to Use

1. **Place the skill folders** inside your Codex skills directory (default: ~/.codex/skills/ or your workspace’s skill/ folder).  
   Example structure after installation:

   `
   skills/
   ├─ game-design-doc/
   │  ├─ SKILL.md
   │  └─ agents/
   │     └─ openai.yaml
   ├─ game-balance/
   │  ├─ SKILL.md
   │  └─ agents/
   │     └─ openai.yaml
   └─ … (10 more skills)
   `

2. **Invoke a skill** in a Codex conversation:  

   `
   Use -design-doc to create a GDD for a sci‑fi RPG with three core pillars.
   `

   Codex will load the skill, ask clarifying questions if needed, and emit a structured deliverable (usually Markdown).

3. **Iterate** – Provide feedback or ask for a specific section (e.g., “expand the monetization model”) and the skill will continue from where it left off.

4. **Add your own resources** – Populate the optional scripts/, eferences/, and ssets/ sub‑folders with helpers, templates, or domain‑specific data to make the skill even more powerful for your team.

## 📖 Skill Structure (SKILL.md)

Every SKILL.md follows a consistent, professional template:

- **YAML Frontmatter** – 
ame and rich description (the trigger for Codex).  
- **# Title** – Human‑readable skill name.  
- **Philosophy** – Guiding principles and methodological stance.  
- **Core Workflow** – 5‑step standardized process:  
  1. Input Gathering  
  2. Domain Analysis  
  3. Structured Design  
  4. Output Synthesis  
  5. Validation Check  
- **Detailed Guidance** – Input expectations, step‑by‑step procedure, decision points, quality criteria, common pitfalls.  
- **Output Format** – Primary format (structured Markdown) plus optional alternatives (CSV/Excel, Mermaid diagrams, JSON schemas, pseudocode).  
- **Resources (optional)** – Example files for scripts/, eferences/, ssets/; delete unused sections.

This structure ensures that **any Codex instance (or compatible AI agent)** can understand when to call the skill, what it does, and how to steer it toward high‑quality results.

## 🧩 Extending & Customizing

- **Add helper scripts** – Place Python/Bash/etc. files in scripts/ and reference them in the “Detailed Guidance” or “Resources” section.  
- **Store reference material** – Design patterns, GDD outlines, monetization model tables, etc., go in eferences/.  
- **Include templates** – Word/Google‑Doc templates, icon sets, HTML skeletons, etc., belong in ssets/.  
- **Adjust UI metadata** – Edit gents/openai.yaml to change the display name, short description, brand color, or default prompt if you want a different presentation in the Codex skill picker.

## 🚀 Getting Started

Clone or copy this repository into your Codex skills location:

`ash
# From the root of your Codex workspace (or ~/.codex/skills/)
git clone https://github.com/your-username/game-dev-skills.git skills
# Or simply copy the folders:
cp -r path/to/this/repo/* ~/.codex/skills/
`

After copying, restart or reload Codex (if needed) so it discovers the new skills. You’re ready to go!

## 📄 Example Sessions

### Creating a GDD

> **You**: Use -design-doc to draft a GDD for a mobile puzzle‑match‑3 game with a “short session, deep mastery” pillar.  
> **Codex**: Asks about target audience, platform, core loop preferences → outputs a markdown GDD with executive summary, pillars, core loop table, system interaction matrix, feature backlog (P0/P1/P2), monetization sketch, risk log, etc.

### Balancing a Combat System

> **You**: Use -balance to balance damage values for a swords‑vs‑sorcerers combat system.  
> **Codex**: Requests current stats, desired time‑to‑kill, enemy health curves → produces a spreadsheet‑style table with formulas, scaling curves, and a short explanation of the balancing methodology.

### Designing a Dungeon Level

> **You**: Use -design to layout a three‑encounter dungeon for a fantasy roguelike.  
> **Codex**: Asks about theme, difficulty curve, player power level → returns a textual room‑by‑room description, ASCII map, enemy placement notes, loot distribution, and pacing suggestions.

## 🙌 Contributing

Feel free to fork this repository, add new skills (e.g., monetization-design, live-ops-planning, ui-ux-guidelines), improve existing ones, or submit issue reports and pull requests.  
When adding a new skill, please follow the same SKILL.md + gents/openai.yaml structure and keep the language actionable, concise, and professional.

## 📜 License

This collection is released under the **MIT License** – you are free to use, modify, and distribute the skills in both personal and commercial projects. See the included LICENSE file for details.

---

# 游戏开发技能合集（中文版）

一套 **11 个专业级 Codex 技能**，专门针对游戏策划、数值策划、系统设计、关卡设计、叙事设计、技术架构、功能实现和性能优化等全链路需求而设计。每个技能都是自包含的模块，引导 Codex 按照结构化、证据驱动的工作流程进行操作，产出可直接用于项目的成果文档（如 GDD、平衡表、关卡设计、架构图等）。

## 📦 包含的技能

| 技能名称 | 主要用途 | 常见输出 |
|----------|----------|----------|
| **game-design-doc** | 编写完整的游戏设计文档（GDD） | 包含愿景、支柱、核心循环、系统、功能、盈利、风险等章节的结构化 Markdown GDD |
| **game-system-design** | 设计具体的游戏系统（战斗、经济、进度、社交等） | 系统规格说明、核心循环、反馈机制、系统交互矩阵 |
| **level-design** | 设计单个关卡、地图或任务 | 文字描述、ASCII 地图、节奏/难度曲线、敌人/掉落布局 |
| **narrative-design** | 编写剧情、角色、对话、世界观 | 故事圣经、角色档案、剧本脚本、情节流程图、环境叙事说明 |
| **game-balance** | 通过数学建模与概率分析调整数值 | 公式表、电子表格、仿真结果、平衡建议 |
| **game-economy** | 设计可持续的游戏内经济与 monetization（变现） | 来源/消耗图、兑换率、定价模型、通胀/通缩控制方案 |
| **probability-model** | 构建抽卡、掉落、暴击等随机系统模型 | 概率分布、期望值/方差计算、仿真脚本 |
| **data-table-generator** | 生成 CSV/Excel 表格（道具、敌人、技能、任务等） | 可直接导入的数据文件，内含公式、曲线、方差控制 |
| **game-dev-arch** | 定义技术架构（ECS vs OOP、网络、渲染、可扩展性） | 架构图、技术决策说明、集成指南 |
| **game-feature-impl** | 将设计转化为实施计划 | 功能拆分、实施步骤、API 契约、代码脚手架/伪代码 |
| **game-performance** | 优化 CPU/GPU、内存、Draw Call、帧率 | 性能剖析指南、优化技巧、性能预算 |

> 每个技能还提供了 **scripts/**、**references/**、**assets/** 三个可选目录的示例结构，方便你以后放置实用脚本、参考文档和模板资源。

## 🛠️ 如何使用

1. **放置技能文件夹**  
   把每个技能文件夹（包含 SKILL.md 与 gents/openai.yaml）复制到你的 Codex skills 目录中，默认路径为：  
   - ~/.codex/skills/（全局）  
   - 或你工作区根目录下的 skill/（局部）  

   示例结构：
   `
   skills/
   ├─ game-design-doc/
   │  ├─ SKILL.md
   │  └─ agents/
   │     └─ openai.yaml
   ├─ game-balance/
   │  ├─ SKILL.md
   │  └─ agents/
   │     └─ openai.yaml
   └─ …（其余 9 个技能）
   `

2. **在对话中调用技能**  
   在与 Codex 的聊天中，直接使用 $技能名 形式调用：
   `
   使用 -design-doc 为一款 sci‑fi RPG 制定 GDD，强调探索、叙事与策略三大支柱。
   `
   Codex 会读取对应的 SKILL.md，根据需要向你提问澄清信息，然后输出结构化的交付物（默认为 Markdown）。

3. **迭代优化**  
   你可以随时给出反馈或要求展开某一节（例如 “请详细说明盈利模型” 或 “补充关卡中的敌人波次”），Skill 会在已有内容基础上继续完善。

4. **丰富资源目录**  
   按需在每个技能目录下添加：  
   - scripts/：放置 Python、Bash 等辅助脚本（例如生成 GDD 的模板脚本、数值计算工具）  
   - eferences/：放文档、行业最佳实践、参考表格等  
   - ssets/：存放模板文件（Word/Google Docs 表格、图标集、UI 原型等）  

   只要在 SKILL.md 的 “Resources” 部分说明这些文件的用途，Codex 在需要时可以直接读取或调用它们。

## 📖 单个技能的文档结构（SKILL.md）

每份 SKILL.md 都采用统一的专业模板，确保任意兼容的代理均能理解其用途、调用时机以及输出期望。

- **YAML 前置信息**  
  - 
ame：技能标识（用于 $技能名 调用）  
  - description：详细说明该技能能做什么、在什么场景下使用（这是 Codex 触发技能的主要依据）

- **# 标题**  
  人类可读的名称，便于在 UI 中展示。

- **## Philosophy（理念）**  
  阐明该技能所遵循的指导原则和方法论（如“基于证据、强调可操作性、兼顾跨团队协作”）。

- **## Core Workflow（核心工作流）**  
  标准化的五步骤流程：  
  1. **Input Gathering** – 收集已有约束、参考资料或目标  
  2. **Domain Analysis** – 将需求拆解为基本组件与系统  
  3. **Structured Design** – 应用该领域的成熟框架与模式  
  4. **Output Synthesis** – 生成符合行业规范的交付物  
  5. **Validation Check** – 检查内部一致性与可落地性

- **## Detailed Guidance（详细指导）**  
  - 输入期望（可接受子弹点、粗略想法或已有文档）  
  - 逐步操作过程（按照上面的工作流执行）  
  - 决策点（根据项目规模、用户角色调整深度）  
  - 质量标准（具体、可测量、无歧义、符合目标）  
  - 常见陷阱（避免模糊表达、过早过度规范、忽视技术限制等）

- **## Output Format（输出格式）**  
  主要输出为结构化 Markdown（标题、表格、列表），可选的其他形式包括：  
  - CSV/Excel 表格（可通过 data-table-generator 子技能生成）  
  - Mermaid 语法描述的图表  
  - JSON Schema（用于数据结构）  
  - 伪代码或语言无关的逻辑规范  
  并在适当时建议调用配套技能（如数值用 data-table-generator，地图用 level-design）。

- **## Resources（可选资源）**  
  仅在你实际创建对应目录时保留此小节，列出建议放置的文件及其用途，例如：  
  - scripts/：generate_gdd.py、alance_calc.py、level_template.py  
  - eferences/：gdd_structure.md、system_design_patterns.md、monetization_models.csv  
  - ssets/：gdd_template.docx、icon_set/（里面放 Milestones、Systems、Features 图标）  

  如果不需要某类资源，直接删除对应小节即可。

## 🧩 如何扩展与自定义

- **添加帮助脚本**：把实用的 Python/Bash 等脚本放进 scripts/，并在“详细指导”或“资源”部分说明它们的作用。  
- **存放参考资料**：把行业白皮书、设计模式汇总、盈利模型对照表等文件放进 eferences/。  
- **放置模板**：Word/Google Docs 模板、图标集、HTML 骨架等放进 ssets/。  
- **调整 UI 元信息**：编辑 gents/openai.yaml，修改 display_name、short_description、rand_color 或 default_prompt，以便在 Codex 技能选择器中呈现你想要的展示效果。  
- **新增子技能**：如果你发现经常需要某种特定输出（如 “live-ops 运营计划”），可以参考现有模板新建一个文件夹，按照同样结构编写 SKILL.md 与 openai.yaml。

## 🚀 快速上手

把本仓库（或直接解压的文件夹）克隆/复制 knji 到你的 Codex 目录：

`ash
# 假设你的 Codex 工作区根目录是 ~/codex-workspace
git clone https://github.com/your-username/game-dev-skills.git ~/codex-workspace/skill
# 或者手动复制：
cp -r /path/to/this/repo/* ~/codex-workspace/skill/
`

复制完毕后，**重新启动或刷新 Codex**，让它重新加载目录中的新技能。随后即可开始使用：

`
使用 -design-doc 为我的回合制策略游戏写一份概念文档。
使用 -balance 来平衡武器伤害与敌人血量曲线。
使用 -design 设计一个包含三波怪物的地牢关卡。
`

你会得到结构清晰、可直接交付给策划、程序或美术同事的成果，显著减少从零开始撰文的时间，让团队把更多精力放在创意验证与玩法迭代上。

## 🙌 衡献指南

欢迎 Fork 本仓库、提出 Issue、提交 Pull Request！  
如果你想贡献新的技能（比如 live-ops-planning、ua‑monetization、ui-ux-guidelines 等），请遵循以下约定：

1. 新建一个文件夹，名称使用 kebab-case（如 live-ops-planning）。  
2. 内部放置 SKILL.md（参照上面的模板）以及 gents/openai.yaml。  
3. 如需，添加 scripts/、eferences/、ssets/ 子目录并说明用途。  
4. 在 Pull Request 描述中简述该技能解决的问题及其典型使用场景。  

我们会审查并合并符合质量标准的贡献。

## 📜 许可证

本项目采用 **MIT 许可证**，你可以自由在个人或商业项目中使用、修改和再分发这些技能。详见仓库根目录的 LICENSE 文件。

---

祝你使用愉快，愿这些技能助力你在游戏创作的每一步都更加高效与专业！ 🎮✨
