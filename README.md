# MINIMUM VIABLE OPERATE (MVO)
MVO proposes that development projects include a minimal and generic install and operate instruction that limits dependencies with other tools.

Your input is welcome:  [Ask a question][1] # Create a MVO equivalent in projects you maintain # [Suggest a package][2].  
 
> "Places I'd rather be.... shortening the journey for others by contributing to a community resource." [dank8][4] 


**Minimum Viable Operate Pages**

| Operate this | What is it? |
|:--:|:-- |
| [Catan](./docs/com.catan/basegame-mvo.md) | Boardgame to Complete with other fearless seafarers on the shores of Catan to settle the island. |
| [git](./docs/com.git-scm/git-mvo.md) | Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency. |
| [github](./docs/com.github/gh-mvo.md) | GitHub gives your team everything they need to ship better software faster. |
| [sed](./docs/org.gnu/sed-mvo.md) | stream editor is used to perform basic text transformations on an input stream (a file or input from a pipeline). |
| [shell Scripting in Linux](./docs/org.opengroup/scripting-mvo.md) | argument syntax of the standard utilities and introduces terminology used throughout POSIX.1-2017 for describing the arguments processed by the utilities. |

**Notes Scrachpad**

| Operate this | What is it? |
|:--:|:-- |
| [VS Code](./docs/com.microsoft.vscode/vscode-mvo.md) | VS Code, is a source-code editor developed by Microsoft for Windows, Linux and macOS. Features include support for debugging, syntax highlighting, intelligent code completion, snippets, code refactoring, and embedded Git. |
| [WinOS Registry](./docs/com.microsoft.windows/registry-mvo.md) | The Windows Registry is a hierarchical database that stores low-level settings for the Microsoft Windows operating system and for applications that opt to use the registry. |


## WHY HAVE I STARTED THIS PROJECT?
I have come across numerous interesting packages. I would eagerly step through the getting started guide and very quickly discover a Third-Package was required to successfully use Target-Package such as OS, containerisation, and a service platform. 

Pushing on with this knowledge, I become stuck in what is commonly known as 'dependency hell'. The dependent Third-Package would report a series of errors and warnings, and the Target-Package errors also report being unable to see the functions of the Third-Package. 

Leaving me to determine if I had:
- Adequate experience in setting up the Third-Package.  
- Time to explore the Third-Party installation and configuration to resolve errors reported by Target-Package. 
- Time available to explore and document the decoupling of Target-Package from the Third-Package.

## OBJECTIVE
Establish concise instructions to demo Target-Package core features anywhere:
- minimise time spent getting started, and minimise time spent on documentation. 
- demonstrates the operation of Target-Package core features 
- successfully runs on generic runtime configuration.
- It successfully runs on Third-Package minimal and generic installation/configuration.

## Writing guidelines

1. MVO Documents are maintainable:
   1. compatible with language and runtime documentation standards
   1. standards first approach (don't reinvent the wheel)
   1. minimal formatting:
      - markdown, for instance, GitHub 
      - widely used document generation standard 
      - compatible with documentation generators 
1. MVO documents are minimal:
   1. reference complex instructions rather than recreating them.
   1. Script rather than document repetable installation steps.
   1. Can be easlitly reproduced from a standard enviornment build (mimisie enviornment tuning)
	
## Structure of [dank8/MinimumViableOperation](https://github.com/dank8/MinimumViableOperation) Repository
1. Folder structure default `docs/{domainName}/{invokeCommand}-mvo.{documentFormat}`, [ietf.org, 1987][5], [oracle.org, 2023][6], for example `docs/com.github/gh-mvo.md`)
   - `{domainName}`, the fully qualified domain hosting the project code.
   - `{invokeCommand}` *NAME* of the exe invoked or the package name.
   - `{documentFormat}` extension of the documentation style.
1. MVO should have one file per package, as following sub-sections:
   - *NAME* 
   - *SYNOPSIS* is the example of the most basic run command to launch the Target-Package core feature successfully.
   - *DESCRIPTION*
   - *SETUP*, instructions on the install package, setup to operational state.
   - *INVOKE* or *PLAY*, a short explanation of each command variation and what it achieves or how to play the game.
   - *EXPLANATORY NOTES*, is a detailed discussion of package nuances or behaviours not described in Target-Package's existing documentation.

## Explanatory notes

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
  