# Séance 4 : Fonctions et Modularité (4 heures)

## Partie 1 : Introduction aux Fonctions

### 2. Anatomie d'une fonction : type de retour, nom, paramètres, corps

---

## 1. Structure générale d’une fonction en C

Une fonction en langage C est composée de quatre éléments fondamentaux :

1. **Type de retour**
2. **Nom de la fonction**
3. **Liste des paramètres (optionnelle)**
4. **Corps de la fonction**

---

### 1.1 Type de retour

- Indique le type de la valeur que la fonction renvoie à son appelant.
- Peut être un type primitif (`int`, `float`, `char`, etc.), un pointeur, une structure, ou `void` si la fonction ne retourne rien.
- Le type doit correspondre à la valeur retournée avec l'instruction `return`.

```c
int maFonction() {
    return 42;   // retourne un entier
}
```

---

### 1.2 Nom de la fonction

- Identificateur unique utilisé pour appeler la fonction.
- Doit respecter les conventions de nommage en C (lettres, chiffres, underscore, ne pas commencer par un chiffre).
- Le nom doit être explicite pour refléter la tâche de la fonction.

---

### 1.3 Liste des paramètres

- Enveloppe les variables d’entrée que la fonction utilise pour effectuer son traitement.
- Chaque paramètre est déclaré avec son type et son nom.
- Une fonction peut ne pas prendre de paramètres (`void` ou liste vide).
- Les paramètres sont passés par valeur en C (sauf si ce sont des pointeurs).

```c
void afficherMessage(char message[]) {
    printf("%s\n", message);
}
```

---

### 1.4 Corps de la fonction

- Bloc d’instructions entre accolades `{ ... }`.
- Contient les déclarations locales et le code à exécuter.
- Peut contenir des structures de contrôle, appels à d’autres fonctions, etc.
- Doit se terminer par un `return` si le type de retour n’est pas `void`.

---

## 2. Exemple complet d’une fonction en C

```c
#include <stdio.h>

// Fonction qui calcule la somme de deux entiers et renvoie le résultat
int addition(int a, int b) {
    int resultat = a + b;
    return resultat;
}

int main() {
    int x = 5, y = 3;
    int somme = addition(x, y);
    printf("La somme de %d et %d est %d\n", x, y, somme);
    return 0;
}
```

---

## 3. Diagramme Mermaid : Anatomie d'une fonction

```mermaid
flowchart TB
    A[Type de retour] --> B[Nom de la fonction]
    B --> C[Liste des paramètres]
    C --> D[Corps de la fonction]
    D --> E[return (optionnel, selon type)]
```

---

## 4. Points clés

| Élément           | Description                                           | Exemple                       |
|-------------------|-------------------------------------------------------|------------------------------|
| Type de retour    | Type de la valeur retournée, ou `void` si rien rendu | `int`, `void`                |
| Nom de la fonction| Identifiant pour l’appel                              | `addition`, `afficher`        |
| Paramètres       | Variables d’entrée (possiblement vide)                 | `(int a, int b)`, `(void)`   |
| Corps            | Suite d’instructions qui réalise la fonction         | `{ return a + b; }`           |

---

## 5. Sources utilisées

- [cppreference.com - Functions in C](https://en.cppreference.com/w/c/language/functions)  
- [GeeksforGeeks - Anatomy of a Function in C](https://www.geeksforgeeks.org/structures-in-c/)  
- [TutorialsPoint - C Functions](https://www.tutorialspoint.com/cprogramming/c_functions.htm)  
- ISO/IEC 9899:2018 (C18) – Section 6.7

---

Cette décomposition détaillée permet de maîtriser la déclaration et la définition des fonctions en C, en structurant clairement leurs entrées, sorties et logique interne.