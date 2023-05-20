# MinimumViableOperate
MVO is documentation repo defining a minimal viable set of installation and operation instruction example for a third-party packages.

- fully referenced, avoids duplication
- instructions for a specific aspect of the package
- to have the fewest number of installation depencencies and steps 

This repo came as over the years i have learned trying to follow instructions for instalation into an environment that i dont currently have often  results in large amounts of time installing, settup and configruation of optioanl dependencies.

## Guidelines

1. file location based on unique namespace of the package
   - folders based on java Package standard [Packages - oracle.org](https://docs.oracle.com/javase/specs/jls/se6/html/packages.html#7.7) 
   - filename: package-mvo.md
1. one file per package, the description section should include the following sub-sections:
   - Installation, instructions on the install package 
   - Invocation, instructions to run the package
3. Use the document generation standard of the third-party package:
   - [documentation generators - Wikipedia](https://en.wikipedia.org/wiki/Comparison_of_documentation_generators)
   - [Conventions for Linux man-pages - man7.org](https://man7.org/linux/man-pages/man7/man-pages.7.html)
