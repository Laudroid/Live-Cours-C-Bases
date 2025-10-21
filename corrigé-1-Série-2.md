

# Corrigé – Thème : Boucles imbriquées et affichage de motifs

---

##  **Exercice 1 — Ligne d’étoiles**

```c
#include <stdio.h>

int main() {
    // On veut afficher 10 étoiles sur une même ligne
    for (int i = 0; i < 10; i++) {
        printf("*"); // pas de saut de ligne ici
    }

    printf("\n"); // retour à la ligne après la série d'étoiles
    return 0;
}
```

 **Explication :**

* La boucle `for` s’exécute 10 fois (`i` de 0 à 9).
* Chaque itération affiche une étoile `*`.
* Le `\n` final sert juste à aller à la ligne après le motif.

---

##  **Exercice 2 — Carré plein d’étoiles**

```c
#include <stdio.h>

int main() {
    // Boucle extérieure : gère les lignes (10 lignes)
    for (int i = 0; i < 10; i++) {
        // Boucle intérieure : gère les colonnes (10 colonnes)
        for (int j = 0; j < 10; j++) {
            printf("*");
        }
        printf("\n"); // saut de ligne à la fin de chaque rangée
    }
    return 0;
}
```

 **Explication :**

* Chaque ligne contient 10 étoiles.
* Une fois une ligne terminée, on fait un retour à la ligne (`\n`) pour passer à la suivante.

---

##  **Exercice 3 — Carré vide**

```c
#include <stdio.h>

int main() {
    int n = 10;

    for (int i = 0; i < n; i++) {         // Parcours des lignes
        for (int j = 0; j < n; j++) {     // Parcours des colonnes
            // On remplit les bords : première/dernière ligne ou première/dernière colonne
            if (i == 0 || i == n - 1 || j == 0 || j == n - 1) {
                printf("*");
            } else {
                printf(" "); // espaces à l'intérieur
            }
        }
        printf("\n"); // retour à la ligne à chaque fin de ligne
    }
    return 0;
}
```

 **Explication :**

* Les étoiles sont affichées uniquement sur les **bords** du carré.
* `i == 0` ou `i == n - 1` → première/dernière ligne pleine.
* `j == 0` ou `j == n - 1` → première/dernière colonne pleine.
* Les autres cases sont remplacées par des espaces `" "`.

---

##  **Exercice 4 — Triangle plein**

###  Objectif : générer une forme dont la taille varie à chaque ligne

```c
#include <stdio.h>

int main() {
    int lignes = 8; // hauteur du triangle

    for (int i = 1; i <= lignes; i++) {
        for (int j = 1; j <= i; j++) {
            printf("*");
        }
        printf("\n");
    }

    return 0;
}
```

 **Explication :**

* La première boucle gère le nombre total de lignes.
* La seconde affiche autant d’étoiles que le numéro de la ligne (`i`).
* Résultat : une forme triangulaire croissante.

---

##  **Exercice 5 — Triangle vide**

###  Objectif : combiner boucles et conditions pour un motif creux

```c
#include <stdio.h>

int main() {
    int lignes = 8;

    for (int i = 1; i <= lignes; i++) {       // gestion des lignes
        for (int j = 1; j <= i; j++) {        // gestion des colonnes
            // Conditions pour afficher une étoile :
            // - première colonne
            // - dernière colonne de la ligne
            // - dernière ligne (pleine)
            if (j == 1 || j == i || i == lignes) {
                printf("*");
            } else {
                printf(" "); // intérieur du triangle
            }
        }
        printf("\n"); // retour à la ligne à chaque ligne
    }

    return 0;
}
```

 **Explication :**

* Pour les lignes intermédiaires : seules les **bords gauche et droit** ont des étoiles.
* La **dernière ligne** (`i == lignes`) est remplie d’étoiles.
* Cela crée un triangle creux mais fermé à la base.
