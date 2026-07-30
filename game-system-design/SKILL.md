---
name: game-system-design
description: >-
  Design a single game system or subsystem at a deliverable level. Use when the user says "design the X system", "create a system spec for X", "system design", "spec the combat/loot/progression/guild/matchmaking system". Outputs a system spec including objectives, player action verbs, data model, core algorithm pseudocode, integration points, edge cases, tuning knobs, quick-validation test plan, and dependency map.
---

# Game System Design

## Rules

1. Always assign a design pattern label before describing the solution (FSM, observer, event queue, lazy eval, etc.).
2. Always include a 1-hour MVP test that validates the core concept before building.
3. Every tuning parameter bounded: min / default / max. Zero unbounded values.
4. One system = one document. If the user mentions multiple systems, list and confirm ordering with them.

## Workflow

### 1. System Problem Scene

- What player behavior or loop drives this system?
- What specific problem does it solve?
- Who is the primary persona?
- Budget constraints: time, art, server, network.

### 2. Architectural Pattern Selection

Require the pattern label explicitly:

- **State machine** for progression / achievement / quest state.
- **Observer/Callback** for any UI-model inversion.
- **ECS layout** for tunable runtime component data.
- **Lazy evaluation** for bough/debuff stacking.
- **Round-Robin / Time-slice** for discrete simulation steps.

### 3. Detailed Spec Blueprint

| Section | Description |
|---|---|
| **Data Model** | Entities, attributes, relationships, raw structures |
| **Core Algorithm** | Pseudo-code walkthrough (step-by-step) |
| **Interface/API** | Entry points and mutation points for other systems |
| **Edge Cases** | empty initial, full-capacity, single-player, first-login, error recovery |
| **Tuning Knobs** | Table: name - min - optimum - max |
| **Feature Guard & Backout** | how to enable/disable at runtime; backout if broken |

### 4. Release Validation Checklist

- Test flag name & default state
- Silent deploy sequence
- Monitor metrics for rapid close indicator
- 1-hour smoke test:
  - one unit test for core algorithm edge
  - one state machine transition test
  - one integration test with "no-op" inputs

## Output Format

- System spec table (as above)
- Mermaid state/flow diagram
- Wilderness pseudo-code snippet (single method)
- Dependency manifest (what this system needs before first deploy)

## Common Pitfalls

- Over-design for scale before existence proof of concept.
- No null/probability path handling → system fails in empty initial state.
- Interfacing via string-based conventions → compile-time interface contracts are safer.
