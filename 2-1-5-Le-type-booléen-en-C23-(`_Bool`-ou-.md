# Séance 2 : Les Fondamentaux du C (4 heures)

## Partie 1 : Variables et Types de Données

### 5. Le type booléen en C23 (`_Bool` ou `bool` avec `<stdbool.h>`)

---

## 1. Contexte et introduction

Avant la norme C99, le langage C ne disposait pas nativement d’un type booléen. Les programmeurs utilisaient souvent des entiers (`int`) avec la convention 0 = faux et toute autre valeur ≠ 0 = vrai.

Avec la norme C99 (maintenue en C23), un type booléen dédié a été introduit : `_Bool`, et une macro `bool` est définie dans `<stdbool.h>` pour simplifier son usage.

---

## 2. Déclaration du type booléen

- Le type natif du langage est `_Bool` (mot-clé réservé).
- L’inclusion de la bibliothèque `<stdbool.h>` permet d’utiliser `bool` comme alias de `_Bool` et les constantes `true` et `false`.

```c
#include <stdbool.h>

bool est_actif = true;
_Bool est_valide = 0;  // false
```

---

## 3. Caractéristiques du type `_Bool`

- Taille généralement 1 octet (mais peut varier).
- Valeur 0 représente `false`.
- Toute valeur non nulle est convertie en `1` (true) lors de l’affectation à une variable `_Bool`.

---

## 4. Exemple d’utilisation

```c
#include <stdio.h>
#include <stdbool.h>

int main() {
    bool condition = true;
    _Bool autre_condition = 0;

    if (condition) {
        printf("condition est vraie\n");
    }

    if (!autre_condition) {
        printf("autre_condition est fausse\n");
    }

    // Affectation de valeurs entières
    autre_condition = 42; // automatiquement converti en true (1)

    printf("autre_condition vaut %d\n", autre_condition);

    return 0;
}
```

**Sortie :**

```
condition est vraie
autre_condition est fausse
autre_condition vaut 1
```

---

## 5. Comparaison avec les pratiques antérieures

| Avant C99                              | Avec C99 et suivantes                         |
|--------------------------------------|----------------------------------------------|
| `int flag = 0;`                      | `bool flag = false;`                          |
| `if (flag)` avec 0 ou non-0          | `if (flag)` avec `true`/`false`              |
| Pas de type booléen dédié             | Type booléen natif clair et standardisé       |
| Usage moins explicite, moins sûr      | Meilleure lisibilité, sécurité sémantique     |

---

## 6. Diagramme Mermaid : cycle de vie d’une variable booléenne

```mermaid
flowchart TD
    A[Déclaration (_Bool ou bool)] --> B[Affectation d'une valeur]
    B --> C{Valeur numérique ?}
    C -->|0| D[Variable = false]
    C -->|Non 0| E[Variable = true (1)]
    D --> F[Utilisation dans conditions if/while]
    E --> F
```

---

## 7. Points clés à retenir

- Inclure `<stdbool.h>` pour définir correctement `bool`, `true`, `false`.
- `_Bool` est le mot-clé natif, `bool` est une macro pour faciliter la lecture.
- Conversion automatique lors de l’affectation : toute valeur non nulle devient `1`.
- Favoriser l’utilisation de `bool` pour clarifier l’intention du code.
- Programmation plus expressive et sûre dans les structures conditionnelles.

---

## 8. Sources utilisées

- cppreference.com - [_Bool and boolean type](https://en.cppreference.com/w/c/language/_Bool)  
- ISO/IEC 9899:2018 (C18) and draft C23 standards - sections sur `_Bool`  
- TutorialsPoint - [C Boolean Data Type](https://www.tutorialspoint.com/cprogramming/c_boolean_data_type.htm)  
- GNU GCC documentation - [stdbool.h](https://gcc.gnu.org/onlinedocs/cpp/Standard-Predefined-Macros.html)  

---

Le type booléen natif apporte une sémantique claire et simplifie la gestion des conditions logiques, en évitant les approximations liées à l’usage des entiers comme booléens.