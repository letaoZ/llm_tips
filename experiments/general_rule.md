# Memory: General Rules
Always-on rules that apply to all code and file handling.

## File protection
NEVER delete a file. Instead:
1. Move it to `file_archive/` with new filename: `yyyymmdd_hhmmss_originalfilename` (time in ET)
2. Create `yyyymmdd_hhmmss_originalfilename_record.md` alongside it recording:
   1. Complete path of where the file is from
   2. Reason we moved it to file_archive
   3. File functionality
   4. If another file replaces it, include the new file's name
   5. If the file has bugs, state them
   6. If the file is data/analytics and not runnable, state what data it saved and why we no longer need it
   7. Any other information that best describes the situation

## Data & serialization
- Never save to pickle — version sensitive. Unless user specifically requests it.
- Save all data needed for plots and metrics.

## Loop intermediates
Always save per-iteration results if intermediate result takes time to run, to enable resuming without recomputing. Enable with a `--reset-partial-result` flag.

```python
reset = False  # if True, force recompute without using cache
result = []
for i in range(1000):
    # ADD code to load dfi if exists and not reset
    dfi = func(i, a, b, c)  # large calc
    result.append(dfi)
    # ADD code to save dfi if not exists or reset
final_result = pd.concat(result)
# more computation
final_result.to_csv("bla.csv")
```

