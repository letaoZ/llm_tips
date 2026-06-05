# Skill: /run-job
Triggered before and while running any script (background or foreground).

## Steps

### 1. Pre-run checks
- Check for duplicate processes already running. If a dupe exists, confirm it is a real dupe and kill it.
- Dry-run the script first. Perform smoke tests to ensure code runs correctly.
  - If the job saves output, verify that saving works successfully in the dry-run.

### 2. Write down complete script
Before launching in background, save the complete script that will be run.

### 3. Launch and monitor in background
- Save logs in a designated folder. If not given, create `logs/` or `results/<subproject>/logs/`.
- Logs must include:
  - Time consumption
  - Memory consumption
  - CPU consumption
  - Reestimated total runtime (updated periodically)
  - Progress bar

### 4. Intermediate results
Scripts should generate intermediate results so one can:
- Early detect potential bugs
- Resume if job failed (see General Rules: loop intermediates with `--reset-partial-result`)

### 5. bash_yard
Save on-the-fly bash scripts (NOT carefully designed background scripts) to:
```
bash_yard/yyyymmdd/{subproject}/
```
- Organized by day and subproject
- Clean up EOD — keep useful ones, discard throwaway
