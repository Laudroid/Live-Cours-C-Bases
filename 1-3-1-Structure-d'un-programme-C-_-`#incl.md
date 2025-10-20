# Séance 1 : Introduction au Langage C et Environnement de Développement (3 heures)

## Partie 3 : Mon Premier Programme C

### 1. Structure d'un programme C : `#include`, `main`, `return 0`

---

Le langage C, malgré sa simplicité apparente, repose sur une structure claire et codifiée qui permet d'écrire des programmes efficaces et compréhensibles. Cette section décrit les éléments fondamentaux qu’un programme C doit contenir pour être correct et fonctionnel.

---

## 1. Directive `#include`

- La directive `#include` permet d’inclure des fichiers d’en-tête (headers) contenant des définitions et des déclarations de fonctions, macros, types, essentielles au programme.
- La forme classique :

  ```c
  #include <nom_du_fichier.h>
  ```

- Par exemple, pour utiliser la fonction `printf` (qui affiche du texte à l’écran), on inclut la bibliothèque standard d’entrée/sortie :

  ```c
  #include <stdio.h>
  ```

- Ce mécanisme permet au compilateur de connaître les signatures des fonctions utilisées.

---

## 2. Fonction `main`

- La fonction `main` est le point d’entrée obligatoire de tout programme C.
- Sa syntaxe minimale est :

  ```c
  int main(void) {
      // corps du programme
  }
  ```

- Elle doit toujours retourner un entier (`int`), qui est le code de sortie du programme.
- La forme la plus utilisée est :

  ```c
  int main() {
      // instructions
      return 0;
  }
  ```
  
- Le `return 0;` signale au système d’exploitation que le programme s’est terminé correctement.

---

## 3. Exemple complet simple

```c
#include <stdio.h>     // Inclusion de la bibliothèque standard d'entrée/sortie

int main() {
    printf("Bonjour le monde !\n");  // Affiche "Bonjour le monde !" suivi d'un retour à la ligne
    return 0;                        // Fin normale du programme
}
```

Ce programme affiche le texte "Bonjour le monde !" à l’écran.

---

## 4. Déroulement du programme

1. Le préprocesseur traite la directive `#include` et insère le contenu du fichier `stdio.h`.
2. Le compilateur transforme le code en langage machine.
3. Lorsque le programme s’exécute, la fonction `main` est appelée automatiquement.
4. La fonction `printf` est exécutée : le message est affiché.
5. Le programme retourne 0 et se termine.

---

## 5. Diagramme Mermaid : Structure d’un programme C

```mermaid
graph TD
    A[#include <stdio.h>] --> B[Déclaration de fonctions / macros]
    C[int main()] --> D[Instructions du programme]
    D --> E[return 0;]
    A --> F[Préprocesseur]
    F --> G[Compilateur]
    G --> H[Exécution]
```

---

## 6. Compléments

- La fonction `main` peut également recevoir des arguments `argc` et `argv` permettant de gérer les paramètres passés en ligne de commande :

  ```c
  int main(int argc, char *argv[]) {
      // argc : nombre d'arguments
      // argv : tableau des arguments
      return 0;
  }
  ```

- Le `return 0;` est conventionnel, mais si omis (en C99 et suivants), la fonction `main` retourne implicitement 0.

---

## Sources utilisées

- ISO/IEC 9899:2018 – Programming Languages – C (C18 standard)  
- [cppreference.com - main function](https://en.cppreference.com/w/c/program/main)  
- [TutorialsPoint - Structure of C program](https://www.tutorialspoint.com/cprogramming/c_basic_syntax.htm)  
- GNU GCC documentation - [Standard C Library](https://gcc.gnu.org/onlinedocs/libstdc++/manual/)  

---

Cette base simple permet d’écrire un programme fonctionnel, structurellement conforme aux spécifications du langage C. La maîtrise de cette structure est la première étape avant d’aborder les notions plus complexes telles que les variables, les conditions, ou les boucles.