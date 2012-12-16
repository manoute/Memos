.VIM PERSO
==========

Installation
------------

1. Installer les fichiers:

     ```
     $ git clone https://github.com/manoute/vimrc.git ~/.vim
     ```

2. Créer un lien symbolique pour le .vimrc  

    ```
    $ cd
    $ ln -sfn .vim/vimrc .vimrc
    ```

3. Installer [vundle](https://github.com/gmarik/vundle)

    ```
    $ git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle
    ```

4. Installer les plugins vim via [vundle](https://github.com/gmarik/vundle)

    Lancer `vim`, exécuter `:BundleInstall` 

Notes pour solarized et gnome terminal
--------------------------------------

1. Créer un nouveau profil pour gnome-terminal (Edition -> Profils)

2. Installer [gnome-terminal-colors-solarized](https://github.com/sigurdga/gnome-terminal-colors-solarized)

3. Cloner le dépôt git, puis exécuter install.sh :

    ```
    $ git clone git://github.com/sigurdga/gnome-terminal-colors-solarized.git
    $ cd gnome-terminal-colors-solarized
    $ ./install.sh
    ```

4. Le choix de light ou dark pour la console doit être en accord avec celui de .vim/after/plugin/vim-colors-solarized.vim


