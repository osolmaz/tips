# Replacing the operator font with sans-serif

\DeclareSymbolFont{sfoperators}{OT1}{cmss}{m}{n}
\DeclareSymbolFontAlphabet{\mathsf}{sfoperators}

\makeatletter
\def\operator@font{\mathgroup\symsfoperators}
\makeatother
