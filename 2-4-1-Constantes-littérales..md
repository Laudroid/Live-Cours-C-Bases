# Séance 2 : Les Fondamentaux du C (4 heures)

## Partie 4 : Les Constantes

### 1. Constantes littérales

---

## 1. Définition des constantes littérales

Une **constante littérale** est une valeur fixe explicitement inscrite dans le code source d’un programme. Contrairement aux variables, ces valeurs ne changent jamais au cours de l’exécution. Elles représentent des entiers, des nombres à virgule flottante, des caractères ou des chaînes de caractères.

---

## 2. Types de constantes littérales en C

| Type               | Exemple littéral               | Description                                |
|--------------------|-------------------------------|--------------------------------------------|
| Entier             | `42`, `-7`, `0xFF`, `0123`    | Nombres entiers en décimal, hexadécimal ou octal |
| Virgule flottante  | `3.14`, `-0.001`, `2.0E-3`    | Nombres réels, avec notation exponentielle possible |
| Caractère          | `'A'`, `'0'`, `'\n'`           | Un seul caractère, entre apostrophes, incluant les caractères d’échappement |
| Chaîne de caractères | `"Bonjour"`, `"C\nest bien!"` | Suite de caractères terminée par un caractère nul (`\0`) |

---

## 3. Détail des constantes littérales

- **Constantes entières** :  
  Sont interprétées comme `int` par défaut, mais peuvent porter des suffixes `u`, `U` (unsigned), `l`, `L` (long), `ll`, `LL` (long long) pour modifier leur type.  
  Exemples :  
  ```c
  100U   // unsigned int  
  500L   // long int  
  0x1A3  // hexadécimal (419 décimal)  
  012    // octal (10 décimal)  
  ```

- **Constantes flottantes** :  
  Par défaut, ce sont des `double`. Le suffixe `f` ou `F` indique un `float`. Le suffixe `l` ou `L` représente un `long double`.  
  Exemples :  
  ```c
  3.14      // double  
  2.5f      // float  
  1.0e-3L   // long double  
  ```

- **Constantes caractères** :  
  Un caractère est encodé selon la table ASCII ou Unicode (en `char`). Les caractères d’échappement permettent de représenter des tabulations, retours à la ligne (`'\n'`), guillemets, antislash, etc.  
  Par exemple :  
  ```c
  '\t'    // tabulation horizontale  
  '\''    // apostrophe  
  ```

- **Constantes chaînes de caractères** :  
  Une séquence de caractères terminée par `\0`. Elles sont de type `const char[]`.  
  Exemple :  
  ```c
  "Hello, World!\n"
  ```

---

## 4. Exemples d’utilisation

```c
#include <stdio.h>

int main() {
    // Constante entière
    int nombre = 42;

    // Constante flottante
    float pi = 3.14f;

    // Constante caractère
    char lettre = 'A';

    // Constante chaîne de caractères
    char message[] = "Bienvenue en C";

    printf("Nombre : %d\n", nombre);
    printf("Pi : %.2f\n", pi);
    printf("Lettre : %c\n", lettre);
    printf("Message : %s\n", message);

    return 0;
}
```

---

## 5. Caractéristiques importantes

- Les constantes littérales sont immuables, il n’est pas possible de leur assigner une nouvelle valeur.
- Le compilateur optimise souvent l’utilisation des constantes pour réduire la consommation mémoire.
- Les chaînes littérales occupent une zone spécifique en mémoire (souvent en mémoire en lecture seule).

---

## 6. Diagramme Mermaid : classification des constantes littérales en C

```mermaid
graph TD
    A[Constantes littérales] --> B[Entiers]
    A --> C[Virgule flottante]
    A --> D[Caractères]
    A --> E[Chaînes de caractères]

    B --> B1[Décimal]
    B --> B2[Hexadécimal]
    B --> B3[Octal]

    C --> C1[Float (suffixe f)]
    C --> C2[Double (par défaut)]
    C --> C3[Long double (suffixe l)]

    D --> D1[Caractère simple]
    D --> D2[Caractère d’échappement]

    E --> E1[Tableau de caractères]
```

---

## 7. Sources utilisées

- cppreference.com - [Integer literals](https://en.cppreference.com/w/c/language/integer_constant)  
- cppreference.com - [Floating literals](https://en.cppreference.com/w/c/language/floating_constant)  
- ISO/IEC 9899:2018 (C18 Standard) - Chapitre 6.4 (Literals and constants)  
- TutorialsPoint - [C Constants](https://www.tutorialspoint.com/cprogramming/c_constants.htm)  

---

Les constantes littérales constituent le socle des valeurs immuables utilisées dans les programmes C. Leur maîtrise est nécessaire pour écrire du code clair et efficace, et pour comprendre le typage implicite des données.