hereapplies.sty
===============

A LaTeX package for cross-linking applications of concepts


Example usage
-------------

### LaTeX source

``` tex
\documentclass[oneside]{book}

\usepackage{hereapplies}

\begin{document}

\title{Some title}
\author{Some author}

\maketitle
This is concept one. To see this concept applied, please
see\whereapplies{conceptone}.

This is concept four. To see this concept applied, please
see\whereapplies{conceptfour}.\newpage

\hereapplies{conceptone}This is page \thepage. As you can see, ``concept
one'' applies here.\newpage

\hereapplies{conceptfour}This is page \thepage. As you can see,
``concept four'' applies here.\newpage

\hereapplies{conceptone}This is page \thepage. As you can see, ``concept
one'' applies here.\newpage

\hereapplies{conceptfour}This is page \thepage. As you can see,
``concept four'' applies here.\newpage

\hereapplies{conceptone}This is page \thepage. As you can see, ``concept
one'' applies here.

\end{document}
```

### Result

![Example of hereapplies.sty][1]


  [1]: example.png
