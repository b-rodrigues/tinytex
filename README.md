# TinyTeX

## Forked from Xie Yihui's repo

Just added some depedencies to compile my thesis. Run this to install:


    wget -qO- \
      "https://github.com/b-rodrigues/tinytex/raw/master/tools/install-unx.sh" | sh


### Maintenance (taken from https://yihui.name/tinytex/)

If you compile a LaTeX document and run into an error message like this:

    ! LaTeX Error: File `framed.sty' not found.

    Type X to quit or <RETURN> to proceed,
    or enter new name. (Default extension: sty)

It basically indicates a missing LaTeX package. Do not panic. Open a command window, and use the command tlmgr search --     global --file followed by the filename,5 e.g.,

    $ tlmgr search --global --file "/framed.sty"
    framed:
            texmf-dist/tex/latex/framed/framed.sty
    ...

Find the package that contains the file with the exact name in the error log above. In this case, the missing package is framed (not mdframed or other packages), and we can install a package via tlmgr install, e.g.,

    tlmgr install framed

If you still see error messages that you don’t understand, you may update everything:

    tlmgr update --self --all
    tlmgr path add
    fmtutil-sys --all

## Original readme below

[![Build Status](https://travis-ci.org/yihui/tinytex.svg)](https://travis-ci.org/yihui/tinytex)

The installation and maintenance of LaTeX have bothered me for several years. Yes, there are MiKTeX, MacTeX, and TeX Live, but the common problems are:

1. You have to either install a basic version that is relatively small (several hundred MB) but basically doesn't work, because it is very likely that certain frequently used LaTeX packages are missing; or you install the full version that is several GB, but in your whole life, you probably will only use 1% of the packages.

2. The documentation for installation and maintenance is often way too long for beginners. For example, I doubt if anyone has the courage or patience to read [the `tlmgr` manual](https://www.tug.org/texlive/doc/tlmgr.html) (yes, it is very useful).

I believe these problems can be solved by TinyTeX, a different LaTeX distribution based on TeX Live that is small in size (about 150Mb) but still functions well in most cases. Even if you run into the problem of missing LaTeX packages, it should be super clear to you what you need to do. The manual should be at most two pages long.

This repo contains the installation scripts of TinyTeX (under the `tools` directory) and the R companion package **tinytex**. Please see the full documentation at <https://yihui.name/tinytex/>. Obviously I hope it is not too long.
