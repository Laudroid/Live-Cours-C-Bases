# Séance 2 : Les Fondamentaux du C (4 heures)

## Partie 3 : Entrées et Sorties Standard

### 2. `scanf()` : lecture d'entrée utilisateur (`%d`, `%f`, `%c`, attention à `&`)

---

## 1. Présentation de `scanf()`

La fonction `scanf()` permet d’effectuer la lecture formatée depuis l’entrée standard (généralement le clavier). Elle est définie dans la bibliothèque `<stdio.h>` et sert à récupérer des données saisies par l’utilisateur, typées et converties selon des spécificateurs.

Prototype simplifié :

```c
int scanf(const char *format, ...);
```

- `format` : chaîne de format, similaire à `printf()` mais avec des spécificateurs adaptés à la lecture.
- `...` : adresses des variables dans lesquelles stocker les valeurs lues.

---

## 2. Spécificateurs courants et syntaxe

| Spécificateur | Type attendu                  | Exemples              |
|---------------|------------------------------|-----------------------|
| `%d`          | Entier (`int`)                | `scanf("%d", &age);`  |
| `%f`          | Nombre à virgule flottante (`float`) | `scanf("%f", &taille);` |
| `%c`          | Caractère (`char`)            | `scanf(" %c", &lettre);` (Note l'espace avant `%c`) |
| `%s`          | Chaîne de caractères (`char[]`) | `scanf("%s", nom);` (sans & car tableau) |

Note : `%s` lit une chaîne jusqu’au premier espace, caractère de tabulation ou saut de ligne.

---

## 3. Importance de l’opérateur `&` (adresse)

`scanf()` nécessite l'adresse des variables pour pouvoir modifier leur contenu. C’est pourquoi pour les types simples on utilise `&var`.

Exception relevante :  
- Pour un tableau de caractères (`char nom[20];`) on passe simplement `nom` sans `&` (car le nom du tableau est par nature une adresse).

---

## 4. Exemples pratiques

```c
#include <stdio.h>

int main() {
    int age;
    float taille;
    char initiale;
    char nom[30];

    printf("Entrez votre âge : ");
    scanf("%d", &age);

    printf("Entrez votre taille en mètres : ");
    scanf("%f", &taille);

    printf("Entrez la première lettre de votre prénom : ");
    scanf(" %c", &initiale); // espace avant %c pour ignorer les caractères blancs

    printf("Entrez votre nom : ");
    scanf("%s", nom);

    printf("\nRésumé :\n");
    printf("Nom : %s\n", nom);
    printf("Initiale : %c\n", initiale);
    printf("Âge : %d\n", age);
    printf("Taille : %.2f m\n", taille);

    return 0;
}
```

---

## 5. Particularités et pièges fréquents

- **L'espace blanc avant `%c`**  
  Lorsque l'on lit un caractère avec `%c`, il faut souvent ajouter un espace avant pour consommer les caractères blancs (retours à la ligne ou espaces résiduels).

- **Ne pas oublier `&`** pour les variables scalaires sauf pour les chaînes (tableaux de caractères).

- **Attention au format de lecture**  
  Une mauvaise correspondance entre le format de `scanf` et le type des variables peut produire des lectures erronées ou des comportements indéfinis.

- **Gestion des retours à la ligne et buffer**  
  Le buffer d'entrée n'est pas toujours vidé ce qui peut impacter la lecture suivante.

---

## 6. Diagramme Mermaid : processus d’utilisation de `scanf()`

```mermaid
flowchart TD
    A[Appel de scanf()] --> B[Analyse de la chaîne de format]
    B --> C[Lire l'entrée standard]
    C --> D{Correspondance entre input et format ?}
    D -->|Oui| E[Stockage dans variable via adresse]
    D -->|Non| F[Erreur ou lecture incorrecte]
    E --> G[Recommencer pour chaque spécificateur]
    G --> H[Retour nombre d'éléments lus avec succès]
```

---

## 7. Résumé

- `scanf()` lit des données depuis l'entrée standard en les interprétant selon des formats précis.
- Utiliser toujours `&` pour passer l'adresse des variables scalaires.
- Ajouter une espace avant `%c` pour ignorer les caractères blancs.
- Vérifier que les types des variables correspondent aux spécificateurs utilisés.
- Penser à la gestion de l’entrée en cas d’erreur ou de dépassement.

---

## 8. Sources utilisées

- cppreference.com - [`scanf`](https://en.cppreference.com/w/c/io/fscanf)  
- ISO/IEC 9899:2018 (C18 Standard) - Chapitre 7.21.6.2  
- TutorialsPoint - [C - scanf() Function](https://www.tutorialspoint.com/c_standard_library/c_function_scanf.htm)  
- GNU GCC Documentation - [Input/output](https://gcc.gnu.org/onlinedocs/gcc/Invocation.html#input-output)  

---

La fonction `scanf()` est un outil direct et simple pour collecter des données utilisateurs avec typage précis. Maîtriser ses subtilités garantit une entrée correcte et évite des bugs liés à la lecture.