The vanilla way to insert an image is

      \includegraphics[width=0.8\textwidth]{blah.png}

Ideally, we'd shorten this verbosity with a macro, like:

      \img[0.8]{blah.png}

Problem is that LaTeX-Workshop's autocomplete (and preview) for image files
does not work with anything else besides "`\includegraphics`":
https://github.com/James-Yu/LaTeX-Workshop/wiki/Intellisense#files

It is not clear, but there does not seem to be an option in LaTeX-Workshop to specify other commands for autocomplete besides `\includegraphics`, `\import`, `\include`.

---

Can we then at least shorten the width part?
sth like

      \includegraphics[\w{0.8}]{blah.png}

Defining that macro naively (as `\newcommand*{\w}[1]{width=#1\textwidth}`)
does not work. You'd have to use `\edef` and verbose `\expandafter`s:
https://tex.stackexchange.com/questions/127897/how-to-use-a-macro-inside-includegraphics-options#127926

---

Finally, we use a solution in `Settings.tex` based on the following:
https://tex.stackexchange.com/questions/91616/macro-for-textwidth-textheight-and-keepaspectratio#91619

It works nicely, as:

    \includegraphics[w=0.8]{blah.png}
