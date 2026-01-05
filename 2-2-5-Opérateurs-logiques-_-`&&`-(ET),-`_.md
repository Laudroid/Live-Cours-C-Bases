# Séance 2 : Les Fondamentaux du C (4 heures)

## Partie 2 : Opérateurs en C

### 5. Opérateurs logiques : `&&` (ET), `||` (OU), `!` (NON)

---

## 1. Rôle des opérateurs logiques

Les opérateurs logiques permettent de combiner ou d'inverser des expressions booléennes (vraies ou fausses). Ils sont utilisés pour construire des conditions complexes dans les structures de contrôle (conditions, boucles).

---

## 2. Description des opérateurs logiques

| Opérateur | Nom        | Fonction                                                      | Exemple                     |
|-----------|------------|--------------------------------------------------------------|-----------------------------|
| `&&`      | ET logique | Résulte en vrai (1) si **les deux** opérandes sont vrais     | `(a > 0) && (b < 10)`       |
| `||`      | OU logique | Résulte en vrai si **au moins un** des opérandes est vrai     | `(x == 5) || (y != 3)`      |
| `!`       | NON logique| Inverse la valeur booléenne (vrai devient faux, et vice versa) | `!(a == b)`                 |

---

## 3. Comportement détaillé

- En C, 0 représente *faux* et toute valeur non nulle représente *vrai*.
- `&&` et `||` effectuent une **évaluation paresseuse** ("short-circuit") :
  - Pour `&&`, si le premier opérande est faux, le deuxième n’est pas évalué.
  - Pour `||`, si le premier opérande est vrai, le deuxième n’est pas évalué.
- L’opérateur `!` ne prend qu’un seul opérande et inverse sa valeur booléenne.

---

## 4. Exemples

```c
#include <stdio.h>

int main() {
    int a = 5, b = 10, c = 0;

    printf("a > 0 && b < 20 : %d\n", (a > 0) && (b < 20)); // 1 (vrai)
    printf("a > 0 && c != 0 : %d\n", (a > 0) && (c != 0)); // 0 (faux)
    printf("a == 5 || b == 5 : %d\n", (a == 5) || (b == 5)); // 1 (vrai)
    printf("! (a == b) : %d\n", !(a == b));                   // 1 (vrai)
    
    // Illustration évaluation paresseuse
    int x = 0;
    if ((x != 0) && (10 / x > 1)) { // La division par zéro est évitée
        printf("Pas d'erreur, second test non exécuté.\n");
    } else {
        printf("Premier test faux, second non évalué.\n");
    }

    return 0;
}
```

---

## 5. Précédence et associativité

| Opérateur | Description       | Précédence (plus haut d’abord) | Associativité   |
|-----------|-------------------|-------------------------------|-----------------|
| `!`       | NON logique       | 3                             | Droite à gauche |
| `&&`      | ET logique        | 2                             | Gauche à droite |
| `||`      | OU logique        | 1                             | Gauche à droite |

---

## 6. Diagramme Mermaid : évaluation des opérateurs logiques

```mermaid
flowchart TD
    Start[Début]
    Start --> Expr1[Évaluer opérande 1]

    subgraph AND "ET logique (&&)"
        Expr1 -->|False| FalseAND[Résultat False]
        Expr1 -->|True| Expr2[Évaluer opérande 2]
        Expr2 --> ResultAND[Résultat de l'opération]
    end

    subgraph OR "OU logique (||)"
        Expr1 -->|True| TrueOR[Résultat True]
        Expr1 -->|False| Expr2_2[Évaluer opérande 2]
        Expr2_2 --> ResultOR[Résultat de l'opération]
    end

    subgraph NOT "NON logique (!)"
        Expr1_NOT[Évaluer opérande]
        Expr1_NOT --> ResultNOT[Inverser valeur booléenne]
    end
```

---

## 7. Bonnes pratiques

- Utiliser les opérateurs logiques pour combiner clairement les conditions.
- Exploiter l’évaluation paresseuse pour éviter des calculs coûteux ou des erreurs (exemple division par zéro).
- Toujours utiliser les parenthèses pour clarifier la priorité des opérations logiques.
- Attention à ne pas confondre `&` (ET bit-à-bit) avec `&&` (ET logique).

---

## 8. Sources utilisées

- cppreference.com - [Logical AND, OR, NOT operators](https://en.cppreference.com/w/c/language/operator_logical)  
- ISO/IEC 9899:2018 (C18 Standard) - section 6.5.13-15  
- TutorialsPoint - [C Logical Operators](https://www.tutorialspoint.com/cprogramming/c_operators.htm)  
- GNU GCC Documentation - [Expressions](https://gcc.gnu.org/onlinedocs/gcc/Expressions.html)  

---

Les opérateurs logiques permettent de créer des conditions complexes indispensables pour contrôler le flux des programmes en C. Leur compréhension précise, notamment du comportement d’évaluation paresseuse, évite des erreurs fréquentes.