---
name: game-balance
description: >-
  Balance game numerical systems through mathematical modeling, probability analysis, and tuning recommendations. Use when the user says "balance combat", "tune damage values", "DPS calculation", "stat curve", "item power scaling", "HP progression", "loot table balance", or needs to derive/validate numerical relationships between game entities.
---

# Game Balance

## Rules

1. Every variable must have a TIME dimension. "DPS" is meaningless without "time-to-kill" and "combat duration".
2. Every tuning parameter expressed as: baseline tolerance (e.g., "200 20 at level 10").
3. Use multiplication analysis: never say "25% more damage" without TTK impact.
4. Never tune in isolation: small global multiplier changes destroy local values.

## Core Cycles

### Formulas Reference

**Combat Model:**
- Effective Damage Per Second (EDPS) = (baseDMG x critMultipper x hitRate) / attackInterval
- Time To Kill (TTK) = target_HP / attacker_EDPS
- EHP (Effective HP) = base_HP x (1 + armor / armor_scale) under armor mode

**Progress Model:**
- Cumulative XP from level a to b: sum(xp_per_level(i)) for i in [a, b)
- Speed decrease: base_cost / level_base_cost (progressive ratio)

**Random System:**
- EV = sum(probability_i * reward_value_i)
- Variance = sum(1/(prob_i)) per rare acquisition

### Threading Tuning Protocol

When asked to balance:
1. **Scope:** Define attribute ranges, combos, benchmarks.
2. **Model:** Build formula or lookup table.
3. **Static Check:** Validate at min/max values.
4. **Trial:** Apply delta, re-check all combos.
5. **Present:** Show low/typical/high anchor points.
6. **Monte Carlo (optional):** Run 10k samples for density.

## Workflow

The 6-step tuning protocol is followed for every balance request: Scope → Model → Check → Adjust → Present → Simulate.

## Deliverable Format

- **Formulas specification** as markdown table with variable definitions
- **Anchor data** for 3 reference levels (early, mid, late)
- **Simulation result** (optional): 2-3 percentile points
- **Red flag list** — where tuning collapses (e.g., one-shot kills possible)

## Anti-Enemplay Checklist

- [ ] TTK checked across all gear combinations
- [ ] Global multiplier drifting caught and isolated
- [ ] Scale breakers (high values) verified as bounded
- [ ] Low-level enemy not stronger than mid-level
- [ ] Tangential balance (infinite combo / stun lock) flagged

## Common Pitfalls

- "Just increase HP 20%" without checking grind-vs-challenge
- Adjusting single values leaks elsewhere: verify against entire matrix
- Weak enemies at high level create imbalance when scaled differently
