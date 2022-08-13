Here Applies
============

A LaTeX package for cross-linking concepts to their applications


Overview
--------

**Here Applies** is a LaTeX package that implements an _informal glossary_. Its
core mechanism is identical to that of a conventional glossary – i.e. some
concepts are marked as “important” and indicized every time they appear in the
document – but it does not produce any nomenclature section, nor relies on the
conventions that normally take part in a glossary.

In fact, normally, besides an indicization mechanism, a proper glossary should
be able to produce a dedicated section (usually at the end of the document)
where the terms are collected in alphabetical order, their definitions are
shown, and the lists of their occurrences are presented. By design, all these
things but the last one are missing in **Here Applies**.

Instead, the package offers only two macros: `\hereapplies` and `\whereapplies`
(plus their “starred” versions `\hereapplies*` and `\whereapplies*`). In both
cases a “concept name” is passed as argument – and this can be any string
invented in the moment, as long as it contains only letters.

Every time `\hereapplies` is invoked again on an identical string the document
knows that the same concept from previous invocations is occurring at that
point. And so every time the `\whereapplies` macro is invoked, all the
occurrences of that concept within the entire document will be printed in the
form of a linkable page number list (“pp. 1, 2, 3, 4, …”).

As `\hereapplies` is designed to be invoked in the middle of a chapter or a
section and make it linkable, the `\phantomsection` macro is invoked by default
before a label is added to that place. To avoid calling `\phantomsection`,
the “starred” macro `\hereapplies*` is available.

Finally, like `\whereapplies` resembles a pluralizable version of `\pageref`,
its “starred” version `\whereapplies*` resembles a pluralizable version of
`\pageref*`.


Example usage
-------------

The following LaTeX manuscript

``` tex
\documentclass{article}

\usepackage{hereapplies}

\begin{document}

\title{Some title}
\author{Some author}

\maketitle

This is concept one. To find this concept applied, please
see \whereapplies{conceptOne}.

This is concept two. To find this concept applied, please
see \whereapplies{conceptTwo}.

\newpage

\hereapplies{conceptOne}This is page \thepage. As you can see, ``concept
one'' applies here.\newpage

\hereapplies{conceptTwo}This is page \thepage. As you can see,
``concept two'' applies here.\newpage

\hereapplies{conceptOne}This is page \thepage. As you can see, ``concept
one'' applies here.\newpage

\hereapplies{conceptTwo}This is page \thepage. As you can see,
``concept two'' applies here.\newpage

\hereapplies[myref]{conceptOne}This is page \thepage. As you can
see, ``concept one'' applies here. This point in the document is
labeled \texttt{myref}.

\end{document}
```

will generate [this document][1].


A minimal tutorial
------------------

### Macro `\hereapplies[label]{concept_name}`

The `\hereapplies` macro notifies the document that a particular concept
applies to a particular point and creates a label for it.

If the optional argument is passed the label created will be named accordingly,
otherwise an opaque name will be assigned to it. This argument may contain only
what is legal in both `\label` and `\pageref`.

The `concept_name` argument may contain only letters and the “at” sign (`@`).

The “starred” version of this macro (`\hereapplies*`) does not invoke the
`\phantomsection` directive.


### Macro `\whereapplies{concept_name}`

The `\whereapplies` macro prints all the occurrences of a concept, in the form
“p. …” or “pp. …”

The `concept_name` argument may contain only letters and the “at” sign (`@`).

The “starred” version of this macro (`\whereapplies*`) will use `\pageref*`
instead of `\pageref` for generating the page list.


Get involved
------------

If you wish to get involved, please do not hesitate to send [merge requests][2]
or participate in the discussion.

The package is also [available on CTAN][3] under
[`macros/latex/contrib/hereapplies`][4].

For any issue, please [drop a message][5].


Free software
-------------

**Here Applies** is free software. You can redistribute it and/or modify it
under the terms of the **AGPL** license version 3 or any later version. See
[COPYING][6] for details.


  [1]: hereapplies-example.pdf
  [2]: https://github.com/madmurphy/hereapplies.sty/pulls
  [3]: https://www.ctan.org/pkg/hereapplies
  [4]: https://www.ctan.org/tex-archive/macros/latex/contrib/hereapplies
  [5]: https://github.com/madmurphy/libgnunetworker/issues
  [6]: COPYING

