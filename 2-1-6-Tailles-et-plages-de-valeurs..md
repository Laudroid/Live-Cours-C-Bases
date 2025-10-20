# Séance 2 : Les Fondamentaux du C (4 heures)

## Partie 1 : Variables et Types de Données

### 6. Tailles et plages de valeurs

---

## 1. Introduction : taille et plage d’un type de donnée

En C, chaque type de variable occupe un espace mémoire défini appelé *taille* (exprimée en octets). Cette taille détermine la *plage de valeurs* que le type peut contenir.

- **Taille** : nombre d’octets réservés en mémoire.
- **Plage** : ensemble des valeurs possibles stockées dans cet espace.

---

## 2. Variabilité selon les plateformes

- La norme C ne fixe pas explicitement la taille des types fondamentaux mais impose seulement des bornes minimales.
- La taille peut varier entre architectures (32-bit, 64-bit) et compilateurs.
- La constante `sizeof()` permet d’obtenir la taille en octets à l’exécution ou via la compilation.

---

## 3. Tailles typiques des types standard (sur architecture commune 64-bit Linux / Windows)

| Type                      | Taille (octets) | Plage (signé)                                      | Plage (non signé)                          |
|---------------------------|-----------------|--------------------------------------------------|--------------------------------------------|
| `char`                    | 1               | -128 à 127                                       | 0 à 255                                    |
| `short`                   | 2               | -32,768 à 32,767                                 | 0 à 65,535                                 |
| `int`                     | 4               | -2,147,483,648 à 2,147,483,647                   | 0 à 4,294,967,295                          |
| `long`                    | 8 (sur 64 bits) | -9,223,372,036,854,775,808 à 9,223,372,036,854,775,807 | 0 à 18,446,744,073,709,551,615           |
| `long long`               | 8               | même que `long`                                 | même que `unsigned long`                    |
| `_Bool` / `bool`          | 1               | 0 (false) ou 1 (true)                            | Même                                      |
| `float`                   | 4               | ±1.5 × 10^−45 à ±3.4 × 10^38 (environ)           | -                                          |
| `double`                  | 8               | ±5.0 × 10^−324 à ±1.7 × 10^308                    | -                                          |

---

## 4. Principes pour calculer les plages des types entiers

Pour les types entiers signés (complément à deux) occupant *N* octets (soit 8×N bits) :

- Plage signée : de -2^{8N-1} à 2^{8N-1} - 1
- Plage non signée : de 0 à 2^{8N} - 1

---

## 5. Vérification pratique avec `sizeof` et `limits.h`

```c
#include <stdio.h>
#include <limits.h>
#include <float.h>

int main() {
    printf("Taille de int: %zu octets\n", sizeof(int));
    printf("INT_MIN: %d, INT_MAX: %d\n", INT_MIN, INT_MAX);

    printf("Taille de char: %zu octets\n", sizeof(char));
    printf("CHAR_MIN: %d, CHAR_MAX: %d\n", CHAR_MIN, CHAR_MAX);

    printf("Taille de long: %zu octets\n", sizeof(long));
    printf("LONG_MIN: %ld, LONG_MAX: %ld\n", LONG_MIN, LONG_MAX);

    printf("Taille de float: %zu octets\n", sizeof(float));
    printf("FLT_MIN: %e, FLT_MAX: %e\n", FLT_MIN, FLT_MAX);

    return 0;
}
```

---

## 6. Diagramme Mermaid : relation taille - plage des types entiers

```mermaid
flowchart TD
    Start["Type C"] --> Size[Int taille (octets)]
    Size --> Bits[Bits = 8 × taille]
    Bits --> SignedRange[Plage signée: -2^(bits-1) à 2^(bits-1)-1]
    Bits --> UnsignedRange[Plage non signée: 0 à 2^bits -1]
    SignedRange --> Result
    UnsignedRange --> Result
```

---

## 7. Points importants

- Toujours vérifier la taille avec `sizeof` pour éviter les erreurs de dépassement.
- Utiliser les constantes définies dans `<limits.h>` et `<float.h>` pour des plages garanties.
- Adapter le choix du type à la plage nécessaire pour économiser la mémoire.
- Ne pas présumer la taille fixe d’un type d’après le nombre octets le plus courant ; préférer des types fixes si besoin (`int32_t`, `uint64_t`...).

---

## 8. Sources utilisées

- cppreference.com - [Data types and limits](https://en.cppreference.com/w/c/language/types)  
- ISO/IEC 9899:2018 – Langage C standard (chapitres sur types et portabilité)  
- GNU GCC Documentation - [Data Types](https://gcc.gnu.org/onlinedocs/gcc/Types.html)  
- TutorialsPoint - [C Data Types and Limits](https://www.tutorialspoint.com/cprogramming/c_data_types.htm)  

---

Comprendre la relation entre taille mémoire et plages de valeurs permet d'écrire des programmes fiables et efficaces, en évitant des erreurs d’overflow ou d’usage mémoire inadapté.