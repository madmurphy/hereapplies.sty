Here Applies
============

A LaTeX package for referencing groups of pages that share something in common


Overview
--------

**Here Applies** is a LaTeX package that allows to collect groups of labels and
reference them altogether. It can be used for creating informal glossaries that
cross-link concepts to their applications, or simply mentioning multiple pages
that share something in common.

The package offers two commands: `\hereapplies` and `\whereapplies` (plus their
“starred” versions `\hereapplies*` and `\whereapplies*`). In both cases an
identifier is passed as argument, and this can be any string invented in the
moment (`\hereapplies` additionally supports more than one identifier in the
form of a comma-separated list).

Every time `\hereapplies` is invoked with known identifiers, the document is
made aware that the place shares some kind of connection with other places in
which the same identifiers were used. And so, every time the `\whereapplies`
command is invoked with a known identifier, all occurrences of the latter
within the entire document will be printed in the form of a linkable page list
(e.g. “pp. 1, 5, 8–9, 14–20…”).

As `\hereapplies` is designed to be invoked in the middle of a chapter or a
section and that location must be made linkable, the `\phantomsection`
directive is invoked by default before a label is added. To avoid calling
`\phantomsection`, the “starred” command `\hereapplies*` is available.

Finally, like `\whereapplies` resembles a pluralizable version of `\pageref`,
its “starred” version `\whereapplies*` will resemble a pluralizable version of
`\pageref*`.

If you use LyX, the package ships a LyX module as well (please check the
`lyx-module` subdirectory).


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
see \whereapplies{conceptTwo}.\newpage

\hereapplies{conceptOne} This is page \thepage. As you can see,
``concept one'' applies here.\newpage

\hereapplies{conceptTwo} This is page \thepage. As you can see,
``concept two'' applies here.\newpage

\hereapplies{conceptOne, conceptTwo} This is page \thepage. As you
can see, both ``concept one'' and ``concept two'' apply here.\newpage

\hereapplies{conceptTwo} This is page \thepage. As you can see,
``concept two'' applies here.\newpage

\hereapplies[myref]{conceptOne} This is page \thepage. As you can
see, ``concept one'' applies here. This point in the document is
labeled \texttt{myref}.

\end{document}
```

will generate the [`hereapplies-example.pdf`][1] document attached.


A minimal tutorial
------------------

### Command `\hereapplies[label]{identifiers}`

The `\hereapplies` command notifies the document that one or more identifiers
apply to a particular point and adds a label to it.

If the optional argument is passed the label created will be named accordingly,
otherwise an opaque name will be chosen for it. This argument may contain only
what is legal for `\pageref`.

The `identifiers` argument must be a comma-separated list of identifiers
(leading and trailing spaces around each member will be ignored). Each of these
strings will remain confined within the internal scope of the package and will
not create conflicts with possible macros or labels of the same names.

After storing some internal values, `\hereapplies` will expand exactly to

``` tex
\phantomsection\label{...}
```

Its “starred” version (`\hereapplies*`) will not invoke the `\phantomsection`
directive.


### Command `\whereapplies{identifier}`

The `\whereapplies` command prints all the occurrences of an identifier, in the
form “p. …” or “pp. …” (with page range support).

The `identifier` argument will remain confined within the internal scope of the
package and will not create conflicts with possible commands or labels of the
same name. Leading and trailing spaces around this string will be ignored.

If the same `identifier` is not passed to `\hereapplies` at least once
throughout the document, `\whereapplies` will print “**??**”.

The “starred” version of this command (`\whereapplies*`) will use `\pageref*`
instead of `\pageref` for generating the page list.


Internationalization
--------------------

Currently the localization of **Here Applies** is not automatic. It is possible
however to control the strings generated by overwriting the four macros
`\hapage`, `\hapages`, `\hadelimiter` and `\halastdelimiter`. For example,
writing at the beginning of a document

``` tex
% German translation of **Here Applies**
% English: "p.\ "
\gdef\hapage{S.\ }
% English: "pp.\ "
\gdef\hapages{S.\ }
% English: "\ and\ "
\gdef\halastdelimiter{\ und\ }
% English: ",\ " (exactly like in German -- leave it)
%\gdef\hadelimiter{,\ }
```

will translate “pp. 2, 4 and 6” into “S. 2, 4 und 6”.


Get involved
------------

If you wish to get involved, please do not hesitate to send [merge requests][2]
or participate in the discussion. The package is also [available on
**CTAN**][3] under [`macros/latex/contrib/hereapplies/`][4]. For any issue,
please [drop a message][5].


Free software
-------------

**Here Applies** is free software. You can redistribute it and/or modify it
under the terms of the **AGPL** license version 3 or any later version. See
[`COPYING`][6] for details.


  [1]: hereapplies-example.pdf
  [2]: https://github.com/madmurphy/hereapplies.sty/pulls
  [3]: https://www.ctan.org/pkg/hereapplies
  [4]: https://www.ctan.org/tex-archive/macros/latex/contrib/hereapplies/
  [5]: https://github.com/madmurphy/hereapplies.sty/issues
  [6]: COPYING

