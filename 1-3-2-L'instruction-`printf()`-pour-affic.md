# Séance 1 : Introduction au Langage C et Environnement de Développement (3 heures)

## Partie 3 : Mon Premier Programme C

### 2. L'instruction `printf()` pour afficher du texte

---

L’une des fonctions les plus utilisées en langage C pour afficher du texte sur la console est la fonction `printf()`. Elle appartient à la bibliothèque standard d’entrée/sortie (`<stdio.h>`) et permet d’afficher des chaînes de caractères, des variables et des données formatées.

---

## 1. Présentation de `printf()`

- Prototype dans `<stdio.h>` :

  ```c
  int printf(const char *format, ...);
  ```

- Fonction variadique, elle accepte une chaîne de format suivie d’un nombre variable d’arguments.
- La chaîne de format peut contenir du texte fixe et des **spécificateurs de format** indiquant comment afficher les arguments.

---

## 2. Usage basique

```c
#include <stdio.h>

int main() {
    printf("Bonjour le monde !\n");
    return 0;
}
```

- `"Bonjour le monde !\n"` est une chaîne littérale affichée telle quelle.
- Le caractère spécial `\n` insère un saut de ligne (nouvelle ligne).

---

## 3. Spécificateurs de format courants

| Spécificateur | Type attendu  | Description                         | Exemple                       |
|---------------|--------------|----------------------------------|------------------------------|
| `%d`          | entier (int) | Affiche un entier en base décimale | `printf("Nombre: %d", 42);`  |
| `%c`          | caractère    | Affiche un caractère              | `printf("Lettre: %c", 'A');` |
| `%f`          | flottant     | Affiche un nombre flottant       | `printf("Valeur: %f", 3.14);`|
| `%s`          | chaîne       | Affiche une chaîne de caractères | `printf("Nom: %s", "Jean");` |
| `%x`          | entier       | Affiche en hexadécimal           | `printf("Hexa: %x", 255);`   |

---

## 4. Exemple d’utilisation avec variables

```c
#include <stdio.h>

int main() {
    int age = 30;
    char lettre = 'C';
    float pi = 3.1416;
    
    printf("Age: %d\n", age);
    printf("Lettre: %c\n", lettre);
    printf("Pi approx: %.2f\n", pi);  // 2 décimales
    return 0;
}
```

---

## 5. Contrôle du format : précision et largeur

- On peut limiter le nombre de chiffres après la virgule avec `.2` (ici deux décimales) :  
  ```c
  printf("%.2f", 3.14159);  // Affiche 3.14
  ```

- On peut fixer une largeur minimum pour l’affichage (exemple 5 caractères) :  
  ```c
  printf("%5d", 42);  // Affiche "   42" avec espaces devant
  ```

---

## 6. Diagramme Mermaid : Fonctionnement de `printf()`

```mermaid
flowchart TD
    A[Appel de printf()] --> B[Analyse de la chaîne de format]
    B --> C[Affichage du texte fixe]
    B --> D[Détection des spécificateurs]
    D --> E[Récupération des arguments]
    E --> F[Conversion selon le spécificateur]
    F --> G[Affichage avec formatage]
```

---

## 7. Retour de `printf()`

- La fonction retourne un entier représentant le nombre de caractères affichés.
- En cas d’erreur, elle retourne un nombre négatif.

---

## Sources utilisées

- GNU C Library Documentation - [printf](https://www.gnu.org/software/libc/manual/html_node/Formatted-Output-Functions.html)  
- cppreference.com - [printf](https://en.cppreference.com/w/c/io/fprintf)  
- TutorialsPoint - [C - printf() Function](https://www.tutorialspoint.com/c_standard_library/c_function_printf.htm)  
- ISO/IEC 9899:2018 (C18) - Sections sur `<stdio.h>` fonctions d'entrée/sortie  

---

La fonction `printf()` est un outil puissant pour le débogage et l’interaction utilisateur en C, car elle permet d’afficher à la fois du texte statique et des données dynamiques selon un format précis et contrôlé.