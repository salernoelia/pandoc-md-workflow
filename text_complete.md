---
title: "Advanced Pandoc and LaTeX Features"
author: "Your Name"
date: "May 13, 2025"
abstract: "This document demonstrates key features available when using Pandoc with LaTeX."
keywords: [pandoc, latex, markdown, academic writing]
documentclass: article
papersize: a4
fontsize: 12pt
mainfont: "DejaVu Serif"
sansfont: "DejaVu Sans"
monofont: "DejaVu Sans Mono"
bibliography: references.bib
csl: ieee.csl
link-citations: true
colorlinks: true
toc: true
toc-depth: 3
numbersections: true
header-includes:
  - \usepackage{booktabs}
  - \usepackage{multirow}
  - \usepackage{xcolor}
  - \usepackage{soul}
  - \usepackage{graphicx}
  - \usepackage{float}
  - \usepackage{amsthm}
  - \newtheorem{theorem}{Theorem}
---

\newpage

# Introduction

This document showcases Pandoc and LaTeX features for academic writing. Cross-references help navigate complex documents [@knuthArtComputerProgramming1997]. Multiple citations can be grouped together [@knuthArtComputerProgramming1997].

# Text Formatting

Basic markdown supports **bold**, _italic_, and **_bold italic_** text. LaTeX extensions allow for \underline{underlined text}, \textsc{small caps}, and \texttt{monospaced text}.

You can also include ~~strikethrough~~ text and ^superscript^ or ~subscript~ elements.

\hl{Highlighted text} requires the soul package.

# Lists and Definition Lists

## Bullet Lists

- First-level item
  - Second-level item
    - Third-level item
  - Another second-level item

## Numbered Lists

1. First item
2. Second item
   1. Sub-item 2.1
   2. Sub-item 2.2
3. Third item

## Definition Lists

Term 1
: Definition 1

Term 2
: Definition 2a
: Definition 2b

# Mathematical Content {#sec:math}

## Inline Mathematics

The quadratic formula is $x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$ where $a \neq 0$.

## Display Equations

Equation \ref{eq:maxwell1} shows Maxwell's first equation:

\begin{equation}
\nabla \cdot \mathbf{E} = \frac{\rho}{\varepsilon_0}
\label{eq:maxwell1}
\end{equation}

Equation systems can be aligned:

\begin{align}
\frac{d}{dx}x^n &= nx^{n-1} \\
\int x^n dx &= \frac{x^{n+1}}{n+1} + C \quad \text{for } n \neq -1
\end{align}

## Matrix Notation

$$
\mathbf{A} =
\begin{pmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn}
\end{pmatrix}
$$

# Figures and Tables

## Figures with Captions

![Example figure with caption. This figure is referenced as Figure \ref{fig:example}.](images/markdown-plugin.png){#fig:example width=80%}

As shown in Figure \ref{fig:example}, images can be referenced.

## Tables

| Right | Left | Default | Center |
| ----: | :--- | ------- | :----: |
|    12 | 12   | 12      |   12   |
|   123 | 123  | 123     |  123   |
|     1 | 1    | 1       |   1    |

Table: Example table with alignment. {#tbl:simple}

As seen in Table \ref{tbl:complex}, we can create complex tables.

# Code Blocks

## Inline Code

Use `print("Hello, world!")` for a simple Python example.

## Code Blocks with Syntax Highlighting

```python
def factorial(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * factorial(n-1)

result = factorial(5)
print(f"5! = {result}")
```

# Cross-References

As mentioned in Section \ref{sec:math}, equations can be referenced.

# Footnotes and Margin Notes

Regular footnotes[^1] are supported.

[^1]: This is a footnote with additional details.

# Block Quotes

> This is a blockquote.
>
> It can span multiple paragraphs.
>
> > Nested blockquotes are also possible.

# Custom LaTeX Environments

\begin{theorem}
For all $n > 0$, $\sum_{i=1}^{n} i = \frac{n(n+1)}{2}$
\end{theorem}

\begin{proof}
Mathematical induction can be used.
\end{proof}

# Citations and Bibliography

Different citation styles include parenthetical [@knuthArtComputerProgramming1997], textual @mejia-hernandezSmartphoneApplicationsEvaluation2018, and with page numbers [@knuthArtComputerProgramming1997, p. 42].

# References

```

```
