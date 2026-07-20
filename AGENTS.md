# Agent instructions

Before any task: **read `skills/README.md`** — it is the router.
Find your task in its table and load exactly **one** skill (plus
`skills/flyrank/flyrank-data/SKILL.md` when touching data).

## Commands

- `python scripts/run_all.py` — run the full pipeline on the bundled sample (~1 min).
  No test framework exists. This or executing a notebook end-to-end is how you verify.
- `pip install -r requirements.txt` — dependencies (pandas, numpy, scikit-learn, duckdb, etc.)
- Windows: prepend `$env:PYTHONIOENCODING='utf-8';` to pipeline commands (run_all.py uses `▶` U+25B6)
- If pipeline fails with "Raw input not found": `git checkout -- data/raw/content_refresh_anonymized.csv`

## Critical data gotchas

- **Rate columns are ×100**: `ctr=0.76` means **0.76%**, not 76%. Same: engagement_rate,
  scroll_rate, ai_traffic_pct, trend_pct.
- **`avg_position=0` = no data** (1205 rows), not rank zero.
- **`trend_direction` and `trend_pct` are NEVER features** — `is_declining_label` is derived
  from `trend_direction == "down"`. Using either in a model is label leakage.
- **IDs are pseudonyms** — `content_id` / `client_id` are for grouping/splitting only,
  never as features.
- **Missingness is systematic by `content_type`** — prefer `has_*` indicator columns over
  blind `fillna(0)`.

## Conventions

- `scripts/` is the reference pipeline — **do not edit**. Copy to `work/` for experiments.
- Feature lists in `scripts/ml_utils.py` (`MODEL_NUMERIC_FEATURES`, `MODEL_CATEGORICAL_FEATURES`).
- `.gitignore` blocks datasets. `work/**/*.csv` is ignored; `work/outputs/*.json` should be
  committed (they are the metric receipts).
- `CLAUDE.md` at root is identical to this file — keep both in sync if you edit one.

## Ground rules

- Search before assuming something is missing. One task per conversation.
- Never commit datasets (CI blocks CSV/parquet/zip/tar/feather). Never print private data,
  client names, or raw queries.
- The intern validates your output — end each task by running the notebook top to bottom.
