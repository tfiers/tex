# ToTeX

(Preposterously named after _Lamport's TeX_, or LaTeX).

Some preamble material common to multiple of my LaTeX documents.

Usage example:
```tex
\documentclass[a4paper,oneside,11pt]{memoir}
\input{totex/Settings}
\input{totex/Commands}
..
\begin{document}
..
\end{document}
```

❗ Make sure `cm-super` is installed, and in MiKTeX console, run *Tasks* > *Refresh font map files*. If not you'll get the dreaded `auto expansion is only possible with scalable fonts`.
