# CherryPicker

Certified-oriented PACE 2026 exact-track solver package.

Build:

```bash
make
```

Run:

```bash
./solver_submit < instance.nw
```

The submit entrypoint intentionally gives no output for two-tree instances:

```bash
#p 2 n
```

For `t>2`, it dispatches to the certified many-tree core. This is a
conservative output policy: if the solver cannot safely justify the result, it
prints nothing rather than returning a risky forest.

## Update note for branch `new`

This branch contains the corrected submit-ready packaging for CherryPicker. The previous pushed folder was incomplete and did not include the intended combined submit wrapper/build target and final certified submit binary.

This branch includes:

- `solver_submit`: Linux static submit executable.
- `combined_wrapper.cpp`: wrapper combining the certified many-tree and two-tree routes into one executable.
- Makefile target for building `solver_submit`.
- Bundled many-tree source.
- Bundled h56/HiGHS two-tree route source.

Final safety update:

- Two-tree instances are suppressed by the wrapper and produce no output.
- Timeout/SIGTERM incumbent output in the bundled two-tree route is guarded so
  an unfinished incumbent cannot be printed accidentally.
- The many-tree executable is built with strict/certified defaults and
  empirical accepts disabled.

CherryPicker is the certified/conservative version.
