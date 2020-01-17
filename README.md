### How to compile in Linux

Forked from official KiTTY 0.67. Major differences:

* Mouse hover support (mode 1003)

* Improved support of ctrl-shift-alt modifiers and F1-F12 function keys.

* Many other improvements - hyperlinks, local config files.

Compile with mingw.

For example use this Arch based docker with installed mingw (https://github.com/mdimura/docker-mingw-arch)

    git clone https://github.com/mdimura/docker-mingw-arch
    cd docker-mingw-arch
    docker build -t docker-mingw-arch .
    docker run -it docker-mingw-arch bash

    # within docker (svn is needed only for kitty compilation, not putty)
    yay -S iputils vim svn

    # checkout and build KiTTY-X
    git clone https://github.com/adizero/KiTTY-X
    cd KiTTY-X/trunk/0.67_My_PuTTY/windows
    make -e TOOLPATH=/usr/bin/i686-w64-mingw32- -f MAKEFILE.MINGW -j4 kitty
