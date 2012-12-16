Makefile
========

exemple
-------

```makefile
# The compiler
FC = gfortran
# flags for debugging or for maximum performance, comment as necessary
FCFLAGS = -W -Wall -O2
# flags forall (e.g. look for system .mod files, required in gfortran)
FCFLAGS += -I/usr/include

# libraries needed for linking, unused in the examples
LDFLAGS = -L/usr/lib -lgrib_api_f90 -lgrib_api -lopenjpeg -lpng -lm 


# Programme principal de l'utilisateur
# -------------------------------------
# le main peut-etre C ou fortran : monprog.c ou monprog.f
MAIN        = interpolations.f90
EXECUTABLE    := $(shell echo $(MAIN) | cut -d "." -f 1,1)

# routines de l'utilisateur
# -------------------------

SRCSF    = interpolations_mod
# List of executables to be built within the package
#PROGRAM = derived_types

SRCSF += $(EXECUTABLE)

OBJS := $(shell echo $(SRCSF) | sed 's|\(\S\+\)|\1.o|g')

echo:
  @echo $(EXECUTABLE) $(SRCSF) $(OBJS)

# "make" builds all
all: $(EXECUTABLE)

# General rule for building prog from prog.o; $^ (GNU extension) is
# used in order to list additional object files on which the
# executable depends
# %: %.o

$(EXECUTABLE): $(OBJS)
  $(FC) $(FCFLAGS) -o $@ $^ $(LDFLAGS)

# General rules for building prog.o from prog.f90 or prog.F90; $< is
# used in order to list only the first prerequisite (the source file)
# and not the additional prerequisites such as module or include files
%.o: %.f90
  $(FC) $(FCFLAGS) -c $<
  
clean:
  rm -f $(OBJS) *.mod core

clobber: clean
  rm -f $(PROGRAMS)
```

Variables automatiques
----------------------

nom | signification
----|--------------
$@  | nom de la cible qui provoque l'exécution de la commande 
$<  | nom de la 1ère dépendance
$?  |nom de toutes les dépendances qui sont plus récentes que la cible
$^  |nom de toutes les dépendances
$*  |chaîne de caractères extraite par un filtre

Par exemple :

```makefile
main : main.c
    gcc –o $@ $<
```

liens
-----

* [[ make.pdf | pdf/make.pdf ]], le même [[ici|http://dpt-info.u-strasbg.fr/~mathis/Enseignement/IPA/MakefileDir/make.pdf ]]
* [[ http://gl.developpez.com/tutoriel/outil/makefile ]]
