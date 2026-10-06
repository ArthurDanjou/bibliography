# Bibliography

BibTeX references for research on Byzantine-robust distributed and federated learning, intended for use with **biblatex and biber**.

This repository serves as the shared bibliography for my thesis, research papers, and reports.

References are split by category. Each entry belongs to its **primary category**; secondary roles are documented in trailing `Roles:` comments. References supporting several categories are stored once and cited using the same key throughout the thesis.

## Files

| File | Category | Contents |
|---|---|---|
| [`protocols.bib`](protocols.bib) | [P] Protocols | Seminal protocols reproduced by the simulation layer: NIPS 2017, ICML 2018, and ICML 2023 MoNNA, plus related protocol context. |
| [`aggregation.bib`](aggregation.bib) | [A] Aggregation | Sources of implemented aggregation rules and pre-aggregation techniques, including future work on bucketing and client weighting. |
| [`attacks.bib`](attacks.bib) | [X] Attacks | Sources of implemented attacks, including ALIE and SignFlip, plus related poisoning, backdoor, and dataset ownership verification research. FullGradientNegation and SmallPerturbation are defined in `elmhamdi2018hidden`, stored in `protocols.bib`. |
| [`theory.bib`](theory.bib) | [T] Theory | Theoretical foundations, resilience guarantees, and supporting references for the introduction and thesis discussions. |
| [`libraries.bib`](libraries.bib) | [L] Libraries | The five systems compared with Krum in Chapter 7 and their companion papers: ByzFL, FedLab, Blades, FL-Byzantine-Library, and ByzPy. |

## Usage

Place this repository in your LaTeX project as `biblio/`, then declare each file in the preamble of `main.tex`:

```tex
\usepackage[backend=biber]{biblatex}

\addbibresource{biblio/protocols.bib}
\addbibresource{biblio/aggregation.bib}
\addbibresource{biblio/attacks.bib}
\addbibresource{biblio/theory.bib}
\addbibresource{biblio/libraries.bib}
```

Cite entries by their existing keys and print the bibliography where needed:

```tex
\cite{blanchard2017machine}
\printbibliography
```

Adjust the resource paths if the files are stored elsewhere. Compile the document using your LaTeX engine, run `biber main`, then run the LaTeX engine twice more to resolve citations and cross-references.

## Maintenance rules

- **Never rename existing citation keys.** They are cited throughout the thesis.
- Keep citation keys globally unique across all five files. Review biber warnings for duplicate keys.
- Store each entry in its primary category only.
- Document secondary roles in trailing `Roles:` comments after the entry.
- Declare each bibliography file separately with `\addbibresource` in `main.tex`.
