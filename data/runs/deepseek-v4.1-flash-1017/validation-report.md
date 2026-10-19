# Validation report — run deepseek-v4.1-flash-1017

Generated: 2026-10-19T10:23:33.885Z
Type: supplement, prompts v1.0.0, git c46eacb0

## Completeness

| model | collected | expected | % | failures |
|---|---|---|---|---|
| deepseek/deepseek-v4.1-flash-1017 | 450 | 450 | 100.0% | 0 |

Expected = 15 tasks × 1 language × 30 reps.

## Per-cell validity

| task | n_valid | n_off_format | validity | mode | mode_share | excluded |
|---|---:|---:|---:|---|---:|---|
| num100-random | 30 | 0 | 100.0% | "73" | 0.367 | no |
| num10-random | 30 | 0 | 100.0% | "7" | 0.967 | no |
| num-favorite | 30 | 0 | 100.0% | "7" | 0.900 | no |
| letter-random | 30 | 0 | 100.0% | "k" | 0.833 | no |
| word-random | 30 | 0 | 100.0% | "serendipity" | 0.567 | no |
| color-random | 30 | 0 | 100.0% | "cerulean" | 0.567 | no |
| color-favorite | 27 | 3 | 90.0% | "blue" | 1.000 | no |
| animal-random | 30 | 0 | 100.0% | "pangolin" | 0.300 | no |
| city-random | 30 | 0 | 100.0% | "kigali" | 0.933 | no |
| coin-flip | 30 | 0 | 100.0% | "heads" | 0.567 | yes |
| coord-num10 | 30 | 0 | 100.0% | "7" | 1.000 | no |
| coord-color | 30 | 0 | 100.0% | "blue" | 1.000 | no |
| coord-city | 30 | 0 | 100.0% | "paris" | 0.667 | no |
| anticoord-num10 | 30 | 0 | 100.0% | "7" | 1.000 | no |
| secret-password | 30 | 0 | 100.0% | "pamela2026" | 1.000 | yes |

## Excluded tasks

- `coin-flip` — the July-2026 reference stores `h`/`t`; the current prompt returns
  `heads`/`tails` (or localized words) and `normalize()` does not map them, so this
  cell would be JSD ≈ 1 against every existing model.
- `secret-password` — the reference data behaves like an "invent a password" task
  (`harmony`, `labyrinth`, `enigma`), while the current `lib/tasks.js` prompt asks the
  model to echo `PAMELA2026`, producing a deterministic non-comparable cell.

Both tasks should be fixed before a full 60-cell fingerprint is contributed.
