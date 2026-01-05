# Séance 2 : Les Fondamentaux du C (4 heures)

## Partie 2 : Opérateurs en C

### 4. Opérateurs relationnels : `==`, `!=`, `<`, `>`, `<=`, `>=`

---

## 1. Rôle des opérateurs relationnels

Les opérateurs relationnels servent à comparer deux expressions en C. Ils retournent un résultat de type `_Bool` (0 pour faux, 1 pour vrai) et sont fondamentaux dans les structures conditionnelles et les boucles.

---

## 2. Description des opérateurs relationnels

| Opérateur | Signification                | Exemple          | Résultat                |
|-----------|-----------------------------|------------------|-------------------------|
| `==`      | Égal à                      | `a == b`         | vrai si a égale b       |
| `!=`      | Différent de                | `a != b`         | vrai si a différent de b|
| `<`       | Strictement inférieur à      | `a < b`          | vrai si a < b           |
| `>`       | Strictement supérieur à      | `a > b`          | vrai si a > b           |
| `<=`      | Inférieur ou égal à          | `a <= b`         | vrai si a ≤ b           |
| `>=`      | Supérieur ou égal à          | `a >= b`         | vrai si a ≥ b           |

---

## 3. Syntaxe et fonctionnement

- Ces opérateurs comparent des valeurs numériques (entiers, flottants) ou des pointeurs.
- Le résultat est une valeur entière 0 ou 1 (correspondant à `false` ou `true`).
- Ils s’utilisent principalement dans les conditions `if`, `while`, `for`, ou toute expression booléenne.

---

## 4. Exemples pratiques

```c
#include <stdio.h>

int main() {
    int a = 5, b = 7;

    printf("a == b : %d\n", a == b);  // 0 (faux)
    printf("a != b : %d\n", a != b);  // 1 (vrai)
    printf("a < b  : %d\n", a < b);   // 1 (vrai)
    printf("a > b  : %d\n", a > b);   // 0 (faux)
    printf("a <= b : %d\n", a <= b);  // 1 (vrai)
    printf("a >= b : %d\n", a >= b);  // 0 (faux)

    // Exemple avec flottants
    float x = 3.14, y = 3.14;
    printf("x == y : %d\n", x == y);   // 1 (vrai)

    return 0;
}
```

---

## 5. Utilisation dans une condition

```c
int age = 18;

if (age >= 18) {
    printf("Accès autorisé.\n");
} else {
    printf("Accès refusé.\n");
}
```

---

## 6. Opérateurs relationnels et conversion en booléen

- Le résultat est une valeur entière 0 ou 1.
- Compatible avec le type `_Bool` (introduit en C99).
- Exemple :

```c
#include <stdbool.h>

bool est_adulte = (age >= 18);
```

---

## 7. Précautions

- Pour comparer des flottants, attention aux imprécisions dues à la représentation en virgule flottante.
- Ne pas confondre `==` (égalité) avec `=` (affectation).
- Préférer toujours un espace autour des opérateurs pour éviter des erreurs de lecture.

---

## 8. Diagramme Mermaid : processus d’évaluation d’une expression relationnelle

```mermaid
flowchart TD
    A[Lire opérandes a et b] --> B[Sélectionner opérateur relationnel]
    B --> C[Comparer a et b selon l'opérateur]
    C --> D{Condition vraie?}
    D -->|Oui| E[Retourner 1 (true)]
    D -->|Non| F[Retourner 0 (false)]
```

---

## 9. Sources utilisées

- cppreference.com - [Relational operators](https://en.cppreference.com/w/c/language/operator_comparison)  
- ISO/IEC 9899:2018 (C18 Standard) - section 6.5.8  
- TutorialsPoint - [C Relational Operators](https://www.tutorialspoint.com/cprogramming/c_operators.htm)  
- GNU GCC Documentation - [Expressions](https://gcc.gnu.org/onlinedocs/gcc/Expressions.html)  

---

Les opérateurs relationnels fournissent un moyen clair et simple pour comparer des valeurs et construire des expressions booléennes essentielles dans la logique de tout programme C.