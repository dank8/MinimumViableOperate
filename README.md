> Your input is welcome:
> 1. [ask a question][1] 
> 1. [suggest a package][2], or []
> 1. developers, create mvo in your project, suggest changes to the guidelines
> 1. package maintainers, incorporate an mvo instruction into your doco, raise [new issue][3] with a link to your mvo.
> 1. or reach out to [dank8][4]
>  
> "Places I'd rather be.... contributing to a community resource, shortening the journey [:checkered_flag:] for others". 

# MinimumViableOperate
MVO is documentation repo defining a minimal viable set of installation and operation instruction example for a third-party packages.

- fully referenced, avoid duplication
- script or replicatable steps to perfom a specific aspect of the package
- to have the fewest number of installation depencencies and steps 

## Why am i doing this?
Over the years i have encountered many exciding project and packages, I would begin a journey of using the package by insalling following the provided getting started guide, the installation is always onto a third-party plaform (OS, containerisation, or other platform).

At some point during the installation I end up in 'depencency hell' with an optional third-party pre-requisite (oTpp) reporting chains of errors and wanrings resulting in a chagne to my objective:
- is there enough confidence or familiarity with the oTpp to solve the errors using the package documentation
- signficant unproductive time and redirected focus to discover the architecure, installation and configuration of the oTpp
- time redirected to decouple the package from the oTpp and define a set of package installation steps
- abandon this package altogehter

## Objectives of mvo
Define a set of package installation and invoke instuctions and scripts, that achives:
- successful operation with minimal time invested seting up oTpp, t
- runtime environment is minimalist or default installation
- zero oTpp packages
- Usecase objective that is clear and specific 
- basic but complete package feature operates successfully
- installation from published package source or build. if code compliation is required it must follow a separate mvo that describes standard minimal instructions for compliation of source language,

## Guidelines
1. mvo must be able to be replicated
1. depencency installation instructions that include depencencies, should refer to 
1. minimise maintenance effort and ensuring compatability by:
   1. following language standards
   1. following runtime standards
   1. borrowing bits of eqivlent standards
   1. write documentation in either:
      - markdown, following the github observed markdown standard OR 
      - standard of package documentation, where time permits OR
      - widely used document generation standard 
1. Folder structure  `docs/FQDN/NAME-mvo.md`, [ietf.org, 1987][5], [oracle.org, 2023][6] 
   - `/docs`  root folder containing all documentation
     - `/{FQND}` the fully qualified domain name (or homepage), one folder for each [[domain label]] (i.e. github.com.au becomes `docs/au/com/github`) 
       - `/NAME-mvo.EXT` *NAME* of the exe invoked, or the package name, *EXT* extension of the documentation style
1. mvo should one file per package, the description section should include the following sub-sections:
   - *NAME* 
   - *SYNOPSIS*
   - *DESCRIPTION*
   - *SETUP*, instructions on the install package, setup to operational state
   - *INVOKE* or *PLAY*, instructions to run the package or play the game

## Explanitory notes:

1. example references to documentation standards:
   - [linux, man pages][4011]
   - [python, pydoc][4012]
1. example tools for document generation:
   - [MkDocs][4021]

  [1]: https://github.com/dank8/MinimumViableOperation/issues/new?assignees=dank8&labels=question&projects=&template=questions-and-feedback.md&title=%5BQ%3A%5D+%3Cask+your+question%3E
  [2]: https://github.com/dank8/MinimumViableOperation/issues/new?assignees=dank8&labels=question&projects=&template=questions-and-feedback.md&title=%5BQ%3A%5D+%3Cask+your+question%3E
  [3]: https://github.com/dank8/MinimumViableOperation/issues/new?assignees=dank8&labels=enhancement&projects=&template=feature_request.md&title=
  [4]: https://github.com/dank8
  [5]:  https://datatracker.ietf.org/doc/html/rfc1034#section-3.1
  [6]: https://docs.oracle.com/javase/specs/jls/se6/html/packages.html#7.7
  [4011]: https://man7.org/linux/man-pages/man7/man-pages.7.html
  [4012]: https://docs.python.org/3/library/pydoc.html
  [4021]: https://www.mkdocs.org/
