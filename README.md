# CherryPicker

Certified-oriented PACE 2026 exact-track solver package.

Build:

```bash
make
```

This builds the many-tree executable:

```text
build/manytree_solver
```

Run:

```bash
./solve < instance.nw
```

The submitted entrypoint is the `./solve` script. No prebuilt submit binary is
included in this branch; the solver should be built from source with `make`.

The entrypoint intentionally terminates with no output for two-tree instances:

```bash
#p 2 n
```

For `t>2`, `./solve` dispatches to the certified many-tree core.
