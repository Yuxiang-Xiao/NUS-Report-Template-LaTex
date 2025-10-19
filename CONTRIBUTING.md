# Contributing to NUS Report Template-LaTeX

Thank you for your interest in contributing to this project! This document provides guidelines for contributing to the NUS Report Template-LaTeX repository.

## How to Contribute

### Reporting Issues

If you find any bugs or have suggestions for improvements:

1. Check if the issue already exists in the [Issues](https://github.com/Yuxiang-Xiao/NUS-Report-Template-LaTex/issues) section
2. If not, create a new issue with a clear title and description
3. Include relevant details such as:
   - LaTeX distribution and version you're using
   - Steps to reproduce the problem
   - Expected vs actual behavior
   - Screenshots if applicable

### Submitting Changes

1. **Fork the repository** to your GitHub account
2. **Clone your fork** locally:
   ```bash
   git clone https://github.com/YOUR-USERNAME/NUS-Report-Template-LaTex.git
   ```
3. **Create a new branch** for your changes:
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. **Make your changes** following the guidelines below
5. **Test your changes** by compiling the LaTeX document
6. **Commit your changes** with clear, descriptive commit messages:
   ```bash
   git commit -m "Add: brief description of your changes"
   ```
7. **Push to your fork**:
   ```bash
   git push origin feature/your-feature-name
   ```
8. **Create a Pull Request** from your fork to the main repository

## Guidelines

### Code Style

- Follow existing LaTeX code formatting and structure
- Keep code readable with appropriate comments
- Maintain consistency with the existing template style

### Template Modifications

- Ensure all changes are backward compatible when possible
- Document any breaking changes clearly in your PR description
- Test that the PDF compiles successfully with your changes

### Documentation

- Update README.md if you add new features or change existing functionality
- Add comments to complex LaTeX code
- Update the Update section in README.md with your changes

### Testing

Before submitting a PR, please ensure:

- [ ] The main.tex file compiles without errors
- [ ] The generated PDF looks correct
- [ ] All figures and references work properly
- [ ] No LaTeX warnings are introduced (unless unavoidable)

## Pull Request Process

1. Ensure your PR description clearly describes the problem and solution
2. Reference any related issues using #issue-number
3. Wait for review and address any feedback
4. Once approved, your PR will be merged

## Questions?

If you have questions about contributing, feel free to:
- Open an issue with the "question" label
- Contact the repository maintainer

## Code of Conduct

- Be respectful and inclusive
- Provide constructive feedback
- Focus on what is best for the community
- Show empathy towards other contributors

Thank you for contributing to make this template better for the NUS community! 🎓
