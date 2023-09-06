# Latex

Markup language to take math note.

## Operation

| operation | description      |
|-----------|------------------|
| \frac{}{} | fraction         |
| \pi       | pi               |
| < >       | greater / lesser |
| \subset   | ⊂                |
| \supset   | ⊃                |
| \subseteq | ⊆                |
| \supseteq | ⊇                |
| \int      | ∫                |
| \oint     | ∮                |
| \sum      | ∑                |
| \prod     | ∏                |

Greek letter: \alpha \beta \gamma \rho \sigma \delta \epsilon


## Formula

Wrap the formula into `$` for a inline formula (fit in the text)
Wrap it in `\[ \]` to have it with a line break.

```latex
$e^{i\pi}+1=0$

\[
e^{i\pi}+1=0
\]
```
## Table

instead of {c c c} you can replace the c with r or l to right or left aline. Add border like so: {|c|c|c|}

\begin{center}
\begin{tabular}{c c c}
 cell1 & cell2 & cell3 \\ 
 cell4 & cell5 & cell6 \\  
 cell7 & cell8 & cell9    
\end{tabular}
\end{center}

## other

Auto size bracket: put \left and \right before the bracket.

\left(frac{1}{\pi}\right)^n

## Text

| syntax           | description    | example |
|------------------|----------------|---------|
| \textbf{text}    | bold text      |         |
| \underline{text} | underline text |         |
| \textit{text}    | italic text    |         |

## List

1. undordered lists:
\begin{itemize}
  \item First bullet point
\end{itemize}

2. ordered lists
\begin{enumerate}
  \item First bullet point
\end{enumerate}

## Document set up

Wrap everything into:

```latex
\documentClass{article}
\usepackage[utf8]{inputenc}

\title{my document}
\author{me}
\date{May 2023}

\begin{document}
\maketitle

\chapter{First Chapter}
\section{Introduction}

...

\end{document}
```
