# Séance 3 : Structures de Contrôle (4 heures)

## Partie 1 : Les Conditions

### 4. Conditions imbriquées

---

## 1. Définition des conditions imbriquées

Les **conditions imbriquées** consistent à placer une structure conditionnelle `if` ou `if-else` à l’intérieur d’un autre bloc conditionnel.

Cela permet de réaliser des tests plus complexes et hiérarchisés, où certains tests dépendent du résultat d’autres tests.

---

## 2. Syntaxe générale

```c
if (condition1) {
    // bloc si condition1 vraie
    if (condition2) {
        // bloc si condition2 vraie et condition1 vraie
    } else {
        // bloc si condition2 fausse et condition1 vraie
    }
} else {
    // bloc si condition1 fausse
}
```

---

## 3. Exemple illustratif

Considérons l’exemple d’une validation simple d’âge et de statut étudiant.

```c
#include <stdio.h>

int main() {
    int age;
    char statut;

    printf("Entrez l'âge : ");
    scanf("%d", &age);
    printf("Entrez le statut (E pour étudiant, A pour autre) : ");
    scanf(" %c", &statut);

    if (age >= 18) {
        if (statut == 'E' || statut == 'e') {
            printf("Adulte étudiant\n");
        } else {
            printf("Adulte non étudiant\n");
        }
    } else {
        printf("Mineur\n");
    }

    return 0;
}
```

- L’entrée est d’abord testée sur l’âge.
- Si majeur, une condition imbriquée teste le statut.
- Sinon, le programme conclut immédiatement que la personne est mineure.

---

## 4. Diagramme Mermaid : conditions imbriquées

```mermaid
flowchart TD
    A[Démarrage] --> B[age >= 18 ?]
    B -->|Oui| C[statut == 'E' ou 'e'?]
    B -->|Non| F[Affiche "Mineur"]
    C -->|Oui| D[Affiche "Adulte étudiant"]
    C -->|Non| E[Affiche "Adulte non étudiant"]
    D --> G[Fin]
    E --> G
    F --> G
```

---

## 5. Avantages et points d’attention

- **Avantages :**
  - Permet d’organiser proprement des tests logiques complexes dépendants.
  - Facilite la structuration en sous-cas clairs et explicites.

- **Points d’attention :**
  - La lecture peut se complexifier avec de nombreuses imbrications.
  - Préférer dans certains cas la composition des conditions avec `&&` et `||` si cela améliore la lisibilité.
  - Toujours utiliser une indentation claire et constante.

---

## 6. Exemple avec conditions combinées (alternative aux imbrications)

La même logique peut être exprimée avec une condition combinée :

```c
if (age >= 18 && (statut == 'E' || statut == 'e')) {
    printf("Adulte étudiant\n");
} else if (age >= 18) {
    printf("Adulte non étudiant\n");
} else {
    printf("Mineur\n");
}
```

---

## 7. Sources utilisées

- cppreference.com - [if statement](https://en.cppreference.com/w/c/language/if)  
- TutorialsPoint - [C Nested if-else](https://www.tutorialspoint.com/cprogramming/c_nested_if_else.htm)  
- GeeksforGeeks - [Nested if in C](https://www.geeksforgeeks.org/nested-if-statement-in-c/)  
- ISO/IEC 9899:2018 (C18 standard) - Chapitre 6.8.4.1  

---

Les conditions imbriquées permettent de créer des choix hiérarchisés dans un programme C, offrant une flexibilité plus fine dans la gestion des cas complexes, tout en requérant une structuration soigneuse pour rester compréhensible.