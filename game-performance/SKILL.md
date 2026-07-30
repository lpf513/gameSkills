---
name: game-performance
description: >-
  Analyze and optimize game performance including CPU/GPU profiling, memory management, draw calls, frame rate, and loading times. Use when the user experiences performance issues ("game is lagging", "fps drops", "memory leak", "loading too slow", "profiling results analysis", "what is causing frame spike"), or wants to establish performance budgets for production.
---

# Game Performance Optimization

## Rules

1. Always profile before optimizing. Any suggestion without profiling data is premature optimization.
2. State bound targets before stating causes: target frame budget (16ms for 60fps), draw call budget, memory cap, load-time ceiling.
3. Output at least one concrete code change suggestion (pseudocode or real) even for "general" optimization requests.
4. The primary cost of performanced analysis is not being perfect but being **profile-first** and **measure-shift-measure**.

## Workflow

## Diagnostic Workflow

### 1. Symptom Classification

- Low FPS? Explicitly note current FPS vs target.
- Stutter / frame-time spiking? Investigate GC / allocation spikes.
- Memory leak? Check monotonic memory increase over time.
- Battery/thermal throttle? On mobile, look at core frequency over time.

### 2. CPU Analysis Path

Draw call focused? → Batch check: static+ dynamic, GPU instancing.  Skinned mesh renderer count, bones per model, Shadow cascade triggering.

Entity computing: ?
- Throttle per tick entities
- Verify update order (fixed update / update / late update) not interleaved incorrectly
- Check empty transform updates (dirty flag missing)
- Check LOD (game id based vs model based)

Physics: collisions count per frame, In hierarchy, disable unused colliders.

### 3. GPU Analysis Path

Common bottlenecks:
- Overdraw (many transparent layers) → verify Z-test Order-check
- Shadow Pass count especially for realtime multiple lights (switch to  baked maps)
- Decals volume → per-pixel lighting cost increments

Optimization: use GPU profiler from engine frame author or Radeon GPU Profiler; record 1 frame capture.

### 4. Memory Analysis

- Allocation profile (where/when)
- Search for unnecessary copies (string, byte serialization)
- Pooling check: particle system, projectile, objects with frequencies that open/close many times
- Asset id footprint tracker for per-type extreme attachments
- Avoid GC Pending. Prealloc pool, not garbage, for time-critical loops.

### 5. Loading Time Analysis

- What assets load and how? Sync or async.
- Stream/background loading? Find dependencies out of order.
- Spike-removal: shifting loads to next frame if no rendering needed.

### Diagnostic Framework

## Output Format

- Main deliverable: issue-classification with root cause hypothesis (required)
- Then recommended code change in pseudocode or language form
- Performance budget tables (CPU ms, memory MB, draw calls, load secs)
- Change-measure loop: repeat test before/after

## Common Pitfalls

- "Make renderer faster" is generic and useless. Always blame specific pass.
- Missing isolating root cause profiling. If you cannot reproduce slowdown with clean playground, you cannot prove to thrust speed.
