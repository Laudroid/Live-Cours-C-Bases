# Séance 1 : Introduction au Langage C et Environnement de Développement (3 heures)

## Partie 3 : Mon Premier Programme C

### 3. Exemple de "Hello, World!"

---

Le programme “Hello, World!” est l’exemple classique et universel pour démarrer en langage C. Il illustre la structure minimale d’un programme fonctionnel et l’usage de la fonction `printf()` pour afficher un texte simple.

---

## 1. Code source complet

```c
#include <stdio.h>  // Inclusion de la bibliothèque standard d'entrée/sortie

int main() {
    printf("Hello, World!\n");  // Affiche la chaîne suivie d'un retour à la ligne
    return 0;                   // Terminaison normale du programme
}
```

---

## 2. Explications

- `#include <stdio.h>`  
  Permet d’accéder à la fonction `printf` pour l’affichage.

- `int main()`  
  Point d’entrée du programme, obligatoire.

- `printf("Hello, World!\n");`  
  Affiche le texte `Hello, World!` sur la console avec un saut de ligne inclus grâce à `\n`.

- `return 0;`  
  Indique que le programme s'est terminé sans erreur.

---

## 3. Compilation et exécution

### Sous Linux / macOS / environnement équipé GCC

```bash
gcc hello.c -o hello   # Compilation
./hello                # Exécution
```

### Sous Windows avec MinGW ou Code::Blocks

- Compiler depuis l’IDE via l’option "Build"
- Exécuter le programme généré

---

## 4. Schéma processus d'exécution du programme

```mermaid
flowchart TD
    A[Fichier source hello.c] --> B[Préprocesseur]
    B --> C[Compilation avec GCC]
    C --> D[Exécutable hello]
    D --> E[Exécution par l'OS]
    E --> F[Affiche "Hello, World!"]
```

---

## 5. Variantes courantes

- Utilisation de la fonction `puts()` :

  ```c
  #include <stdio.h>

  int main() {
      puts("Hello, World!");
      return 0;
  }
  ```

- Variante avec arguments `main` :

  ```c
  int main(int argc, char *argv[]) {
      printf("Hello, World!\n");
      return 0;
  }
  ```

---

## 6. Sources utilisées

- GNU GCC official docs – [https://gcc.gnu.org/onlinedocs/](https://gcc.gnu.org/onlinedocs/)  
- cppreference.com – [main function](https://en.cppreference.com/w/c/program/main)  
- TutorialsPoint – [Hello World in C](https://www.tutorialspoint.com/cprogramming/c_hello_world_program.htm)  
- ISO/IEC 9899:2018 – C Standard

---

Ce programme est un excellent point de départ pour tester son environnement, comprendre la compilation et lancer un premier code en C. Les notions abordées ici se retrouveront dans tous les programmes plus complexes.