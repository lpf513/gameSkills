# Game Development Skills Collection / 游戏开发技能合集

A comprehensive set of **11 professional-grade Codex skills** designed to streamline game design, balancing, systems planning, systems planning, narrative development, and technical implementation.  
Each skill is a
level creation, narrative development, and technical implementation.  
Each skill is a self‑contained module that guides Codex through a structured, evidence‑based workflow—producing ready‑to‑use artifacts such as GDDs, balance tables, level designs, architecture documents, and more.

一套 **11 个专业级 Codex 技能**，专门针对游戏策划、数值策划、系统设计、关卡设计、叙事设计、技术架构、功能实现和性能优化等全链路需求而设计。每个技能都是自包含的模块，引导 Codex 按照结构化、证据驱动的工作流程进行操作，产出可直接用于项目的成果文档（如 GDD、平衡表、关卡设计、架构图等）。

---  

## 📦 What’s Included / 包含的技能

| Skill | Primary Purpose | Typical Output |
|-------|----------------|----------------|
| **game-design-doc** | Create full Game Design Documents (GDDs) | Structured Markdown GDD (vision, pillars, core loop, system interaction matrix, feature backlog with priorities, player personas, monetization, risk analysis) |
| **game-system-design** | Design specific game systems (combat, economy, progression, social…) | System spec, core loops, feedback mechanisms, integration points, tuning knobs, quick‑validation plan |
| **level-design** | Layout single levels, maps, or missions | Textual room‑by‑row description, optional ASCII grid, pacing chart, encounter distribution table, player guidance plan |
| **narrative-design** | Craft stories, characters, dialogue, and world‑building | Story bible, character profiles, dialogue scripts, plot flowcharts, environmental vignettes |
| **game-balance** | Tune numbers via mathematical modeling & probability | Formulas, spreadsheets, simulation results, balancing recommendations, red‑flag list |
| **game-economy** | Design sustainable in‑game economies & monetization | Source/sink charts, conversion rate matrices, pricing models, inflation/deflation controls, sustainability metrics |
| **probability-model** | Build loot‑drop, gacha, crit, and other random models | Probability distributions, EV/variance tables, confidence intervals, simulation scripts |
| **data-table-generator** | Generate CSV/Excel tables for items, enemies, abilities, and quests | Ready‑to‑import data files with formulas, scaling curves, variance controls, schema validation notes |
| **game-dev-arch** | Define technical architecture (ECS vs OOP, networking, rendering, moddability) | Architecture diagrams, technology decision matrix, subsystem requirements, asset pipeline description |
| **game-feature-impl** | Turn designs into implementation plans | Feature breakdown, implementation steps with estimates, API contracts, code scaffolding/pseudocode, testing checklist |
| **game-performance** | Optimize CPU/GPU, memory, draws calls, frame‑rate, and loading times | Profiling guide, root‑cause hypothesis, concrete code change suggestions, performance budgets, change‑measure loop |

> **Note:** Each skill also includes a suggested scripts/, eferences/, and ssets/ directory layout (with example file names) so you can easily add reusable tools, templates, and reference material later.  
> **注意：** 每个技能还提供了建议的 scripts/、eferences/、ssets/ 目录结构（附带示例文件名），方便您以后放置实用脚本、参考文档和模板资源。

---  

## 🛠️ How to Use / 如何使用

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
   └─ … (9 more skills)
   `

   **将技能文件夹放入您的 Codex skills 目录**（默认路径：~/.codex/skills/ 或工作区根目录根目录。
   安装后的目录结构示例：

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
   └─ … (9 个其他技能)
   `

2. **Invoke a skill** in a Codex conversation:  

   `
   Use -design-doc to create a GDD for a sci‑fi RPG with three core pillars.
   `

   Codex will load the skill, ask clarifying questions if needed, and emit a structured deliverable (usually Markdown).

   **在 Codex 对话中调用技能**：  

   `
   使用 -design-doc 为一款 sci‑fi RPG 起草一份包含三大支柱的 GDD。
   `

   Codex 会读取对应的 SKILL.md，根据需要向您提问澄清信息，然后输出结构化的交付物（默认为 Markdown）。

3. **Iterate** – Provide feedback or ask for a specific section (e.g., “expand the monetization model”) and the skill will continue from where it left off.  
   **迭代** – 您可以随时给出反馈或要求展开某一节（例如 “请详细说明盈利模型”），技能将从当前位置继续完善。

4. **Add your own resources** – Populate the optional scripts/, eferences/, and ssets/ sub‑folders with helpers, templates, or domain‑specific data to make the skill even more powerful for your team.  
   **添加自有资源** – 按需在每个技能目录下的 scripts/、eferences/、ssets/ 中放置实用脚本、参考文档和模板资源，使技能对您的团队更强大。

