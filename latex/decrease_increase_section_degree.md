# Increasing/Decreasing Sectioning Degrees in LaTeX

In LaTeX, one sometimes needs to convert between different document classes,
such as book to article or vice versa. In that case, the top-level degree of sectioning
changes from \chapter to \section, which needs to be accounted for in the code. In
fact, all section macros need to be decreased. In a project directory with many
files, one can implement this in a simple script which finds and replaces the
relevant commands in every LaTeX file. Just copy and paste into a Bash script,
or directly into your terminal:

    sed -i 's/\\paragraph/\\subparagraph/g' *.tex
    sed -i 's/\\subsubsection/\\paragraph/g' *.tex
    sed -i 's/\\subsection/\\subsubsection/g' *.tex
    sed -i 's/\\section/\\subsection/g' *.tex
    sed -i 's/\\chapter/\\section/g' *.tex

Increasing is the same except the other way around:

    sed -i 's/\\subparagraph/\\paragraph/g' *.tex
    sed -i 's/\\paragraph/\\subsubsection/g' *.tex
    sed -i 's/\\subsubsection/\\subsection/g' *.tex
    sed -i 's/\\subsection/\\section/g' *.tex
    sed -i 's/\\section/\\chapter/g' *.tex

