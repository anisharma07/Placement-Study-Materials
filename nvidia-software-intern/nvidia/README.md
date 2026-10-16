# NVIDIA Compiler Verification Intern: one-day preparation manual

Study material for the **Software Engineering Intern, Compiler Verification team** role (winter internship and full-time
conversion, campus drive; stipend INR 100,000 per month; Pune and Bengaluru; online assessment on HackerRank with aptitude
and technical sections covering C/C++, Python, ML exposure and compilers).

| File | What it is |
|---|---|
| `theory-nvidia.pdf` | The compiled manual (about 260 pages, A4). Start here. |
| `theory-nvidia.tex` | The complete LaTeX source, a single self-contained file (compile with `pdflatex`, three passes). |
| `role.txt` | The role description and the notice table as supplied (the original `role.txt` was not in the repository, so it was recreated from the text you pasted). |

## How to use it in one day

Open the PDF and read *How to use this manual*, then follow the hour-by-hour plan (Chapter 3). Every section title carries a
priority mark: three stars are must-master, two should-know, one skim. The three-star material alone is a complete,
passable preparation; Chapter 3 also has a six-hour fast path. The last twenty minutes belong to Appendix A, the Top-40 card.

## What is inside

| Part | Chapters |
|---|---|
| I Orientation | 1 role decoder, 2 exam intelligence (what candidates reported, with sources), 3 the 24-hour plan and OA tactics |
| II Programming foundations | 4 C, 5 C++, 6 Python, 7 coding-round patterns with the reported problems solved |
| III Compiler theory | 8 front end and lexing, 9 parsing, 10 semantic analysis / IR / SSA, 11 optimisation, code generation, linking |
| IV LLVM and NVIDIA toolchain | 12 LLVM, 13 lit and FileCheck, 14 nvcc / NVVM / PTX / SASS, 15 CUDA and GPU architecture, 16 parallel programming |
| V Verification and automation | 17 oracles, differential and metamorphic testing, fuzzing, reduction, bisection; 18 a mini verification framework in Python |
| VI ML, CS fundamentals, aptitude | 19 ML exposure and ML compilers, 20 numbers / logic / architecture / OS / databases / networks, 21 aptitude and puzzles with a 30-question mock test |
| VII Question bank and playbook | 22 coverage map of reported questions and a full mock OA, 23 interview playbook, flashcards and behavioural answers; appendices: Top-40 card, cheat sheets, glossary, reading list, source listings |

## What "verified" means here

* Every C, C++ and Python snippet was **compiled and run while the document was built**; the yellow output boxes are the real
  captured output, never typed by hand. The build cache and the assembler are not part of this folder; the `.tex` file already
  contains the captured outputs.
* Formulas, puzzle answers, the mock-test answer keys (Chapters 21 and 22) and the compiler/OS/ML computations are recomputed by
  code (brute force, exact fractions, search programs); the printed check output is in the chapters.
* GPU material: no CUDA SDK or GPU was available. Kernels were compiled to PTX with Clang's NVPTX back end and *executed* only
  through a CPU emulator (Chapter 15); PTX was not assembled by `ptxas`. Timings in the book depend on the build machine.

## Honest limits

* **Previous-year questions are anecdotes.** NVIDIA does not publish its OA. Chapter 2 lists candidate reports (GeeksforGeeks,
  Glassdoor, Jointaro, LeetCode Discuss, placement blogs, job postings) that were found through web search and read as
  search-engine summaries; the research sandbox could not open most of those sites, and Reddit could not be searched at all.
  Open the numbered links and search r/developersIndia and r/Btechtards yourself. Reported counts (bugs found by tools, etc.) are
  the papers' headline numbers.
* Formats change by team, city and year. Follow the instructions in your official invitation.
* This is unofficial study material and is not affiliated with or endorsed by NVIDIA.

## Rebuilding the PDF

```
pdflatex theory-nvidia.tex && pdflatex theory-nvidia.tex && pdflatex theory-nvidia.tex
```

A recent TeX Live (2022 or later) with the usual packages (`tcolorbox`, `listings`, `tikz`, `xltabular`, `fancyhdr`, `titlesec`,
`needspace`, `enumitem`, `booktabs`, `microtype`, `lmodern`) is enough; no shell escape is needed.
