# LaTeX Template Examples

This document provides common LaTeX code snippets for use with the NUS Report Template.

## Table of Contents
- [Sections and Subsections](#sections-and-subsections)
- [Figures](#figures)
- [Tables](#tables)
- [Equations](#equations)
- [Lists](#lists)
- [References and Citations](#references-and-citations)
- [Code Listings](#code-listings)

## Sections and Subsections

```latex
\section{Introduction}
Your introduction text here.

\subsection{Background}
Background information.

\subsubsection{Historical Context}
More detailed information.

\section*{Unnumbered Section}
This section won't be numbered.
```

## Figures

### Single Figure
```latex
\begin{figure}[h!]
\centering
\includegraphics[width=0.6\textwidth]{figures/your-image.png}
\caption{Description of your figure.}
\label{fig:example}
\end{figure}
```

### Multiple Figures Side by Side
```latex
\begin{figure}[h!]
\centering
\begin{minipage}{0.45\textwidth}
    \centering
    \includegraphics[width=\textwidth]{figures/image1.png}
    \caption{First image}
    \label{fig:first}
\end{minipage}
\hfill
\begin{minipage}{0.45\textwidth}
    \centering
    \includegraphics[width=\textwidth]{figures/image2.png}
    \caption{Second image}
    \label{fig:second}
\end{minipage}
\end{figure}
```

### Subfigures
```latex
\begin{figure}[h!]
\centering
\subfigure[First subfigure]{
    \includegraphics[width=0.45\textwidth]{figures/sub1.png}
    \label{fig:sub1}
}
\subfigure[Second subfigure]{
    \includegraphics[width=0.45\textwidth]{figures/sub2.png}
    \label{fig:sub2}
}
\caption{Main caption for both subfigures}
\label{fig:subfigures}
\end{figure}
```

## Tables

### Simple Table
```latex
\begin{table}[h!]
\centering
\caption{A simple table}
\label{tab:simple}
\begin{tabular}{|c|c|c|}
\hline
\textbf{Column 1} & \textbf{Column 2} & \textbf{Column 3} \\
\hline
Data 1 & Data 2 & Data 3 \\
Data 4 & Data 5 & Data 6 \\
\hline
\end{tabular}
\end{table}
```

### Table with Different Column Alignments
```latex
\begin{table}[h!]
\centering
\caption{Table with mixed alignments}
\label{tab:aligned}
\begin{tabular}{|l|c|r|}
\hline
\textbf{Left} & \textbf{Center} & \textbf{Right} \\
\hline
Left aligned & Centered & Right aligned \\
Text & 123 & 45.67 \\
\hline
\end{tabular}
\end{table}
```

### Table with Merged Cells
```latex
\begin{table}[h!]
\centering
\caption{Table with merged cells}
\label{tab:merged}
\begin{tabular}{|c|c|c|}
\hline
\multicolumn{2}{|c|}{\textbf{Merged Header}} & \textbf{Column 3} \\
\hline
Data 1 & Data 2 & Data 3 \\
\multirow{2}{*}{Merged Rows} & Data 5 & Data 6 \\
 & Data 8 & Data 9 \\
\hline
\end{tabular}
\end{table}
```

## Equations

### Inline Equation
```latex
The equation $E = mc^2$ is Einstein's famous formula.
```

### Numbered Equation
```latex
\begin{equation}
F = ma
\label{eq:newton}
\end{equation}
```

### Unnumbered Equation
```latex
\[
\int_{0}^{\infty} e^{-x} dx = 1
\]
```

### Multiple Equations
```latex
\begin{align}
a &= b + c \label{eq:first} \\
d &= e - f \label{eq:second} \\
g &= h \times i \label{eq:third}
\end{align}
```

### Equation Array
```latex
\begin{equation}
\begin{array}{rcl}
f(x) &=& x^2 + 2x + 1 \\
     &=& (x + 1)^2
\end{array}
\end{equation}
```

## Lists

### Bulleted List
```latex
\begin{itemize}
    \item First item
    \item Second item
    \item Third item
        \begin{itemize}
            \item Nested item 1
            \item Nested item 2
        \end{itemize}
\end{itemize}
```

### Numbered List
```latex
\begin{enumerate}
    \item First step
    \item Second step
    \item Third step
        \begin{enumerate}
            \item Sub-step A
            \item Sub-step B
        \end{enumerate}
\end{enumerate}
```

### Custom Numbered List
```latex
\begin{enumerate}[a)]
    \item Item a
    \item Item b
    \item Item c
\end{enumerate}
```

### Description List
```latex
\begin{description}
    \item[Term 1] Definition of term 1
    \item[Term 2] Definition of term 2
    \item[Term 3] Definition of term 3
\end{description}
```

## References and Citations

### Citing References
```latex
According to Smith \cite{Smith2020}, the results are significant.
Multiple citations can be grouped \cite{Smith2020, Jones2021, Brown2022}.
```

### Cross-Referencing
```latex
% Reference a figure
As shown in Figure \ref{fig:example}...

% Reference a table
The data in Table \ref{tab:results} indicates...

% Reference an equation
Using equation \eqref{eq:newton}, we can derive...

% Reference a section
As discussed in Section \ref{sec:introduction}...
```

### Adding Bibliography Entries
Add to `mybib.bib`:
```bibtex
@article{Smith2020,
    author = {Smith, John and Doe, Jane},
    title = {An Important Study},
    journal = {Journal of Important Things},
    year = {2020},
    volume = {15},
    number = {3},
    pages = {123--145}
}

@book{Jones2021,
    author = {Jones, Bob},
    title = {The Complete Guide},
    publisher = {Academic Press},
    year = {2021},
    edition = {3rd}
}

@inproceedings{Brown2022,
    author = {Brown, Alice},
    title = {New Developments},
    booktitle = {Proceedings of the Conference},
    year = {2022},
    pages = {45--52}
}
```

## Code Listings

### Inline Code
```latex
Use the \texttt{print()} function to display output.
```

### Code Block (requires listings package)
```latex
\begin{lstlisting}[language=Python, caption=Python example]
def hello_world():
    print("Hello, World!")
    
if __name__ == "__main__":
    hello_world()
\end{lstlisting}
```

### Code from File
```latex
\lstinputlisting[language=Python, caption=Code from file]{code/example.py}
```

## Mathematical Symbols and Notations

The template includes custom notations in `notation.tex`:

```latex
% Vectors and matrices
\vec{x}        % Bold vector
\mat{A}        % Bold matrix

% Number sets
\R             % Real numbers
\Z             % Integers
\N             % Natural numbers
\C             % Complex numbers
\Q             % Rational numbers

% Operations
\tr            % Trace
\inv           % Inverse (use as A\inv)
\T             % Transpose (use as A\T)

% Probability
\E             % Expectation
\var           % Variance
\gauss{\mu}{\sigma^2}  % Gaussian distribution
```

## Boxes and Highlighting

### Text Box
```latex
\begin{boxit}
Important information goes here.
\end{boxit}
```

### Colored Text (from notation.tex)
```latex
\blue{This text is blue}
\red{This text is red}
\green{This text is green}
```

## URLs and Hyperlinks

```latex
% URL
Visit \url{https://www.example.com}

% Hyperlink with custom text
See \href{https://www.example.com}{this website} for more info.
```

## Footnotes

```latex
This is some text\footnote{This is a footnote explaining the text.} with a footnote.
```

## Tips

1. **Always compile twice** after adding references or citations
2. **Use labels consistently**: prefix with type (e.g., `fig:`, `tab:`, `eq:`, `sec:`)
3. **Keep figure files organized** in the `figures/` directory
4. **Test incrementally** - add one element at a time and compile
5. **Use comments** (`%`) to explain complex LaTeX code

## Need More Help?

- LaTeX Wikibook: https://en.wikibooks.org/wiki/LaTeX
- Overleaf Documentation: https://www.overleaf.com/learn
- TeX StackExchange: https://tex.stackexchange.com/

---

Remember to check [TROUBLESHOOTING.md](TROUBLESHOOTING.md) if you encounter any issues!
