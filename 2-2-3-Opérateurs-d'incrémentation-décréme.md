# Séance 2 : Les Fondamentaux du C (4 heures)

## Partie 2 : Opérateurs en C

### 3. Opérateurs d'incrémentation/décrémentation : `++`, `--`

---

## 1. Présentation des opérateurs `++` et `--`

Les opérateurs d'incrémentation et de décrémentation permettent d'ajouter ou de soustraire 1 à une variable entière de façon concise et efficace.

- `++` : incrémente la valeur d'une variable de 1.
- `--` : décrémente la valeur d'une variable de 1.

Ces opérateurs sont uniquement applicables aux variables modifiables (lvalues).

---

## 2. Formes d’utilisation : préfixe et suffixe

- **Pré-incrémentation / Pré-décrémentation (`++var`, `--var`)**  
  La variable est modifiée **avant** d’être utilisée dans une expression.

- **Post-incrémentation / Post-décrémentation (`var++`, `var--`)**  
  La variable est utilisée dans l'expression **avant** d’être modifiée.

---

## 3. Différence fonctionnelle entre préfixe et suffixe

```c
int a = 5;
int b;

b = ++a;   // pré-incrémentation
// a passe à 6, b reçoit 6

a = 5;
b = a++;   // post-incrémentation
// b reçoit 5, puis a passe à 6
```

---

## 4. Exemple complet

```c
#include <stdio.h>

int main() {
    int x = 10;
    int y;

    // Post-incrémentation
    y = x++;
    printf("Post-incrémentation: x = %d, y = %d\n", x, y);

    // Pré-incrémentation
    x = 10;
    y = ++x;
    printf("Pré-incrémentation: x = %d, y = %d\n", x, y);

    // Post-décrémentation
    y = x--;
    printf("Post-décrémentation: x = %d, y = %d\n", x, y);

    // Pré-décrémentation
    x = 10;
    y = --x;
    printf("Pré-décrémentation: x = %d, y = %d\n", x, y);

    return 0;
}
```

**Sortie attendue :**

```
Post-incrémentation: x = 11, y = 10
Pré-incrémentation: x = 11, y = 11
Post-décrémentation: x = 10, y = 11
Pré-décrémentation: x = 9, y = 9
```

---

## 5. Précautions et bonnes pratiques

- Eviter d'utiliser les opérateurs d'incrémentation/décrémentation plusieurs fois sur la même variable dans une seule expression, cela peut provoquer un comportement indéfini.
- Favoriser des expressions simples pour garantir la lisibilité et la portabilité du code.
- Utiliser préférentiellement la forme préfixe dans les boucles lorsqu'il n'y a pas de différence fonctionnelle, par convention et parfois pour une légère optimisation.
- Ces opérateurs ne s’appliquent pas aux types flottants en standard C.

---

## 6. Diagramme Mermaid : cycle d’utilisation des opérateurs `++` et `--`

```mermaid
flowchart TD
    A[Variable initiale] --> B{Opérateur ?}
    B -->|Préfixe (++var / --var)| C[Incrémente/décrémente d'abord]
    B -->|Postfixe (var++ / var--)| D[Retourne la valeur puis modifie]
    C --> E[Utilisation de la nouvelle valeur]
    D --> E[Utilisation de l’ancienne valeur]
```

---

## 7. Sources utilisées

- cppreference.com - [Increment and decrement operators](https://en.cppreference.com/w/c/language/operator_incdec)  
- ISO/IEC 9899:2018 (C18 Standard) - Section 6.5.3  
- TutorialsPoint - [C Increment and Decrement Operators](https://www.tutorialspoint.com/cprogramming/c_operators.htm)  
- GNU GCC Documentation - [Expressions](https://gcc.gnu.org/onlinedocs/gcc/Expressions.html)  

---

Les opérateurs `++` et `--` sont des raccourcis syntaxiques puissants qui permettent de modifier rapidement une variable entière par un ajustement simple. Comprendre la différence entre préfixe et suffixe évite des erreurs logiques fréquentes dans les expressions.