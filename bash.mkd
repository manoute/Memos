Bash
====

Exemple
-------

```bash
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
```

Initialisation de variables
---------------------------

Pour tester si une variable a été initialisée et est non vide dans un script :

- Première méthode :

    ```bash
    : ${toto?}
    ```
    Lors de la première passe du shell, il renvoie une erreur si la variable n'existe pas.
    Lors de la deuxième passe (exécution), il n'exécute pas la ligne...

- Deuxième méthode :

    ```bash
    [[ -z $toto ]] && exit $code_unset_or_null

    ```

Forcer l'utilisation de la commande système avec \
--------------------------------------------------

`$ \cp source cible` utilisera toujours la commande système,
même si elle a été redéfinie ou "aliasées".

Printf
------

Forcer l'affichage sur au moins 3 chiffres significatifs

```bash
$ printf "%03i\n" 2
$ 002
$ printf "%3.3i\n" 42
$ 042
```
