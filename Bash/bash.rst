====
Bash
====

Exemple
-------

    # ------------- SCRIPT ------------- #

    #!/bin/bash

    echo
    echo "# arguments called with ---->  ${@}     "
    echo "# \$1 ---------------------->  $1       "
    echo "# \$2 ---------------------->  $2       "
    echo "# path to me --------------->  ${0}     "
    echo "# parent path -------------->  ${0%/*}  "
    echo "# my name ------------------>  ${0##*/} "
    echo "# my full path ------------------>  $(readlink -m $0) "
    echo "# my parent full path ------------------>  $(readlink -m ${0%/*}) "
    echo
    export PATH=$(readlink -m ${0%/*}):$PATH
    echo "# my new PATH------------------------> $PATH"
    exit

    # ------------- CALLED ------------- #
