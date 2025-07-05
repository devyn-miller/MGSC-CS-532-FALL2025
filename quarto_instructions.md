# Quarto Presentation Instructions

This document provides instructions for setting up and previewing Quarto presentations for the MGSC/CS 532 course.

## Prerequisites

- [Quarto](https://quarto.org/docs/get-started/) installed on your system
- Python 3.x installed
- Basic familiarity with command line operations

## Setup Instructions

### 1. Create a Python Virtual Environment

Creating a dedicated virtual environment ensures that all required packages are properly installed and isolated from your system Python.

```bash
# Navigate to your project directory
cd /path/to/your/project

# Create a virtual environment
python -m venv quarto_env

# Activate the virtual environment
# On macOS/Linux:
source quarto_env/bin/activate
# On Windows:
# quarto_env\Scripts\activate
```

### 2. Install Required Packages

Once your virtual environment is activated, install the necessary packages:

```bash
# Install basic requirements for Quarto presentations
pip install PyYAML jupyter

# Install packages needed for data analysis and visualization
pip install numpy matplotlib pandas scipy
```

## Previewing Quarto Presentations

### 1. Activate the Virtual Environment

Always ensure your virtual environment is activated before running Quarto commands:

```bash
# On macOS/Linux:
source quarto_env/bin/activate
# On Windows:
# quarto_env\Scripts\activate
```

### 2. Preview the Presentation

```bash
# Basic preview command
quarto preview your_presentation.qmd

# Preview with specific format (e.g., revealjs for slides)
quarto preview your_presentation.qmd --to revealjs

# Preview without opening browser automatically
quarto preview your_presentation.qmd --to revealjs --no-browser

# Specify a custom port (useful if default port is in use)
quarto preview your_presentation.qmd --to revealjs --port 8000
```

### 3. Access the Preview

After running the preview command, you can access your presentation at:
- http://localhost:8000 (if you specified port 8000)
- http://localhost:4848 (default port if not specified)

## Troubleshooting

### Missing Python Modules

If you encounter errors about missing Python modules:

```
ModuleNotFoundError: No module named 'yaml'
```

Ensure you have:
1. Activated the virtual environment
2. Installed all required packages within that environment

### Port Already in Use

If the default port is already in use, specify a different port:

```bash
quarto preview your_presentation.qmd --port 8080
```

### Rendering Issues

If you encounter rendering issues:

1. Check the console output for specific error messages
2. Ensure all required packages are installed
3. Try rendering to a different format (e.g., `--to html` instead of `--to revealjs`)
4. Validate your Quarto markdown syntax

## Building the Final Presentation

When you're ready to create the final presentation file:

```bash
# Build the presentation
quarto render your_presentation.qmd --to revealjs

# For PDF output (requires LaTeX installation)
quarto render your_presentation.qmd --to pdf
```

## Additional Resources

- [Quarto Documentation](https://quarto.org/docs/guide/)
- [Quarto Presentations Guide](https://quarto.org/docs/presentations/)
- [RevealJS Options](https://quarto.org/docs/presentations/revealjs/) 