# Introduction

This project explores the most common numerical optimization methods and algorithms, providing a comprehensive guide to understanding and solving optimization problems. It offers a gradual introduction to optimization, blending mathematical explanations with practical Python implementations. All code can be executed using Jupyter Notebook or Google Colab.

## Covered Subjects:

- **Introduction to Python and Basic Mathematical Operations**:
  - Learn Python fundamentals and basic mathematical operations necessary for optimization.

- **Linear Algebra, Lists, and Matrices in Python**:
  - Grasp essential linear algebra concepts and their implementation using lists and matrices in Python.

- **Optimization Algorithms in Python**:
  - Delve into various optimization algorithms and learn how to implement them in Python.

- **Linear Programming**:
  - Understand and solve linear programming problems using Python.

This book aims to provide both theoretical knowledge and practical skills, focusing on basic methods rather than advanced techniques. It is an invaluable resource for students, researchers, and professionals in the field of optimization.

## Visual Studio setup
The following notes are useful for running the project locally:

### Visual studio setup
https://code.visualstudio.com/docs/python/python-quick-start

### Setup conda
* https://conda.io/projects/conda/en/latest/user-guide/getting-started.html

### Conda setup
* conda create -n <environmentName>
* conda activate .conda/ 
* conda deactivate

## Jupiter notebook
* https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter

## VS Commands
* Command Palette  Cmd+Shift+P

## PDF exporter
* conda install nbconvert
* install https://tug.org/mactex/ for conversion to pdf

## Diagrams
* https://marketplace.visualstudio.com/items?itemName=vstirbu.vscode-mermaid-preview
* https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio
* https://support.typora.io/Draw-Diagrams-With-Markdown/ - tutorial

## Latex
* https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop

## Spelling check
* https://marketplace.visualstudio.com/items?itemName=ban.spellright
* https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker

## Quarto setup

### Install Quarto
* Download and install from https://quarto.org/docs/get-started/
* Or via Homebrew: `brew install quarto`

### VS Code extension
* https://marketplace.visualstudio.com/items?itemName=quarto.quarto

### Virtual environment setup
```bash
# Create and activate the virtual environment
python -m venv quarto_env
source quarto_env/bin/activate

# Install required packages
pip install jupyter jupyterlab
pip freeze > requirements.txt
```

### Restore environment (after cloning)
```bash
python -m venv quarto_env
source quarto_env/bin/activate
pip install -r requirements.txt
```

### Convert .ipynb to .qmd
```bash
quarto convert optimizationmethods.ipynb
```

### Render to HTML
```bash
quarto render optimizationmethods.qmd --to html
```

### Preview with live reload
```bash
quarto preview optimizationmethods.qmd
```

## Convert to pdf and html
```bash
jupyter nbconvert --to pdf optimizationmethods.ipynb
jupyter nbconvert --to html optimizationmethods.ipynb
```


## Convert to word base
```bash

# Version 1
# initially convert to .md
jupyter nbconvert --to markdown optimizationmethods.ipynb

# convert to word
pandoc optimizationmethods.md -o optimizationmethods.docx

# convert to word with table of content
pandoc optimizationmethods.md -o optimizationmethods.docx --toc --toc-depth=3

# Version 2
jupyter nbconvert --to latex optimizationmethods.ipynb

pandoc optimizationmethods.tex -o optimizationmethods.docx --toc --toc-depth=3

```