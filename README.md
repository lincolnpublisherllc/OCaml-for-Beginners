README (summary outside the ZIP)
What’s inside

One folder per chapter: chapter01 … chapter12

Inside each chapter are .ml source files.

Where the book named a file inside a comment header like (* hello.ml *), I kept that filename.

If a block didn’t have a name, I assigned example_XX.ml in order of appearance.

REPL transcripts (lines that start with #) are saved as repl_XX.txt for reference.

File counts by chapter

chapter01: 16 files

chapter02: 10 files

chapter03: 20 files

chapter04: 34 files

chapter05: 30 files

chapter06: 31 files

chapter07: 34 files

chapter08: 34 files

chapter09: 33 files

chapter10: 46 files

chapter11: 19 files

chapter12: 49 files

How I extracted the code

Parsed the book, detected OCaml blocks using common patterns: let, match, print_endline, Printf.printf, String.*, List.*, Array.*, Hashtbl.*, for/while, read_line, and (* … *) comments.

Ignored shell/build lines like ocamlc, ocamlopt, dune, opam, brew, etc., to keep the archive focused on source code.

Grouped consecutive code lines into a single file per block.

Running examples quickly

You can compile a single file with the bytecode compiler:

ocamlc file.ml -o app && ./app


Or use native:

ocamlopt file.ml -o app && ./app


If a file uses multiple modules, compile them in one command (order matters), for example:

ocamlc -w A -warn-error A util.ml main.ml -o app_bc && ./app_bc


For Dune-based snippets, place the .ml in a Dune project as shown in Chapter 2:

opam install dune
dune init proj demo && cd demo
# put code into bin/main.ml
dune exec demo

Notes and edge cases

A few blocks in the book are REPL-only demonstrations. Those are stored as repl_XX.txt since they aren’t standalone .ml files.

“Expected output” shown in the book isn’t duplicated as separate files; when useful, the code includes comments indicating expected output.

Exercises and “Try It Yourself” prompts that didn’t include full code aren’t added, since they weren’t actual code blocks.
