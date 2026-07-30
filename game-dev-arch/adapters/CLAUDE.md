# game-dev-arch
Define technical architecture for game projects: engine selection, rendering pipeline, ECS vs OOP, networking model, threading model, asset pipeline, platform release strategy. Use when the user wants to plan the technical foundation of a game, evaluate engine tradeoffs, or prepare a technical design document.

# Game Development Architecture

## Rules

1. Frame budget and memory budget define everything. State them first.
2. Platform constraints determine architecture: GPU tier, install size, threading limits.
3. Every subsystem declares its thread: main thread, worker pool, GPU, or RPC.
4. Entity model must be explicitly chosen: ECS (for cache locality, high entity count) or OOP (familiarity, editor support). Provide a 1-sentence justification.

## Workflow

### 1. Scope Questionnaire

Ask the user (if not given):
- Target FPS and frame budget (60fps = 16ms per frame)?
- Platform(s)?
- Engine candidate(s)?
- Max simultaneous entities (players, enemies, projectiles, objects)?
- Network model (single-player, cooperative, dedicated server, P2P)?
- Modding support needed?

### 2. Core Architecture Decision Matrix

| Domain | Options | Decision | Justification |
|---|---|---|---|
| Engine | Unreal / Unity / Godot / custom | ... | team skill, target quality, platform support |
| Render | forward / deferred / hybrid | ... | transparency needs, light counts, dynamic light |
| Physics | built-in / dedicated / simplified | ... | body count, CCD needs |
| Network | authoritative / P2P / hybrid | ... | competitive vs casual, cheating tolerance |
| Asset Load | sync / async / streaming | ... | memory target, world size, open-world / linear |
| Scripting | Lua / C# / blueprint / none | ... | designer exposure, scope of scripting |

### 3. System Architecture

Provide Mermaid-like text diagram showing:
- Input stack
- Game logic tick loop
- Rendering queue
- Audio pipeline
- UI controller
- Asset manager

### 4. Threading Model

| Subsystem | Thread | Communication |
|---|---|---|
| Input | Main thread | event queue |
| Physics | worker pool | FIFO batch |
| Audio | dedicated thread | message bus |
| Render | Main thread + GPU | GPU buffer |

### 5. Asset and Content Pipeline

- Source asset -> Intermediate format -> Runtime format flow
- Bundle size target per platform
- Hot-module swap: editor-only or production?

### 6. Network Architecture

- Network topology
- Tick rate and reconciliation method
- Peak bandwidth per player estimate

### 7. Build and Delivery

- Per-platform tooling
- CI pipeline overview
- Crash / error reporting stack outline

## Output Format

- Technology decision matrix (table)
- Mermaid architecture diagram
- Per-subsystem requirements table
- Asset pipeline flow-sheet

## Common Pitfalls

- Engine choice based on trailers rather than team competence.
- Memory cap unspecified until tail end of production leads to restructure.
- Over-engineering for speculative scale rather than validated requirements.
