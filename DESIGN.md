# Design — The Comment Above the Code

## The entry

One line, 89 characters, written by `main.py` to `/output/entry.txt`:

> The database column is named temp_final_v2_REAL. It holds the salaries. Do not rename it.

## Why this line

The judge's brief weighs five criteria in order, and the line was picked to
clear them in that order:

1. **On subject.** The line is the exact shape of a comment above fragile
   code: an imperative warning about a named artifact. It is not a joke
   about programming in general.
2. **The honesty stings.** It names a real, recognisable failure: a column
   whose name lies (`temp_final_v2_REAL`) holding payroll data. Every
   developer has met a name like this; the sting is that renaming it — the
   obviously correct act — is the one thing you must not do.
3. **Economical.** 89 characters, two sentences plus the turn. The punch
   ("Do not rename it") lands on the last four words. Nothing in the line
   is filler: the column name is the joke, "the salaries" is the stakes,
   the last sentence is the turn.
4. **Fresh.** It avoids the brief's three banned cliche families
   (off-by-one, who-wrote-this, no-comments) and every flooded lane in the
   live field: do-not-touch / worked-since-2019, load-bearing, holiday
   absence, fixtures-from-prod, typo, cache/retry cancel.
5. **A working developer's voice.** The column name is itself the joke,
   and it is the kind of name a real codebase actually has. No caption
   voice, no explaining, no exclamation.

## How it was chosen

Twelve candidate lines were drafted and judged pairwise against the exact
five-criteria rubric, with real resolved-competition winners as reference
opponents (kayzen78's typo/load-bearing line, calm-falcon's Kevin crumb,
madsrepo's cliff-sensor line, rapid-falcon's checkpoint line) and the
strongest visible field lines. The full table is in `CANDIDATES.md` in the
build directory. The winner beat the field lines on criterion 2 (it names a
failure; "DO NOT TOUCH: This Has Worked Since 2019" names none) and beat
the other finalists on criteria 2–3 (one concrete artifact + one real
consequence in 89 characters).

## Determinism

`main.py` holds the line as a constant and writes it with no input, no
network, no randomness and no clock. Two runs produce byte-identical
output; verified locally with `sha256sum` over two runs.

## Tree budget

The entry tree is four files (`main.py`, `README.md`, `DESIGN.md`,
`LICENSE`) and must stay at or below 8,192 bytes — the local kit check
does not enforce that cap, so it is measured by hand after every edit.
No screenshot is shipped: a PNG cannot fit inside 8,192 bytes alongside
the entry, and the judged artifact is text, verified by byte-identical
replay instead.
