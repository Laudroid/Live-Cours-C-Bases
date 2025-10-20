# Séance 2 : Les Fondamentaux du C (4 heures)

## Partie 1 : Variables et Types de Données

### 3. Types flottants : `float`, `double`

---

## 1. Introduction aux types flottants

Les types flottants permettent de représenter des nombres réels, avec une partie fractionnaire, dans un format en virgule flottante. Ils sont essentiels pour gérer des données précises comme des mesures physiques, des calculs scientifiques ou financiers.

En C, les deux types flottants principaux sont :

- `float` : simple précision
- `double` : double précision

---

## 2. Description des types flottants

| Type    | Taille typique (octets) | Précision approximative      | Plage typique                     |
|---------|-------------------------|-----------------------------|----------------------------------|
| `float` | 4                       | 6 à 9 chiffres décimaux      | ±1.5 × 10^−45 à ±3.4 × 10^38     |
| `double`| 8                       | 15 à 17 chiffres décimaux    | ±5.0 × 10^−324 à ±1.7 × 10^308   |

**Notes** : Ces caractéristiques correspondent à la norme IEEE 754 sur la plupart des architectures modernes.

---

## 3. Syntaxe de déclaration et initialisation

```c
float vitesse = 12.5f;   // suffixe 'f' optionnel mais recommandé pour float
double distance = 12345.6789;
```

Sans suffixe, un littéral à virgule flottante est considéré comme `double` par défaut en C.

---

## 4. Particularités du calcul en virgule flottante

- Les opérations peuvent engendrer des imprécisions, dues à la représentation binaire.
- Les comparaisons d’égalité directe entre flottants sont déconseillées.
- Utiliser une tolérance (epsilon) pour comparer deux nombres flottants.

---

## 5. Exemples illustrés

```c
#include <stdio.h>
#include <math.h>

int main() {
    float pi_float = 3.1415927f;   // simple précision
    double pi_double = 3.141592653589793;

    printf("float pi = %.7f\n", pi_float);
    printf("double pi = %.15lf\n", pi_double);

    // Comparaison prudente
    double a = 0.1 + 0.2;
    double b = 0.3;
    double epsilon = 0.00001;

    if (fabs(a - b) < epsilon) {
        printf("a et b sont égaux avec tolérance epsilon\n");
    } else {
        printf("a et b sont différents\n");
    }

    return 0;
}
```

---

## 6. Diagramme Mermaid : relations entre types numériques en C

```mermaid
graph TD
    A[Types numériques en C] --> B[Entiers (int, short, long...)]
    A --> C[Flottants]
    C --> D[float - simple précision (4 octets)]
    C --> E[double - double précision (8 octets)]
```

---

## 7. Conseils pratiques

- Choisir `float` lorsqu’on souhaite économiser de la mémoire avec une précision modérée.
- Préférer `double` lorsque la précision est importante.
- Attention aux dépassements et erreurs d’arrondi.
- Utiliser des fonctions mathématiques compatibles avec le type (`sin`, `cos`, `sqrt`, etc.)

---

## 8. Sources utilisées

- ISO/IEC 9899:2018 – Langage C standard (section sur les types flottants)  
- cppreference.com - [Floating-point types](https://en.cppreference.com/w/c/language/floating)  
- TutorialsPoint - [C Floating Point](https://www.tutorialspoint.com/cprogramming/c_floating_point.htm)  
- IEEE 754 Standard overview - [https://ieeexplore.ieee.org/document/8766229](https://ieeexplore.ieee.org/document/8766229)  

---

Maîtriser les types flottants et leurs limites est indispensable pour tout calcul nécessitant une représentation précise des valeurs réelles en programmation C.