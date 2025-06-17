# eoldef

eoldef: define commands which absorb the whole source line as arguments.

Usage: `\eoldef <control sequence> <parameter text> { <replacement text> }`
defines a control sequence that is delimited by the end-of-line in addition to
the specified parameter text. This enables less verbose markdown-like syntax.

For instance, `\eoldef\test#1:#2{}` and

    \test abc:def

will give `#1` = `abc`, `#2` = `def`.

`\eolgdef` is the `\global` variant to `\eoldef`.

Like `\verb|...|`, `\eoldef`'d commands may generally not be used as part of
another command's argument as it changes catcodes.
However, if you must use it in environments where catcodes are frozen, you
may follow the command with a braced argument, eg. `\test{#1:#2}` using the
previous example.

This package may be used in plain TeX or LaTeX by `\input{eoldef}`.

Copyright (C) 2025 plante
Version 1.0a
This package is relased under the LaTeX Project Public License (LPPL) 1.3c.
