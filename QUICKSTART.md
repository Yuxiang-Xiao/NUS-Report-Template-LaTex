# Quick Start Guide

This guide will help you get started with the NUS Report Template quickly.

## For Overleaf Users (Easiest Method)

1. **Download the Template**
   - Go to the [Releases page](https://github.com/Yuxiang-Xiao/NUS-Report-Template-LaTex/releases)
   - Download the latest `Source-code.zip` file

2. **Upload to Overleaf**
   - Log in to [Overleaf](https://www.overleaf.com/)
   - Click "New Project" → "Upload Project"
   - Select the `Source-code.zip` file you downloaded
   - Wait for the upload to complete

3. **Customize Your Report**
   - Open `main.tex`
   - Update the following lines with your information:
     ```latex
     \newcommand{\reporttitle}{Your Project Title}
     \newcommand{\reportauthorOne}{Your Name}
     \newcommand{\cidOne}{Your Student ID}
     \newcommand{\reportauthorTwo}{Partner Name (if applicable)}
     \newcommand{\cidTwo}{Partner Student ID (if applicable)}
     ```

4. **Update Course Information**
   - Open `titlepage.tex`
   - Modify the course code and name:
     ```latex
     \textbf{\textsc{\Large ME611 - Mechatronics}}\\[1.0cm]
     ```

5. **Start Writing**
   - Replace the example content in `main.tex` with your own
   - Add figures to the `figures/` directory
   - Update references in `mybib.bib`
   - Click "Recompile" to see your changes

## For Local LaTeX Users

### Prerequisites
- A LaTeX distribution installed (TeX Live, MiKTeX, or MacTeX)
- A LaTeX editor (TeXStudio, TeXMaker, VS Code with LaTeX Workshop, etc.)

### Steps

1. **Get the Template**
   ```bash
   git clone https://github.com/Yuxiang-Xiao/NUS-Report-Template-LaTex.git
   cd NUS-Report-Template-LaTex
   ```

2. **Open in Your Editor**
   - Open `main.tex` in your LaTeX editor

3. **Customize** (same as Overleaf steps 3-4 above)

4. **Compile**
   - Using command line:
     ```bash
     pdflatex main.tex
     bibtex main
     pdflatex main.tex
     pdflatex main.tex
     ```
   - Or use your editor's compile button (usually F5 or F7)

## Common Customizations

### Adding Figures
1. Place your image in the `figures/` directory
2. In your document, use:
   ```latex
   \begin{figure}[h!]
   \centering
   \includegraphics[width=0.45\textwidth]{figures/your-image.png}
   \caption{Your caption here.}
   \label{fig:yourlabel}
   \end{figure}
   ```

### Adding References
1. Add entries to `mybib.bib`:
   ```bibtex
   @article{AuthorYear,
     author = {Author Name},
     title = {Article Title},
     journal = {Journal Name},
     year = {2024},
     volume = {1},
     pages = {1--10}
   }
   ```
2. Cite in your document: `\cite{AuthorYear}`

### Changing Bibliography Style
In `main.tex`, change:
- `\bibliographystyle{plain}` - alphabetical by author
- `\bibliographystyle{unsrt}` - order of citation
- `\bibliographystyle{ieeetr}` - IEEE style

### Enabling Table of Contents
In `main.tex`, uncomment:
```latex
\tableofcontents
\newpage
```

## Tips

- **Compile Multiple Times**: Always compile at least twice after adding citations or references
- **Check Logs**: If compilation fails, check the `.log` file for error messages
- **Use Git**: Track your changes with git for version control
- **Backup**: Regularly backup your work, especially before major changes

## Getting Help

- **Issues**: Report bugs or problems in the [Issues section](https://github.com/Yuxiang-Xiao/NUS-Report-Template-LaTex/issues)
- **Questions**: Tag your issue with "question" for general inquiries
- **LaTeX Help**: For LaTeX-specific questions, check [TeX StackExchange](https://tex.stackexchange.com/)

## Next Steps

- Read the full [README.md](README.md) for detailed information
- Check [CONTRIBUTING.md](CONTRIBUTING.md) if you want to improve the template
- See [CHANGELOG.md](CHANGELOG.md) for version history

Happy writing! 🎓
