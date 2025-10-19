# NUS Report Template-LaTex


[![License](https://img.shields.io/badge/License-CC%20BY--NC--SA%203.0-blue.svg)](https://creativecommons.org/licenses/by-nc-sa/3.0/)

⭐ **Star this repository if you find it useful!** 😉

[View PDF example here](./NUS_Report_Template.pdf)

<img src="./template.png" style="zoom:60%">

## 📌 Introduction

This template is modified from the original template by [Jean-Pierre Hicke](https://www.overleaf.com/latex/templates/university-of-waterloo-me303-report-format/fvcvbdbfpmmt)

### ✨ Key Features

- **NUS Branding**: Includes official NUS logo and customized title page
- **Professional Layout**: Two-sided letter paper format with 12pt font
- **Multi-Author Support**: Easy configuration for team projects
- **Comprehensive Math Support**: Extensive mathematical notation and theorem environments
- **Bibliography Management**: BibTeX integration with multiple citation styles
- **Cross-Referencing**: Automatic numbering for equations, figures, sections, and citations
- **Customizable Headers/Footers**: Professional page formatting
- **Code Highlighting**: Ready for technical content presentation
- **Hyperlinks**: PDF hyperlinks with professional black styling

## 📋 Table of Contents

- [Quick Start](#-quick-start)
- [File Structure](#-file-structure)
- [Customization Guide](#-customization-guide)
- [Mathematical Notation](#-mathematical-notation)
- [Bibliography Management](#-bibliography-management)
- [Tips and Best Practices](#-tips-and-best-practices)
- [Troubleshooting](#-troubleshooting)
- [Updates](#-updates)

## 📦 Quick Start

### Method 1: Using Overleaf (Recommended)

1. Download the `Source code.zip` from the [releases page](../../releases)
2. Go to [Overleaf](https://www.overleaf.com)
3. Click on **New Project** → **Upload Project**
4. Upload the downloaded zip file
5. Start editing!

### Method 2: Local LaTeX Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/Yuxiang-Xiao/NUS-Report-Template-LaTex.git
   cd NUS-Report-Template-LaTex
   ```

2. Compile the document:
   ```bash
   pdflatex main.tex
   bibtex main
   pdflatex main.tex
   pdflatex main.tex
   ```

3. Or use your preferred LaTeX editor (TeXstudio, TeXmaker, VS Code with LaTeX Workshop, etc.)

## 📁 File Structure

```
NUS-Report-Template-LaTex/
├── main.tex              # Main document - start here
├── titlepage.tex         # Title page with NUS branding
├── includes.tex          # Package imports and configurations
├── notation.tex          # Mathematical notation and custom macros
├── mybib.bib            # Bibliography database (BibTeX format)
├── dsfont.sty           # Custom font package
├── kpfonts.sty          # Custom font package
├── README.md            # This file
└── figures/             # Directory for images
    ├── nus.jpg          # NUS logo
    └── goose.png        # Sample figure
```

### File Descriptions

- **`main.tex`**: The primary document where you define report metadata and write your content
- **`titlepage.tex`**: Generates the title page with NUS logo, course info, and author details
- **`includes.tex`**: Contains all package imports, page layout settings, and document styling (257 lines)
- **`notation.tex`**: Defines mathematical shortcuts and custom commands for equations
- **`mybib.bib`**: Bibliography database - add your references here in BibTeX format
- **`.sty files`**: Custom style packages for fonts

## ⚙️ Customization Guide

### 1. Basic Information (in `main.tex`)

Edit the following commands at the top of `main.tex`:

```latex
\newcommand{\reporttitle}{Project 1: Your Project Name}
\newcommand{\reportauthorOne}{Student 1}
\newcommand{\cidOne}{your id number}
\newcommand{\reportauthorTwo}{Student 2}
\newcommand{\cidTwo}{your id number}
\newcommand{\reporttype}{Coursework}
\bibliographystyle{plain}  % Citation style
```

### 2. Course Information (in `titlepage.tex`)

Modify the course details:

```latex
\textbf{\textsc{\Large ME611 - Mechatronics}}\\[1.0cm] 
\textsc{\Large National University of Singapore}\\[0.5cm] 
\textsc{\large Department of Mechanical Engineering}\\[0.95cm]
```

### 3. Table of Contents

Uncomment these lines in `main.tex` to add a table of contents:

```latex
\tableofcontents
\newpage
```

### 4. Adding More Authors

For projects with more than 2 authors, edit `titlepage.tex`:

```latex
\begin{flushleft} \large
\textit{Authors:}\\
\reportauthorOne~(ID: \cidOne)\\
\reportauthorTwo~(ID: \cidTwo)\\
Author Three~(ID: AXXXXXXXX)\\  % Add more as needed
\end{flushleft}
```

## 📐 Mathematical Notation

The template includes extensive mathematical notation support via `notation.tex`:

### Vectors and Matrices
```latex
\vec{x}          % Bold vector
\mat{A}          % Bold matrix
\T               % Transpose: A^\top
\inv             % Inverse: A^{-1}
```

### Number Sets
```latex
\R               % Real numbers ℝ
\N               % Natural numbers ℕ
\Z               % Integers ℤ
\Q               % Rational numbers ℚ
\C               % Complex numbers ℂ
```

### Linear Algebra
```latex
\tr              % Trace
\det{A}          % Determinant
\rank            % Rank
\dim             % Dimension
\kernel          % Kernel/nullspace
\img             % Image
\diag{x}         % Diagonal matrix
```

### Statistics
```latex
\E               % Expectation
\var             % Variance
\cov             % Covariance
\gauss{μ}{Σ}     % Gaussian distribution N(μ,Σ)
```

### Quick Column Vectors
```latex
\colvec{1,2,3}   % Creates a column vector [1; 2; 3]
```

### Color Highlighting
```latex
\blue{text}      % Blue text
\red{text}       % Red text
\green{text}     % Green text
\emph{text}      % Blue bold (redefined)
```

## 📚 Bibliography Management

### Citation Styles

The template supports two main bibliography styles:

1. **`plain`** (default): Sorts references alphabetically by first author's last name
2. **`unsrt`**: Sorts references in order of citation appearance

To change the style, modify in `main.tex`:
```latex
\bibliographystyle{unsrt}  % Change from 'plain' to 'unsrt'
```

### Adding References

Edit `mybib.bib` to add references. Example formats:

**Journal Article:**
```bibtex
@Article{AuthorYear,
  author    = {Last, First and Last, First},
  title     = {Article Title},
  journal   = {Journal Name},
  year      = {2024},
  volume    = {10},
  number    = {5},
  pages     = {123--145},
  publisher = {Publisher},
}
```

**Conference Paper:**
```bibtex
@InProceedings{AuthorYear,
  author    = {Last, First},
  title     = {Paper Title},
  booktitle = {Conference Name},
  year      = {2024},
  pages     = {1--10},
}
```

**Book:**
```bibtex
@Book{AuthorYear,
  author    = {Last, First},
  title     = {Book Title},
  publisher = {Publisher Name},
  year      = {2024},
  edition   = {2nd},
}
```

### Citing in Your Document

```latex
\cite{AuthorYear}           % Standard citation [1]
\cite{Author1,Author2}      % Multiple citations [1, 2]
```

### Managing References

**Recommended Tools:**
- [JabRef](http://www.jabref.org) - Desktop reference manager
- [Zotero](https://www.zotero.org) - Can export to BibTeX
- [Mendeley](https://www.mendeley.com) - Integrates with Overleaf
- Google Scholar - Click "Cite" → "BibTeX" for easy import

## 💡 Tips and Best Practices

### Figures

```latex
\begin{figure}[h!]
\centering
\includegraphics[width=0.7\textwidth]{figures/your_image.png}
\caption{Your caption here.}
\label{fig:yourlabel}
\end{figure}

% Reference it later:
As shown in Figure \ref{fig:yourlabel}...
```

### Equations

```latex
\begin{equation}
E = mc^2
\label{eq:einstein}
\end{equation}

% Reference it later:
From Equation \eqref{eq:einstein}, we see...
```

### Tables

```latex
\begin{table}[h!]
\centering
\begin{tabular}{|c|c|c|}
\hline
Header 1 & Header 2 & Header 3 \\
\hline
Data 1 & Data 2 & Data 3 \\
Data 4 & Data 5 & Data 6 \\
\hline
\end{tabular}
\caption{Table caption.}
\label{tab:yourlabel}
\end{table}
```

### Sections and Subsections

```latex
\section{Introduction}           % Numbered section
\section*{Acknowledgments}        % Unnumbered section
\subsection{Background}           % Numbered subsection
\subsubsection{Details}           % Numbered subsubsection
```

### Theorem Environments

```latex
\begin{theorem}
Your theorem statement.
\end{theorem}

\begin{lemma}
Your lemma statement.
\end{lemma}

\begin{definition}
Your definition.
\end{definition}

\begin{proof}
Your proof here.
\end{proof}
```


## 🤝 Contributing

Contributions are welcome! If you have improvements:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📄 License

This template is based on work licensed under [CC BY-NC-SA 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/).

## 📄 Updates

### Version History

```
- 19.Oct.2025
    - Enhanced README with comprehensive documentation
    - Added detailed usage instructions and examples

- 07.Sept.2024
    - Updated the Usage section for Bibliography Style

- 06.Sept.2024
    - Aligned the heading of pages to left

- 22.Aug.2024
    - Uploaded the Logo for NUS
    - Changed the footnote of pages to right
```


