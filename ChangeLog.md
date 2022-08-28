Change Log
==========


## 0.7.0 (2022-08-29)

Changes:

* All restrictions have been lifted concerning the characters that are allowed
  in the identifiers passed to `\hereapplies` and `\whereapplies`; leading and
  trailing spaces from now on will be trimmed
* I/O operations now rely on one auxiliary file only
* Code review
* Documentation


## 0.6.0 (2022-08-23)

Changes:

* The `\whereapplies` macro now prints "and", instead of a comma, before the
  last page
* All translatable strings have been isolated into the four adjustable macros
  `\hapage`, `\hapages`, `\hadelimiter` and `\halastdelimiter`
* Code review (the `\hereapplies` macro now invokes `\detokenize` before
  checking whether the optional argument was passed)
* The LyX module has been updated
* Documentation


## 0.5.0 (2022-08-19)

Changes:

* A macro expansion bug has been fixed
* The `\hereapplies` macro now supports a comma-separated list of identifiers
* Documentation
* Examples


## 0.4.0 (2022-08-16)

Changes:

* The `\whereapplies` macro and its starred counterpart now support page ranges
  and a more robust indexing (a partial rewrite of the code and the addition of
  the `refcount` dependency were necessary)
* The LyX module has been updated
* Documentation
* Examples


## 0.3.1 (2022-08-15)

Changes:

* Documentation


## 0.3.0 (2022-08-13)

Changes:

* A starred version of the `\whereapplies` macro has been created
* The label generated when `\hereapplies` is invoked with two arguments has now
  become verbatim equal to the first argument -- previously it was equal to
  `appl:[concept]:[label]`
* Code review
* The LyX module has been updated
* Documentation
* Examples


## 0.2.0 (2022-08-12)

Changes:

* A starred version of the `\hereapplies` macro has been created
* A module for LyX has been added to the repository
* The package now prints `??` (instead of generating an error) when
  `\whereapplies` is invoked but `\hereapplies` is never invoked
* Code review
* Documentation
* Examples


## 0.1.0 (2022-08-11)

**Here Applies** has been published.

