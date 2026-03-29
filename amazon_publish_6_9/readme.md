# Steps to generate pdf
Amazon PDF size = 6x9

## Convert to .tex

Run from this folder:
```bash
jupyter nbconvert \
  --to latex \
  ../optimizationmethods.ipynb \
  --output optimizationmethods_amazon_6_9 \
  --output-dir .
```

## Edit Format to 6 x 9

Edit optimizationmethods_amazon_6_9.tex, replace the:

```tex
    \geometry{verbose,tmargin=1in,bmargin=1in,lmargin=1in,rmargin=1in} 
```
or 
```tex
    \geometry
```
with 

```tex
    \geometry{paperwidth=6in,paperheight=9in,inner=0.9in,outer=0.7in,top=0.7in,bottom=0.7in}
```

## Adjust text size


The python blocks inside the .md cells are originally rendered with bigger font, this font passes the margin, to reduce it add this before the `\begin{document}`

```tex    
    \usepackage{etoolbox}

    \AtBeginEnvironment{Verbatim}{\footnotesize}
    \AtBeginEnvironment{Highlighting}{\footnotesize}
``    

The code block text original size is too big, it should be smaller here is how to reduce it:
replace 
```tex
\def\FancyVerbFormatLine ##1{\hsize\linewidth
            \vtop{\raggedright\hyphenpenalty\z@\exhyphenpenalty\z@
                \doublehyphendemerits\z@\finalhyphendemerits\z@
                \strut ##1\strut}%
        }%
```

with 

```tex
\def\FancyVerbFormatLine ##1{\hsize\linewidth\footnotesize
    \vtop{\raggedright\hyphenpenalty\z@\exhyphenpenalty\z@
        \doublehyphendemerits\z@\finalhyphendemerits\z@
        \strut ##1\strut}%
        }%
```


## Add title page

Replace `\maketitle` with this:

```
\begin{titlepage}
    \centering
    \vspace*{3cm}

    {\Huge\bfseries Python for Fundamental Optimization Methods\par}
    \vspace{1cm}

    {\Large An Introduction to Algorithms, Linear Algebra, Numerical Optimization, and Linear Programming\par}
    \vspace{2cm}

    {\Large Marko Grabuloski\par}
    \vfill

    \thispagestyle{empty}   
\end{titlepage}

```

## remove page numeration from the copy write page


just before © 2024 - 2026 Marko Grabuloski

add 

```
\thispagestyle{empty}
```   

## generate pdf

```bash
# clean
latexmk -xelatex -CA optimizationmethods_amazon_6_9.tex
# generate pdf
latexmk -xelatex optimizationmethods_amazon_6_9.tex

```