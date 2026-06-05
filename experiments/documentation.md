# Memory: Documentation & Writing Rules
Always-on rules that apply whenever writing any doc or code file.

## Doc writing rules
1. When drafting any doc, ask clarifying questions before drafting; record Q&A and decisions with reasons.
2. Record timestamp on top of each file on creation.
3. Record code/functions used.
4. Record references (e.g. github link, papers, other reports/results, etc.) used.
5. Record bugs found — specifically write out how you found the bug and how you fixed it.
6. Write notes and steps when making changes.
7. Save each step's work, progress and results in a separate .md in docs folder.
8. Escape `$` and `%` in markdown with `\$` and `\%`.
9. When referencing figures in markdown docs, place them in `docs/figures/` with descriptive names (e.g. `1.2.3_timeseries_agg.png`).
10. Name generated python/sh files following lowercase section content name. Example: if section is `1.3.5 Hello World` in plan.md:
    - `hello_world_math.py`
    - `hello_world.py`
    - `hello_world_summary.py`
    - `hello_world_run.sh`
    - `hello_world_*.*`
11. Use correct python paths anchored via `Path(__file__).resolve().parent` and store all paths in `config.py`. Example:
    ```python
    # === Repository layout =====================================================
    SIGNAL_EVAL_ROOT = Path(__file__).resolve().parent
    NOTEBOOKS_ROOT   = SIGNAL_EVAL_ROOT.parent
    CLEAN_UNIVERSE_DIR = NOTEBOOKS_ROOT / "universe"
    DATA_SNAP_DIR      = NOTEBOOKS_ROOT / "data_snap"
    ```

## Communication
- Write Slack message when job finishes — filtered to channels: **DONE** / **Partial Results** / **Broken**
