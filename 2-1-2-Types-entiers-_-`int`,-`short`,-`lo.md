# Séance 2 : Les Fondamentaux du C (4 heures)

## Partie 1 : Variables et Types de Données

### 2. Types entiers : `int`, `short`, `long`, `long long`, `unsigned`

---

## 1. Introduction aux types entiers en C

Les types entiers sont utilisés pour stocker des nombres entiers (sans parties décimales). Le langage C propose plusieurs variantes pour optimiser l’espace mémoire ou s’adapter à différentes plages de valeurs. Ces types sont signés par défaut, c’est-à-dire qu’ils peuvent stocker à la fois des nombres positifs et négatifs. Le modificateur `unsigned` permet de ne stocker que des valeurs positives, doublant ainsi la valeur maximale possible.

---

## 2. Description des types entiers standard

| Type            | Taille typique (octets)¹ | Plage de valeurs signée                         | Plage de valeurs non signée (unsigned)               |
|-----------------|-------------------------|-------------------------------------------------|------------------------------------------------------|
| `short`         | 2                       | -32,768 à 32,767                                | 0 à 65,535                                           |
| `int`           | 4                       | -2,147,483,648 à 2,147,483,647                  | 0 à 4,294,967,295                                     |
| `long`          | 4 ou 8                  | -2,147,483,648 à 2,147,483,647 (4 octets) ou    | 0 à 4,294,967,295 (4 octets) ou                       |
|                 |                         | -9,223,372,036,854,775,808 à 9,223,372,036,854,775,807 (8 octets) | 0 à 18,446,744,073,709,551,615 (8 octets)            |
| `long long`     | 8                       | -9,223,372,036,854,775,808 à 9,223,372,036,854,775,807 | 0 à 18,446,744,073,709,551,615                       |

¹La taille dépend de la plateforme et du compilateur, les valeurs indiquées correspondent à des configurations courantes (32-bit ou 64-bit).

---

## 3. Usage du modificateur `unsigned`

- Enlever le signe permet d’élargir la plage des valeurs positives.
- Exemple : un `unsigned int` peut représenter des nombres de 0 à plus de 4 milliards.
- Important : ne pas mélanger variables signées et non signées dans des opérations arithmétiques pour éviter des bugs.

---

## 4. Exemples en code

```c
#include <stdio.h>

int main() {
    short s = -10;
    unsigned short us = 60000;

    int i = -1000;
    unsigned int ui = 3000000000U;  // suffixe U pour unsigned

    long l = 100000L;              // suffixe L pour long
    unsigned long ul = 4000000000UL;

    long long ll = -9000000000000000000LL; // suffixe LL pour long long
    unsigned long long ull = 18000000000000000000ULL;

    printf("short s = %d\n", s);
    printf("unsigned short us = %u\n", us);
    printf("int i = %d\n", i);
    printf("unsigned int ui = %u\n", ui);
    printf("long l = %ld\n", l);
    printf("unsigned long ul = %lu\n", ul);
    printf("long long ll = %lld\n", ll);
    printf("unsigned long long ull = %llu\n", ull);

    return 0;
}
```

---

## 5. Rappels importants

- La taille des types entiers (`sizeof`) peut varier selon la machine.
- Toujours vérifier la capacité nécessaire aux données que vous manipulez.
- Prendre en compte la nature signée ou non pour éviter des erreurs dans les comparaisons et calculs.

---

## 6. Diagramme Mermaid : hiérarchie et plage des types entiers

```mermaid
graph TD
    A[Types entiers] --> B[int (4 octets)]
    A --> C[short (2 octets)]
    A --> D[long (4 ou 8 octets)]
    A --> E[long long (8 octets)]

    B --> F[plage: -2 147 483 648 à 2 147 483 647]
    B --> G[unsigned: 0 à 4 294 967 295]

    C --> H[plage: -32 768 à 32 767]
    C --> I[unsigned: 0 à 65 535]

    D --> J[plage: variable selon plateforme]
    D --> K[unsigned: variable]

    E --> L[plage: -9 223 372 036 854 775 808 à 9 223 372 036 854 775 807]
    E --> M[unsigned: 0 à 18 446 744 073 709 551 615]
```

---

## 7. Sources utilisées

- cppreference.com - [Integer types (C)](https://en.cppreference.com/w/c/language/integer)
- ISO/IEC 9899:2018 – Langage C standard
- TutorialsPoint - [C Data Types](https://www.tutorialspoint.com/cprogramming/c_data_types.htm)
- GNU GCC documentation - [Integer Types and Sizes](https://gcc.gnu.org/onlinedocs/gcc/Types.html)

---

Comprendre ces types entiers et leurs limites permet d’adapter efficacement la gestion des données numériques selon la nature des besoins et des architectures cibles.