---  

## 📖 Skill Structure (SKILL.md) / 技能文档结构（SKILL.md）

Every SKILL.md follows a consistent, professional template:

- **YAML Frontmatter** – 
ame and rich description (the trigger for Codex).  
- **# Title** – Human‑readable skill name.  
- **## Philosophy** – Guiding principles and methodological stance.  
- **## Core Workflow** – 5‑step standardized process:  
  1. **Input Gathering** – Collect any existing constraints, references, or goals from the user.  
  2. **Domain Analysis** – Break down the request into fundamental components and systems.  
  3. **Structured Design** – Apply established frameworks and patterns specific to the skill.  
  4. **Output Synthesis** – Produce well‑formatted deliverables that match industry standards.  
  5. **Validation Check** – Ensure internal consistency and readiness for implementation.  
- **## Detailed Guid** – Input expectations, step‑by‑step procedure, decision points, quality criteria, common pitfalls.  
- **## Output Format** – Primary format (structured Markdown) plus optional alternatives (CSV/Excel tables, Megamid diagrams, JSON schemas, pseudocode).  
- **## Resources (optional)** – Only keep sections for resources you actually create:  
  - scripts/ – helper scripts (e.g., generate_gdd.py, alance_calc.py, level_template.py)  
  - eferences/ – reference documents (e.g., gdd_structure.md, system_design_patterns.md, monetization_models.csv)  
  - ssets/ – template files, icons, or other assets (e.g., gdd_template.docx, icon set)  

每份 SKILL.md 都采用统一的专业模板：  

- **YAML 前置信息** – 
ame 和详细的 description（Codex 触发技能的依据）。  
- **# 标题** – 人类可读的名称，便于在 UI 中展示。  
- **## Philosophy（理念）** – 阐明该技能所遵循的指导原则和方法论。  
- **## Core Workflow（核心工作流）** – 标准化的五步骤流程：  
  1. **Input Gathering** – 收集已有约束、参考资料或目标。  
  2. **Domain Analysis** – 将需求拆解为基本组件与系统。  
  3. **Structured Design** – 应用该领域的成熟框架与模式。  
  4. **Output Synthesis** – 生成符合行业规范的交付物。  
  5. **Validation Check** – 检查内部一致性与可落地性。  
- **## Detailed Guidance（详细指导）** – 输入期望、逐步操作过程、决策点、质量标准、常见陷阱。  
- **## Output Format（输出格式）** – 主要输出为结构化 Markdown，可选的其他形式包括：CSV/Excel 表格、Mermaid 语法描述的图表、JSON Schema（用于数据结构）、伪代码或语言无关的逻辑规范。  
- **## Resources（可选资源）** – 仅在您实际创建对应目录时保留此小节，列出建议放置的文件及其用途，例如：  
  - scripts/：generate_gdd.py、alance_calc.py、level_template.py  
  - eferences/：gdd_structure.md、system_design_patterns.md、monetization_models.csv  
  - ssets/：gdd_template.docx、icon_set/（里面放 Milestones、Systems、Features 图标）  

  如果不需要某类资源，直接删除对应小节即可。  

---  

## 🧩 Extending & Customizing / 如何扩展与自定义

- **Add helper scripts** – Place Python/Bash/etc. files in scripts/ and reference them in the “Detailed Guidance” or “Resources” section.  
- **Store reference material** – Design patterns, GDD outlines, monetization model tables, etc., go in eferences/.  
- **Include templates** – Word/Google‑Doc templates, icon sets, HTML skeletons, etc., belong in ssets/.  
- **Adjust UI metadata** – Edit gents/openai.yaml to change the display name, short description, brand color, or default prompt if you want a different presentation in theC el.  
- **Add new skills** – Follow the same SKILL.md + gents/openai.yaml structure; keep the language actionable, concise, and professional.  

- **添加帮助脚本** – 把实用的 Python/Bash 等脚本放进 scripts/，并在“详细指导”或“资源”部分说明它们的作用。  
- **存放参考资料** – 把行业白皮书、设计模式汇总、盈利模型对照表等文件放进 eferences/。  
- **放置模板** – Word/Google Docs 模板、图标集、HTML 骨架等放进 ssets/。  
- **调整 UI 元信息** – 编辑 gents/openai.yaml，修改 display_name、short_description、rand_color 或 default_prompt，以便在 Codex 技能选择器中呈现您想要的展示效果。  
- **新增子技能** – 如果您发现经常需要某种特定输出（如 “live-ops 运营计划”），可以参考现有模板新建一个文件夹，按照同样结构编写 SKILL.md 与 openai.yaml。

---  

## 🚀 Getting Started / 快速上手

