GIT
===

Configuration globale
---------------------

```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
$ git config --global color.ui auto
$ git config --global core.editor vim
```

Visualiser les commits
----------------------

```
$ git log --pretty=oneline --abbrev-commit -n4
$ git show as1e45 --format=email
```

Ajouter une origine
-------------------

```
$ git remote add origin https://github.com/username/Hello-World.git
$ git remote add origin git@github.com:/username/Hello-World.git
# Creates a remote named "origin" pointing at your GitHub repo
```

