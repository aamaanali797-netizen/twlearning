# LaTeX

LaTeX is a document preparation system used for writing technical and scientific documents. Unlike Word, you write code which then gets compiled into a PDF.

## Basic Structure

Every LaTeX document follows this structure:

```latex
\documentclass[12pt,a4paper]{article}
\begin{document}
Your content here
\end{document}
```

The `\documentclass` sets the type of document. Common classes are:
- `article` - for papers and short documents
- `report` - for longer documents with chapters
- `book` - for books and theses
- `beamer` - for presentations
- `letter` - for formal letters

## Document Preamble

Everything between `\documentclass` and `\begin{document}` is the preamble. This is where you load packages and set configurations.

```latex
\usepackage{graphicx}    % for images
\usepackage{amsmath}      % for math
\usepackage{geometry}     % for margins
\geometry{left=2.5cm, right=2.5cm, top=2.5cm, bottom=2.5cm}
```

## Text Formatting

```latex
\textbf{Bold text}
\textit{Italic text}
\underline{Underlined text}
\texttt{Monospace text}
```

## Font Sizes

LaTeX has built-in size commands:

```latex
{\tiny Tiny}
{\small Small}
{\normalsize Normal}
{\large Large}
{\Large Larger}
{\huge Huge}
```

## Text Alignment

```latex
\begin{flushleft}
Left aligned text
\end{flushleft}

\begin{center}
Centered text
\end{center}

\begin{flushright}
Right aligned text
\end{flushright}
```

## Lists

Three types of lists:

```latex
% Bulleted list
\begin{itemize}
\item Apple
\item Mango
\end{itemize}

% Numbered list
\begin{enumerate}
\item First
\item Second
\end{enumerate}

% Description list
\begin{description}
\item[CPU] Processor
\item[RAM] Memory
\end{description}
```

## Math in LaTeX

Inline math uses `$...$` or `\(...\)`. Display math uses `\[...\]`.

```latex
Inline: $a + b = c$

Display:
\[
E = mc^2
\]
```

Some common math symbols:
- `$x^2$` for superscript
- `$x_i$` for subscript
- `$\frac{a}{b}$` for fractions
- `$\sqrt{x}$` for square root
- `$\sum_{i=1}^{n} x_i$` for summation
- `$\int_{0}^{1} x\,dx$` for integrals
- Greek letters: `$\alpha, \beta, \gamma, \pi$`

## Tables

Tables use the `tabular` environment:

```latex
\begin{tabular}{|c|c|c|}
\hline
Name & Age & City \\
\hline
Alice & 20 & Jaipur \\
Bob & 21 & Delhi \\
\hline
\end{tabular}
```

- `c` = center, `l` = left, `r` = right alignment
- `|` adds vertical lines
- `\hline` adds horizontal lines
- `&` separates columns, `\\` ends a row

For combining rows and columns:
- `\multicolumn{3}{|c|}{Title}` merges 3 columns
- `\multirow{2}{4em}{Text}` merges 2 rows (needs `multirow` package)

You can also change row height with `\renewcommand{\arraystretch}{1.5}` and column spacing with `\setlength{\tabcolsep}{18pt}`.

## Figures

```latex
\usepackage{graphicx}

\begin{figure}[h]
\centering
\includegraphics[width=0.5\textwidth]{image.jpg}
\caption{My figure caption}
\label{fig:myfig}
\end{figure}
```

Position options: `h` (here), `t` (top), `b` (bottom), `p` (separate page), `!` (override).

For side by side images, use `minipage`:

```latex
\begin{minipage}{0.45\textwidth}
\includegraphics[width=\linewidth]{imageA}
\end{minipage}
\quad
\begin{minipage}{0.45\textwidth}
\includegraphics[width=\linewidth]{imageB}
\end{minipage}
```

## Colors

Need to load `\usepackage{xcolor}` first.

```latex
\textcolor{red}{Red text}
\colorbox{yellow}{Highlighted text}
\fcolorbox{red}{white}{Bordered box}
```

You can define custom colors too:
```latex
\definecolor{myblue}{RGB}{10,60,200}
```

## Cross References

```latex
\section{Introduction}
\label{sec:intro}

See Section~\ref{sec:intro} on page~\pageref{sec:intro}.
```

Works with figures, tables, and equations too.

## Bibliography

```latex
This is explained in \cite{lamport}.

\begin{thebibliography}{9}
\bibitem{lamport}
Leslie Lamport, LaTeX: A Document Preparation System.
\end{thebibliography}
```

## Page Styles

- `\pagestyle{plain}` - page number at bottom (default)
- `\pagestyle{headings}` - chapter/section in header
- `\pagestyle{empty}` - no header or footer

For custom headers use the `fancyhdr` package:

```latex
\usepackage{fancyhdr}
\pagestyle{fancy}
\fancyhead[L]{Left Header}
\fancyhead[R]{Right Header}
\fancyfoot[C]{\thepage}
```

## Useful Environments

```latex
% Verbatim - prints text as-is
\begin{verbatim}
code here
\end{verbatim}

% Quote
\begin{quote}
This is a quoted paragraph.
\end{quote}
```

## Hyphenation

LaTeX auto-hyphenates words. You can specify break points manually:
```latex
micro\-processor
```
