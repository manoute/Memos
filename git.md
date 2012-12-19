GIT
===

Configuration globale
---------------------

```bash
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
$ git config --global color.ui auto
$ git config --global core.editor vim
```

Visualiser les commits
----------------------

```bash
$ git log --pretty=oneline --abbrev-commit -n4
$ git show as1e45 --format=email
```

Ajouter/modifier un dépôt distant
---------------------------------

* Ajouter un dépot distant comme origine :

    ```bash
    $ git remote add origin git@github.com:/username/Hello-World.git
    ```

* Modifier l'origine :

    ```bash
    $ git config remote.origin.url git@newserver:newrepo.git
    ```

* Renommer une branche

    ```bash
    $ git remote rename origin github
    ```

[[Gitolite | http://sitaramc.github.com/gitolite/master-toc.html ]]
-------------------------------------------------------------------

### Utiliser un dépot existant avec Gitolite

* Sur l'utilisateur "hôte" de Gitolite
  
    - Créer le dépot correspondant
    
      ```bash
      $ git init --bare myrepo.git
      ```
    - Exécuter 
        ```bash
        $ gitolite setup
        ```

* Sur l'utilisateur "administrateur" de gitolite

    - Ajouter le dépot myrepo.git dans le conf/gitolite.conf du dépôt
      *gitolite-admin* cloné
    - Git commit et git push sur le dépot *gitolite-admin*

* Dans le dépot existant, ajouter un dépôt distant

    ```bash
    $ git remote add newremote git@gitolite.com:myrepo.git
    $ git push newremote branch
    ```

Créer une archive
-----------------

```bash
$ git archive --prefix=mydir/ HEAD > archive.tar
```

Liens
-----

* [[ Gitref | http://gitref.org ]]
