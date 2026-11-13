# Beamer

Beamer is a LaTeX class used for making presentations (slides). Instead of PowerPoint, you write LaTeX code and it generates a PDF presentation.

## Basic Structure

```latex
\documentclass{beamer}
\begin{document}

\begin{frame}{Title of Slide}
Content goes here
\end{frame}

\end{document}
```

Each slide is a `frame` environment. You give it a title in curly braces.

## Title Slide

```latex
\title{My Presentation}
\author{Your Name}
\institute{MNIT Jaipur}
\date{\today}

\begin{frame}
\titlepage
\end{frame}
```

## Adding Content to Slides

You can use all normal LaTeX inside frames - lists, math, images, tables etc.

```latex
\begin{frame}{Key Points}
\begin{itemize}
\item First point
\item Second point
\item Third point
\end{itemize}
\end{frame}
```

## Themes

Beamer comes with built-in themes that change the look of your slides:

```latex
\usetheme{Madrid}
```

Some popular themes: `Madrid`, `Berlin`, `Warsaw`, `CambridgeUS`, `AnnArbor`

You can also change the color theme:
```latex
\usecolortheme{dolphin}
```

## Overlays and Animations

Beamer lets you reveal content step by step using `\pause` or overlay specs:

```latex
\begin{frame}{Step by Step}
\begin{itemize}
\item<1-> This shows first
\item<2-> This shows second
\item<3-> This shows third
\end{itemize}
\end{frame}
```

Or simply use `\pause`:
```latex
\begin{frame}{With Pause}
First point
\pause
Second point
\pause
Third point
\end{frame}
```

## Blocks

Beamer has special block environments for highlighting content:

```latex
\begin{frame}{Blocks}
\begin{block}{Definition}
A block with a blue title bar
\end{block}

\begin{alertblock}{Warning}
A red highlighted block
\end{alertblock}

\begin{exampleblock}{Example}
A green example block
\end{exampleblock}
\end{frame}
```

## Two Column Layout

```latex
\begin{frame}{Two Columns}
\begin{columns}
\column{0.5\textwidth}
Left side content

\column{0.5\textwidth}
Right side content
\end{columns}
\end{frame}
```

## Adding Figures

Same as regular LaTeX but without the float:

```latex
\begin{frame}{Image Slide}
\centering
\includegraphics[width=0.6\textwidth]{image.png}
\end{frame}
```

## Table of Contents

```latex
\begin{frame}{Outline}
\tableofcontents
\end{frame}
```

Use `\section{}` and `\subsection{}` before frames to organize the presentation structure.

## Why Beamer over PowerPoint

- Consistent formatting throughout
- Math equations look much better
- Version control friendly (its just text files)
- Can reuse LaTeX content directly from papers
- PDF output works everywhere
