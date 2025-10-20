# Séance 1 : Introduction au Langage C et Environnement de Développement (3 heures)

## Partie 2 : Préparation de l'Environnement de Développement

### 3. Configuration de l'IDE pour la compilation C

---

Configurer un IDE (Integrated Development Environment) pour compiler et exécuter des programmes en C demande quelques réglages afin d’assurer la bonne interaction entre le code source, le compilateur et le débogueur. Ce cours explique comment configurer les IDE populaires, notamment **Code::Blocks** et **Visual Studio Code**, pour compiler du code C avec GCC.

---

## 1. Configuration de Code::Blocks pour la compilation C

### Installation préalable

- Code::Blocks installé avec MinGW (GCC) intégré (voir étape d’installation).
  
### Étapes pour vérifier et configurer le compilateur GCC

1. **Accéder aux paramètres du compilateur**  
   Menu : `Settings` > `Compiler...`

2. **Vérifier le compilateur sélectionné**  
   Dans la liste déroulante, sélectionnez « GNU GCC Compiler ».

3. **Vérifier le chemin vers le compilateur**  
   Allez dans l’onglet « Toolchain executables », repérez les chemins  
   - Le chemin doit pointer vers le dossier où `gcc.exe`, `g++.exe`, `gdb.exe` sont présents.  
   - Exemple pour MinGW : `C:\Program Files (x86)\CodeBlocks\MinGW\bin`

4. **Tester la configuration**  
   Créez un nouveau projet Console en C (`File` > `New` > `Project` > `Console application` > `C`), écrivez un code simple (ex : `printf("Hello world\n");`). Compilez avec `Build` puis exécutez.  
   - Si le programme compile et s’exécute sans erreur, la configuration est correcte.

---

## 2. Configuration de Visual Studio Code (VS Code) pour compiler du C avec GCC

### Prérequis

- Avoir GCC installé (MinGW sur Windows, GCC sous Linux/macOS).
- Installer VS Code.
- Installer l’extension officielle Microsoft C/C++.

### Configuration pas à pas

1. **Installer l’extension C/C++**  
   Ouvrez le Marketplace (`Ctrl+Shift+X`), recherchez « C/C++ » et installez l’extension de Microsoft.

2. **Configurer la tâche de compilation (tasks.json)**  
   Dans VS Code, créez un fichier `tasks.json` dans le dossier `.vscode` du projet (via `Terminal` > `Configure Default Build Task`).

   Exemple minimal `tasks.json` pour compiler un fichier `main.c` :

   ```json
   {
       "version": "2.0.0",
       "tasks": [
           {
               "label": "Build C program",
               "type": "shell",
               "command": "gcc",
               "args": [
                   "-g",
                   "main.c",
                   "-o",
                   "main"
               ],
               "group": {
                   "kind": "build",
                   "isDefault": true
               },
               "problemMatcher": ["$gcc"]
           }
       ]
   }
   ```

3. **Task de débogage (launch.json)**  
   Ajoutez aussi un fichier `launch.json` pour le débogage :

   ```json
   {
       "version": "0.2.0",
       "configurations": [
           {
               "name": "Debug C program",
               "type": "cppdbg",
               "request": "launch",
               "program": "${workspaceFolder}/main",
               "args": [],
               "stopAtEntry": false,
               "cwd": "${workspaceFolder}",
               "environment": [],
               "externalConsole": false,
               "MIMode": "gdb",
               "setupCommands": [
                   {
                       "description": "Enable pretty-printing for gdb",
                       "text": "-enable-pretty-printing",
                       "ignoreFailures": true
                   }
               ]
           }
       ]
   }
   ```

4. **Compiler et exécuter**  
   - `Ctrl+Shift+B` lance la compilation via la tâche configurée.  
   - F5 démarre la session débogage.

---

## 3. Exemple : Compilation et exécution dans VS Code

Code C (`main.c`) : 

```c
#include <stdio.h>

int main() {
    printf("Hello from VS Code!\n");
    return 0;
}
```

Compilation :

```bash
gcc -g main.c -o main
```

Exécution :

```bash
./main
```

---

## Diagramme Mermaid : Schéma du processus de compilation dans un IDE

```mermaid
graph LR
    A[Éditeur de code] -- Sauvegarde --> B[Fichiers source C]
    B -- Lancement compilation --> C[Compilateur GCC]
    C -- Génère --> D[Exécutable]
    D -- Exécution --> E[Programme en mémoire]
    E -- Débogage possible --> A
```

---

## Sources utilisées

- Code::Blocks Wiki - [Compilers setup](http://wiki.codeblocks.org/index.php?title=Compilers_setup)  
- Visual Studio Code Docs - [C/C++ development](https://code.visualstudio.com/docs/languages/cpp)  
- Microsoft Docs - [Debugging configurations](https://code.visualstudio.com/docs/cpp/config-mingw)  
- GCC Documentation - [Building and using GCC](https://gcc.gnu.org/onlinedocs/)  

---

La configuration précise du compilateur dans l’IDE garantit un cycle de développement fluide : de l’écriture à la compilation puis à l’exécution et au débogage. Ces étapes sont la clé pour exploiter pleinement le potentiel des outils de développement C modernes.