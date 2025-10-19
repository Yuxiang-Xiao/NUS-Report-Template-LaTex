# Troubleshooting Guide

This guide helps you resolve common issues when using the NUS Report Template.

## Compilation Errors

### Error: "File not found"

**Problem**: LaTeX cannot find a file (usually an image or style file).

**Solutions**:
1. Check that the file exists in the correct directory
2. Verify the file path in your `\includegraphics` or `\input` command
3. Make sure the file extension is correct (e.g., `.png`, `.jpg`, `.pdf`)
4. For Overleaf users: Ensure the file was uploaded correctly

### Error: "Undefined control sequence"

**Problem**: LaTeX doesn't recognize a command.

**Solutions**:
1. Check for typos in the command name
2. Ensure the required package is loaded in `includes.tex`
3. Make sure you're using the correct syntax for the command

### Error: "Missing $ inserted"

**Problem**: Math mode error.

**Solutions**:
1. Check that all mathematical expressions are within `$...$` or `\[...\]`
2. Look for special characters (like `_` or `^`) used outside math mode
3. Ensure opening and closing delimiters match

### Error: Bibliography not showing

**Problem**: References don't appear in the document.

**Solutions**:
1. Compile multiple times (the full sequence):
   ```bash
   pdflatex main.tex
   bibtex main
   pdflatex main.tex
   pdflatex main.tex
   ```
2. Check that you've cited at least one reference using `\cite{}`
3. Verify `mybib.bib` has correct BibTeX format
4. Ensure `\bibliography{mybib}` is in your document

### Error: Package conflicts

**Problem**: "Option clash" or package compatibility issues.

**Solutions**:
1. Check if a package is loaded multiple times with different options
2. Review `includes.tex` for duplicate package declarations
3. Load packages with conflicting options only once with all needed options

## Formatting Issues

### Issue: Title page doesn't show NUS logo

**Problem**: Logo not displaying.

**Solutions**:
1. Verify `figures/nus.jpg` exists
2. Check the file path in `titlepage.tex`
3. Ensure the image file is not corrupted
4. Try using a different image format (convert to PNG if needed)

### Issue: Incorrect page numbering

**Problem**: Page numbers don't start correctly.

**Solutions**:
1. Check for `\setcounter{page}{1}` commands
2. Verify `\pagenumbering{arabic}` is set appropriately
3. Look for conflicting page style commands

### Issue: Headers/footers not appearing correctly

**Problem**: Page headers or footers are missing or wrong.

**Solutions**:
1. Check `\pagestyle{fancy}` is set in `includes.tex`
2. Verify fancyhdr package is loaded
3. Review custom header/footer settings in `includes.tex`

## Content Issues

### Issue: Figures not appearing

**Problem**: Figures compile but don't show in the document.

**Solutions**:
1. Check figure placement options (`[h]`, `[t]`, `[b]`, `[p]`)
2. Try `[h!]` or `[H]` (requires float package) for forced placement
3. Ensure sufficient space on the page for the figure
4. Check if the figure is commented out accidentally

### Issue: References not linking correctly

**Problem**: Clicking references doesn't jump to the right location.

**Solutions**:
1. Compile multiple times to update all references
2. Ensure hyperref package is loaded (it is, in `includes.tex`)
3. Check label names are unique
4. Verify `\label{}` comes after `\caption{}`

### Issue: Table of contents not updating

**Problem**: TOC shows old or missing entries.

**Solutions**:
1. Compile at least twice after making changes
2. Delete auxiliary files (`.aux`, `.toc`) and recompile
3. Check section commands are using standard LaTeX (`\section`, etc.)

## Overleaf-Specific Issues

### Issue: Compilation timeout

**Problem**: Overleaf stops compiling before finishing.

**Solutions**:
1. Remove or comment out large, unused sections
2. Compress large images
3. Consider splitting into multiple documents
4. Check for infinite loops in custom commands

### Issue: Upload failed

**Problem**: Cannot upload the template to Overleaf.

**Solutions**:
1. Ensure you're uploading a `.zip` file
2. Check the file size is within Overleaf's limits
3. Try extracting and re-zipping the files
4. Upload files individually if zip upload fails

## Local LaTeX Issues

### Issue: Missing packages

**Problem**: "Package not found" errors.

**Solutions**:
1. **TeX Live**: `tlmgr install <package-name>`
2. **MiKTeX**: Packages usually install automatically; if not, use MiKTeX Package Manager
3. **MacTeX**: Use TeX Live Utility
4. Update your LaTeX distribution if very old

### Issue: Compilation very slow

**Problem**: Takes too long to compile.

**Solutions**:
1. Comment out `\usepackage{draftwatermark}` if present
2. Use draft mode: `\documentclass[draft]{article}`
3. Disable hyperref temporarily during editing
4. Use `\includeonly{}` for multi-file documents

## Getting More Help

If you've tried these solutions and still have issues:

1. **Check the error log**: Look in the `.log` file for detailed error messages
2. **Search online**: Copy the exact error message and search on:
   - [TeX StackExchange](https://tex.stackexchange.com/)
   - [LaTeX Community Forum](https://latex.org/forum/)
3. **Open an issue**: Report the problem on our [GitHub Issues](https://github.com/Yuxiang-Xiao/NUS-Report-Template-LaTex/issues) with:
   - The exact error message
   - Your LaTeX distribution and version
   - Steps to reproduce the issue
   - Minimal example code if possible

## Useful Commands

**Clean auxiliary files** (Linux/Mac):
```bash
rm -f *.aux *.log *.out *.toc *.bbl *.blg *.synctex.gz
```

**Clean auxiliary files** (Windows):
```cmd
del *.aux *.log *.out *.toc *.bbl *.blg *.synctex.gz
```

**Force recompile everything**:
```bash
rm -f *.aux *.bbl *.blg
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

## Prevention Tips

1. **Compile frequently**: Don't wait until you've written a lot before compiling
2. **Use version control**: Git can help you track changes and revert if needed
3. **Backup regularly**: Save copies of working versions
4. **Test incrementally**: Add complex features one at a time
5. **Keep it simple**: Avoid overly complex custom commands when starting out

Happy troubleshooting! 🔧
