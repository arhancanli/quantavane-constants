# Named constants: best known bounds, who holds them, and checkers

A living table of named mathematical constants. For each bound it gives the best value we know of, who holds it and
where it is published, Quantavane's own certified bound where we have one, and a program that checks it.

## The files

`constants.csv`, one row per bound (a constant with a lower and an upper bound has two rows):

| column | meaning |
|---|---|
| `id` | `QV-...` where Quantavane's certified bound is the best we know; `T-<n>-l` / `T-<n>-u` for the lower / upper bound of constant `<n>` in Terence Tao's table of optimization constants |
| `constant` | its name |
| `field` | the area of mathematics (for `T-` rows, see the constant's page) |
| `bound` | `lower` or `upper` |
| `best_known` | the best bound, as the source prints it (a value in parentheses with `*` is a bound that table marks with its asterisk) |
| `holder` | who holds that bound: the reference printed next to it, with the citation from the same page |
| `holder_source` | where it is published |
| `quantavane_bound` | our own certified bound, if any |
| `quantavane_best` | `yes` when our bound is the best we know of |
| `checker` | a program that checks the bound or rows posted for the constant |
| `status` | how the row is established |
| `notes` | the previous best, the holder of a starred value, and anything a reader should know |
| `holder_check` | how the holder was read, and against which file |

`replays.csv` lists the 121 replay folders of github.com/arhancanli/quantavane-replays used in the `checker` column,
the constant each one replays, and how that was established (the folder's own heading, the replay repository's
README, or the folder name).

## What is in it

- **4 constants where our certified bound is the best we know of** (rows `QV-`):
  - the union-closed sets constant, c_UC >= c* + 3.0e-4 (github.com/arhancanli/quantavane-union-closed);
  - the diagonal Ramsey growth base, R(k,k) <= (3.4827 + o(1))^k;
  - the off-diagonal Ramsey exponents on l/k in [1/5, 1] (Theorem O). These two are in
    github.com/arhancanli/quantavane-diagonal-ramsey;
  - the smallest rank at which the van Emde Boas-Kruyswijk conjecture fails for C_6^r: D(C_6^13) >= 67, so
    D(C_6^r) > 5r + 1 from r = 13, where Gao, Geroldinger, Wang and Zeng (arXiv:2611.24775) showed it from r = 23
    (github.com/arhancanli/quantavane-davenport-c6).

  Each has two separately written checkers and a referee inside Quantavane. None is peer reviewed yet.
- **120 constants of Terence Tao's table** (github.com/teorth/optimizationproblems), 240 bounds, as listed on its main
  branch at commit 87b4ebb (28 October 2026; still the head of main on 20 November 2026).
  - The holder of every one of the 240 bounds was read against the constant's own page at the same commit.
  - 136 rows match the listed value exactly, on one row of the page's bound table.
  - 67 match one row where the page writes the same value in another form (a fraction, a closed form, more digits).
  - 37 were read by hand: several rows share the value, the page writes it quite differently, or the bound is
    trivial, classical or infinite. `holder_check` says which, row by row.
  - For 97 of the 120 constants, a replay of rows posted for that constant is in github.com/arhancanli/quantavane-replays,
    with two programs and red controls per replay.
- **Known to be newer than that snapshot:**
  - The minimum overlap constant (1b) has public step functions on the EinsteinArena leaderboard below the listed
    0.38085856. The best we found is 0.3808562597779765..., exact, posted between 16 and 29 October 2026.
  - Several rows have open pull requests in Tao's repository.

  Rows are refreshed from each source.

## Counting rule

A row says `quantavane_best = yes` only when our bound is certified by two separately written programs, has passed a
fresh referee, and beats every bound we found at the source on the same day. A tie is not a record. Rows that restate
another table credit it and its sources; we add checkers, never a claim.

## Licences and credit

The data of this repository is CC BY 4.0 (`LICENSE`). The `T-` rows restate bounds and references from Terence Tao's
table, which is under the Apache License 2.0 (a copy is in `LICENSE-teorth-optimizationproblems`); please cite that
table and the papers it cites.

## How to cite

```bibtex
@misc{quantavane-constants,
  author       = {Canli, Arhan},
  title        = {Named constants: best known bounds, who holds them, and checkers},
  year         = {2026},
  howpublished = {\url{https://github.com/arhancanli/quantavane-constants}},
  note         = {Quantavane; data CC BY 4.0}
}
```

Known uses of this work are listed in [USED_BY.md](USED_BY.md). If you use it, please open an issue or a pull request
with a link so that yours can be added.

## Authorship and the role of AI

Author and maintainer: Arhan Canli (Quantavane), who takes responsibility for this table.

The searches, checks, programs and text here were produced by AI agents (Claude, by Anthropic) working for Quantavane
under Arhan Canli's direction. Bounds marked as ours are verified by two independent programs and an internal referee;
they are not yet peer reviewed. The holder column restates what the cited pages print; it is not an independent
check of priority.
