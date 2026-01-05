# Séance 4 : Fonctions et Modularité (4 heures)

## Partie 3 : Fonctions de Bibliothèques Standards

### 2. Inclusion de bibliothèques avec `#include`

---

## 1. Rôle de l’instruction `#include`

- Directive de préprocesseur qui sert à **inclure le contenu d’un fichier source ou d’en-tête** avant la compilation.
- Permet d’utiliser les **déclarations et définitions** présentes dans ces fichiers, comme les prototypes de fonctions, macros, constantes, et types.
- Facilite la modularité du code en réutilisant des bibliothèques standards ou personnalisées.

---

## 2. Syntaxe et types d’inclusion

### 2.1 Inclusion avec chevrons `< >`

```c
#include <nom_de_fichier.h>
```

- Recherche le fichier dans les **répertoires systèmes et bibliothèques standards**.
- Utilisée pour inclure des bibliothèques **standard**.

**Exemple :**

```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>
```

### 2.2 Inclusion avec guillemets `" "`

```c
#include "mon_fichier.h"
```

- Recherche d'abord dans le **répertoire courant**, puis dans les répertoires système.
- Utilisée surtout pour les fichiers **personnalisés** (headers locaux).

---

## 3. Fonctionnement pendant la compilation

- Le préprocesseur **copie littéralement le contenu** du fichier inclus à la place de l’instruction `#include`.
- Permet au compilateur d’avoir accès aux déclarations indispensables pour la compilation correcte.

---

## 4. Exemple concret

Supposons deux fichiers :

**fichier `math_utils.h`**

```c
#ifndef MATH_UTILS_H
#define MATH_UTILS_H

double carre(double x);

#endif
```

**fichier `math_utils.c`**

```c
#include "math_utils.h"

double carre(double x) {
    return x * x;
}
```

**fichier `main.c`**

```c
#include <stdio.h>
#include "math_utils.h"

int main() {
    double val = 5.0;
    printf("Carré de %.2f = %.2f\n", val, carre(val));
    return 0;
}
```

- `main.c` inclut la déclaration de la fonction `carre` via `"math_utils.h"`.
- Le fichier `.c` avec la définition est compilé avec `main.c`.
- Permet séparation claire entre interface (`.h`) et implémentation (`.c`).

---

## 5. Diagramme Mermaid : inclusion et compilation

```mermaid
graph TD
    A[main.c] -->|#include "math_utils.h"| B[math_utils.h]
    C[math_utils.c] -->|#include "math_utils.h"| B
    subgraph Compilation
      B
      A
      C
    end
```

---

## 6. Bonnes pratiques liées à l’inclusion

- Utiliser les **gardes d’inclusion** (`#ifndef`, `#define`, `#endif`) pour éviter les doubles inclusions.
- Préférer les fichiers `.h` pour déclarer les prototypes et les constantes, gardant les définitions dans les fichiers `.c`.
- Inclure uniquement les fichiers nécessaires dans chaque unité source pour réduire les dépendances.

---

## 7. Sources utilisées

- [cppreference.com - #include Directive](https://en.cppreference.com/w/c/preprocessor/include)  
- [TutorialsPoint - C Header Files](https://www.tutorialspoint.com/cprogramming/c_header_files.htm)  
- [GeeksforGeeks - #include in C](https://www.geeksforgeeks.org/include-preprocessor-directives-in-c-c-with-examples/)  
- ISO/IEC 9899:2018 (C18) – Chapitre 6.10

---

L’utilisation de `#include` est la pierre angulaire de la modularité en C, permettant de composer un programme à partir de composants séparés tout en donnant accès aux définitions nécessaires. Comprendre son fonctionnement favorise l’organisation rationnelle du code.