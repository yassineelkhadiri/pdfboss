# Evidence for pdfboss#52 / PR #53

Before/after renders for the `/Separation` tint-transform fix. "Before" is
`main`, "after" is the PR branch; both from a release `maturin build` of the
same tree, rendered through `pdfboss.Document(...)[0].render(fonts="full")`.

| file | what it shows | mean luma before → after |
|---|---|---|
| `01-minimal-repro.png` | the 686-byte synthetic case from the issue | 0.0 → 248.0 |
| `02-pantone-menu.png` | a print-origin menu, full-bleed Pantone spot fill | 0.5 → 240.2 |
| `03-benchmark-excluded.png` | the corpus file `benchmarks/bench_render.py` excluded on main for `pdfboss ink 99.99% vs median 2.96%` | 2.3 → 208.8 |

`separation-tint.pdf` is the synthetic reproducer itself (686 bytes).
