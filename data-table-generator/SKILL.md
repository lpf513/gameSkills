---
name: data-table-generator
description: >-
  Generate structured numerical data tables (CSV/Excel) for game content: items, enemies, abilities, quest rewards, crafting recipes. Use when the user says "generate data table", "item table", "enemy stat sheet", "XP curve table", "recipe table", or any bulk numerical content for game configuration. Outputs are import-ready with formulas, growth curves, and verified consistency.
---

# Data Table Generator

## Rules

1. Always output as CSV or human-readable Markdown table, with a clear header row and column labels.
2. Data columns must include: ID (unique), Name, and at least one stat column.
3. Growth/level columns: provide the FORMULA in a comment line beneath the header: `# formula: base_stat * level^exponent`.
4. Verify: total rows match expected count; columns align; no cell left blank unless explicitly described.

## Workflow

### 1. Schema Definition (before any data)

Produce the column header row with types in parentheses:

```
ID | Name | Attack | HP | Speed | DropRate
int| str  | int(1-999)| int(500-50000) | int | float(0-1)
```

### 2. Anchor Points

Generate 3 reference rows (level 1, level mid, level max) first to verify formula and range with the user.

### 3. Mass Generation + Validation

- Check that all IDs are unique.
- Scan for missing values (NULL detection).
- Round to appropriate significant digits.

### 4. Geometric/Formula Line

Below the data, produce the empirical formula check:

```
Growth check: HP at max / HP at level 1 = 50; Attack at max / Attack at level 1 = 25
```

### 5. Delivery

Toxic ones: offer to export as CSV string, XLSX through use of spreadsheet skill, or draw as a markdown table.

## Output Format
- Surface: Markdown table with comment lines for others
- Suggested clean: CSV dump in code block


### Schema Validation (before delivery)

- Verify every int column has no empty cells; replace ? with sentinel value 0.
- Check formula consistency across rows: if HP = baseHP * level^1.2, validate 3 anchor rows.
- Ensure unique IDs, sorted by ID.

### Export

Default delivery as Markdown table with formula comments. Optionally export as CSV block or XLSX using spreadsheet skills.

### Formula Template

When generating growth curves, provide the formula in comment form:
`
# HP = base_hp * level^1.15
# Attack = base_atk * level^0.95
`
Verify formula consistency: check value at level 1 and level max before mass generation.

### Column Checklist

- Is every column type defined? (int, float, string, and legal range)
- Are derived columns verified? (total_price = base_price * level_factor)
- Is the unique column present? (ID, not nullable)
## Common Pitfalls
- Forgetting to anchor the first and last row data for verification.
- No formula line, so the user cannot independently verify intermediate data.
- Missing null-check for gaps in auto-generated ranges.