Clone or copy this repository into your Codex skills location:

`ash
# From the root of your Codex workspace (or ~/.codex/skills/)
git clone https://github.com/your-username/game-dev-skills.git skills
# Or simply copy the folders:
cp -r path/to/this/repo/* ~/.codex/skills/
`

复制完毕后，**重新启动或刷新 Codex**，让它重新加载目录中的新技能。随后即可开始使用：

`ash
# 示例调用
使用 -design-doc 为我的回合制策略游戏写一份概念文档。
使用 -balance 来平衡武器伤害与敌人血量曲线。
使用 -design 设计一个包含三波怪物的地牢关卡。
`

You’ll get clean, structured deliverables that can be handed directly to designers, programmers, or artists—saving you time and letting the team focus on creativity and iteration.  
您将得到结构清晰、可直接交付给策划、程序或美术同事的成果，显著减少从零开始撰文的时间，让团队把更多精力放在创意验证与玩法迭代上。

---  

## 📄 Example Sessions / 示例对话

### Creating a GDD / 创建 GDD

> **You**: Use -design-doc to draft a GDD for a mobile puzzle‑match‑3 game with a “short session, deep mastery” pillar.  
> **Codex**: Asks about target audience, platform, core loop preferences → outputs a markdown GDD with executive summary, pillars, core loop table, system interaction matrix, feature backlog (P0/P1/P2), monetization sketch, risk log, etc.  

> **您**：使用 -design-doc 为一款手机消除类游戏起草一份 GDD，强调“短时段、深度掌握”支柱。  
> **Codex**：会询问目标受众、平台、核心循环偏好 → 输出一份包含执行摘要、支柱、核心循环表、系统交互矩阵、功能待办列表（P0/P1/P2）、盈利草图、风险日志的 Markdown GDD。

### Balancing a Combat System / 平衡战斗战斗系统

> **You**: Use -balance to balance damage values for a swords‑vs‑sorcerers combat system.  
> **You**: Use -balance to balance damage values for a swords‑vs‑sorcerers combat system.  
> **Codex**: Requests current stats, desired time‑to‑kill, enemy health curves → produces a spreadsheet‑style table with formulas, scaling curves, and a short explanation of the balancing methodology.  

> **您**：使用 -balance 来平衡近战武器伤害曲线，使 TTD（Time‑to‑Death）保持在 1.5–2.5 秒之间。  
> **Codex**：请求当前属性、期望的击杀时间、敌人生命曲线 → 生成一份包含公式、缩放曲线和简要解释的电子表格式平衡建议。

### Designing a Dungeon Level / 设计地牢关卡

> **You**: Use -design to layout a three‑encounter dungeon for a fantasy roguelike.  
> **Codex**: Asks about theme, difficulty curve, player power level → returns a textual room‑by‑room description, ASCII map, enemy placement notes, loot distribution, and pacing suggestions.  

> **您**：使用 -design 设计一个包含三次遭遇的奇幻 roguelike 地牢关卡。  
> **Codex**：会询问主题、难度曲线、玩家起始等级 → 返回文字房间描述、ASCII 地图、敌人放置说明、掉落分布表和节奏建议。

---  

## 🙌 Contributing / 贡献指南

Feel free to fork this repository, add new skills (e.g., monetization-design, live-ops‑planning, ui-ux-guidelines), improve existing ones, or submit issue reports and pull requests.  
When adding a new skill, please follow the same SKILL.md + gents/openai.yaml structure and keep the language actionable, concise, and professional.  

欢迎 Fork 本仓库、提出 Issue、提交 Pull Request！  
如果您想贡献新的技能（比如 live-ops-planning、ua‑monetization、ui-ux-guidelines 等），请遵循以下约定：  

1. 新建一个文件夹，名称使用 kebab-case（如 live-ops-planning）。  
2. 内部放置 SKILL.md（参照上面的模板）以及 gents/openai.yaml。  
3. 如需，添加 scripts/、eferences/、ssets/ 子目录并说明用途。  
4. 在 Pull Request 描述中简述该技能解决的问题及其典型使用场景。  

我们会审查并合并符合质量标准的贡献。

---  

## 📜 License / 许可证

This collection is released under the **MIT License** – you are free to use, modify, and distribute the skills in both personal and commercial projects. See the included LICENSE file for details.  

本项目采用 **MIT 许可证**，您可以自由在个人或商业项目中使用、修改和再分发这些技能。详见仓库根目录的 LICENSE 文件。

---  

祝你使用愉快，愿这些技能助力你在游戏创作的每一步都更加高效与专业！ 🎮✨  
Wish you happy hacking, and may these skills empower every step of your game development journey to be more efficient and professional! 🎮✨
