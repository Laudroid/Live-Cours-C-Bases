# Séance 4 : Fonctions et Modularité (4 heures)

## Partie 3 : Fonctions de Bibliothèques Standards

### 1. Présentation de quelques bibliothèques : `stdio.h`, `stdlib.h`, `math.h`

---

## 1. `stdio.h` : Entrée/Sortie standard (rappel)

Cette bibliothèque est centrale pour les opérations d’entrée/sortie console :

- `printf()`, `scanf()` : affichage et lecture formatée.
- `putchar()`, `getchar()` : caractères simples.
- Gestion des fichiers avec `fopen()`, `fclose()`, etc.

---

## 2. `stdlib.h` : Fonctions générales utilitaires

Inclut plusieurs fonctions importantes pour la gestion mémoire, le contrôle du programme, et la génération de nombres aléatoires.

### 2.1 Fonctions courantes

| Fonction         | Description                                  |
|------------------|----------------------------------------------|
| `exit(int status)` | Termine immédiatement le programme avec un code de sortie |
| `rand()`          | Génère un entier pseudo-aléatoire           |
| `srand(unsigned int seed)` | Initialise le générateur de nombres aléatoires |
| `malloc()`, `free()`  | Allocation et libération dynamique mémoire (hors de notre sujet immédiat) |

---

### 2.2 Exemple d’utilisation de `exit()` et `rand()`

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    srand(time(NULL)); // Initialisation du générateur

    int alea = rand() % 100; // Génère nombre entre 0 et 99
    printf("Nombre aléatoire généré : %d\n", alea);

    if (alea < 10) {
        printf("Valeur trop petite, sortie du programme.\n");
        exit(EXIT_FAILURE);  // Fin immédiate avec code erreur
    }

    printf("Programme continue...\n");
    return 0;
}
```

- `srand(time(NULL))` initialise la graine basée sur l'horloge système.
- `rand()` généré pseudo-aléatoire.
- `exit()` commande la terminaison immédiate avec un code.

---

## 3. `math.h` : Fonctions mathématiques

Fourni des fonctions pour réaliser des calculs mathématiques avancés.

### 3.1 Fonctions présentées

| Fonction         | Description                       | Prototype                           |
|------------------|---------------------------------|-----------------------------------|
| `sqrt(double x)`  | Racine carrée                   | `double sqrt(double x)`            |
| `pow(double x, double y)` | Puissance (x^y)            | `double pow(double x, double y)`  |
| `sin(double x)`   | Sinus (x en radians)             | `double sin(double x)`             |

---

### 3.2 Exemple d’utilisation

```c
#include <stdio.h>
#include <math.h>

int main() {
    double x = 9.0;
    printf("sqrt(%.1f) = %.2f\n", x, sqrt(x));

    double base = 2.0, exposant = 3.0;
    printf("%.1f^%.1f = %.2f\n", base, exposant, pow(base, exposant));

    double angle = 3.14159 / 2;  // ~ π/2 radians
    printf("sin(π/2) = %.2f\n", sin(angle));

    return 0;
}
```

---

## 4. Diagramme Mermaid : Relations entre bibliothèques et fonctions

```mermaid
graph LR
    A[Programme C] --> B{Bibliothèques}
    B --> C[stdio.h]
    B --> D[stdlib.h]
    B --> E[math.h]
    C --> F[printf(), scanf(), etc.]
    D --> G[exit(), rand(), srand()]
    E --> H[sqrt(), pow(), sin()]
```

---

## 5. Notes importantes

- Pour utiliser `math.h` sous Linux et certains environnements, il peut être nécessaire d’ajouter l’option `-lm` lors de la compilation (ex : `gcc fichier.c -o prog -lm`).
- Initialiser toujours `srand()` avant d’utiliser `rand()` pour éviter d’obtenir la même séquence à chaque exécution.
- `exit()` termine le programme immédiatement, contournant la fin normale du `main()`.

---

## 6. Sources utilisées

- [cppreference.com - stdio.h](https://en.cppreference.com/w/c/io)  
- [cppreference.com - stdlib.h](https://en.cppreference.com/w/c/memory)  
- [cppreference.com - math.h](https://en.cppreference.com/w/c/numeric/math)  
- [TutorialsPoint - C Standard Library](https://www.tutorialspoint.com/c_standard_library/index.htm)  
- ISO/IEC 9899:2018 (C18) – Section 7.22

---

Ce panorama des fonctions des bibliothèques standard courantes montre comment tirer parti des ressources préexistantes et fiables pour simplifier la programmation en C, tant dans l’affichage, la gestion du contrôle ou le calcul numérique.