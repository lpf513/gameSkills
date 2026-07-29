---
name: game-performance
description: >-
  Analyze and optimize game performance including CPU/GPU usage, memory management, draw calls, and frame rate. Use when the user experiences performance issues or wants to ensure smooth gameplay. Outputs include profiling guides, optimization techniques, and performance budgets.
---

# Game Performance Optimization

## Philosophy

This skill follows a pragmatic, evidence-based approach to game performance. It emphasizes clarity, actionability, and integration with broader development workflows. Outputs are designed to be directly usable by designers, developers, and producers without further interpretation.

## Core Workflow

1. **Input Gathering** – Collect any existing constraints, references, or goals from the user.
2. **Domain Analysis** – Break down the request into fundamental components and systems.
3. **Structured Design** – Apply established frameworks and patterns specific to game performance.
4. **Output Synthesis** – Produce well-formatted deliverables that match industry standards.
5. **Validation Check** – Ensure internal consistency and readiness for implementation.

## Detailed Guidance

- **Input expectations**: Accepts bullet points, rough ideas, or existing documents. Asks clarifying questions if scope is ambiguous.
- **Step-by-step procedures**: Follows the workflow above, emitting structured Markdown by default.
- **Decision points**: Adapts depth based on project scale (indie vs AAA) and user role (designer vs programmer).
- **Quality criteria**: Outputs are specific, measurable, unambiguous, and aligned with stated goals.
- **Common pitfalls**: Avoids vague language, over-specification prematurely, and ignoring technical constraints.

## Output Format

Primarily outputs structured Markdown with clear headings, tables, and lists. Can also produce:
- CSV/Excel tables (via data-table-generator sub-skill)
- Diagrams described in Mermaid syntax
- JSON schemas for data structures
- Pseudocode or language-agnostic logic specs

When appropriate, the skill will suggest using companion skills (e.g., data-table-generator for numbers, level-design for maps) and invoke them.

## Resources (optional)

### scripts/
- generate_gdd.py – Helper script to convert structured data into full GDD Markdown.
- balance_calc.py – Probability and expected value calculator for game systems.
- level_template.py – Procedural level layout generator based on parameters.

### references/
- gdd_structure.md – Canonical outline of a professional GDD.
- system_design_patterns.md – Common architectural patterns in game systems.
- monetization_models.csv – Reference table of f2p, premium, and hybrid models.

### assets/
- gdd_template.docx – Optional Word template for teams requiring DOCX.
- icon_set/ – Simple PNG icons for Milestones, Systems, Features.

---
