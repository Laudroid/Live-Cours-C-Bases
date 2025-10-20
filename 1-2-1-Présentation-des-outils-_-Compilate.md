# Séance 1 : Introduction au Langage C et Environnement de Développement (3 heures)

## Partie 2 : Préparation de l'Environnement de Développement

### 1. Présentation des outils : Compilateur (GCC), Éditeur de texte/IDE (VS Code, Code::Blocks)

---

L’environnement de développement est un ensemble d’outils indispensables pour écrire, compiler, déboguer et exécuter des programmes en langage C. Cette section présente les outils principaux utilisés, notamment le compilateur GCC, ainsi que deux environnements populaires pour coder en C : VS Code et Code::Blocks.

---

### 1. Le compilateur GCC (GNU Compiler Collection)

GCC est un compilateur libre, open-source, standard de facto pour le langage C, mais supporte aussi d’autres langages comme C++, Fortran, etc. Il est développé par la Free Software Foundation.

#### Caractéristiques :

- Compatible avec un grand nombre de plateformes (Linux, Windows, macOS, architectures variées).
- Génère du code machine optimisé et performant.
- Options puissantes pour le diagnostic et l’analyse (avertissements, debug).
- Intégration aisée aux éditeurs et IDE.

#### Installation rapide

- **Linux** : souvent préinstallé ou disponible via le gestionnaire de paquets (`sudo apt install gcc`).
- **Windows** : inclus dans MinGW ou WSL.
- **macOS** : via Xcode Command Line Tools (`xcode-select --install`).

#### Commande basique de compilation

```bash
gcc programme.c -o programme
./programme
```

> Exemple : un fichier `hello.c` compilé avec GCC
```c
#include <stdio.h>

int main() {
    printf("Bonjour, GCC!\n");
    return 0;
}
```
Compilation et exécution :
```bash
gcc hello.c -o hello
./hello
```

---

### 2. Éditeurs de texte et IDE

#### a) Visual Studio Code (VS Code)

- **Type** : Éditeur de texte léger avec extensions (gratuit, open-source).
- **Fonctionnalités clés** :
  - Support multi-langages, dont C/C++ via extension officielle Microsoft.
  - Intégration de débogueur, gestionnaire de tâches (build), terminal intégré.
  - Intellisense : autocomplétion et suggestions.
  - Interface moderne et personnalisable.

- **Installation de l’extension C/C++** :
  Dans le Marketplace de VS Code, installer l’extension “C/C++” par Microsoft.

- **Compilation intégrée avec tasks.json** :
  Permet d'automatiser la compilation en un clic.

Exemple d’un fichier `tasks.json` pour GCC sous VS Code :

```json
{
    "version": "2.0.0",
    "tasks": [{
        "type": "shell",
        "label": "compiler C",
        "command": "gcc",
        "args": ["-g", "${file}", "-o", "${fileBasenameNoExtension}"],
        "group": "build"
    }]
}
```

---

#### b) Code::Blocks

- **Type** : Environnement de développement intégré (IDE) open-source, spécifique pour C/C++.
- **Caractéristiques** :
  - Interface complète avec gestionnaire de projets, éditeur, compilateur intégré.
  - Débogueur intégré avec interface graphique.
  - Support multi-plateforme (Windows, Linux, macOS).
  - Configuration simplifiée pour GCC.

- **Utilisation** :
  Création de projets C faciles, compilation et débogage via menus graphiques.

---

### Diagramme Mermaid : Interaction entre outils dans un environnement C

```mermaid
graph LR
    A[Éditeur / IDE] -->|Édition| B[Fichiers Source (.c/.h)]
    B -->|Compilation| C[GCC]
    C -->|Exécutable| D[Machine / Système]
    A -->|Débogage| E[Debuggeur (gdb intégré)]
```

---

### Résumé des outils

| Outil           | Type            | Points forts                        | Usage typique                       |
|-----------------|-----------------|-----------------------------------|-----------------------------------|
| **GCC**         | Compilateur     | Performance, portabilité          | Compilation rapide en ligne de commande |
| **VS Code**     | Éditeur léger   | Très personnalisable, extensions  | Programmeurs préférant flexibilité |
| **Code::Blocks**| IDE complet     | Intégration, facilité d’utilisation| Développement structuré projets C |

---

### Sources utilisées

- GNU GCC official website - [https://gcc.gnu.org/](https://gcc.gnu.org/)  
- Visual Studio Code - [https://code.visualstudio.com/docs/languages/cpp](https://code.visualstudio.com/docs/languages/cpp)  
- Code::Blocks - [http://www.codeblocks.org/](http://www.codeblocks.org/)  
- TutsMake - [How to compile C program using GCC](https://www.tutsmake.com/gcc-compile-c-program-on-windows-linux-mac/)  
- Microsoft Docs - [VS Code C++ Tutorial](https://code.visualstudio.com/docs/cpp/config-mingw)  

---

Cette présentation fixe les fondations matérielles pour coder efficacement en C à travers des outils modernes polyvalents et accessibles.