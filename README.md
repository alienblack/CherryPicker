# CherryPicker

Certified-oriented PACE 2026 exact-track solver package.

Build:

```bash
make
```

Run:

```bash
./solve < instance.nw
```

The entrypoint intentionally terminates with no output for two-tree instances:

```bash
#p 2 n
```

For `t>2`, it dispatches to the certified many-tree core.
