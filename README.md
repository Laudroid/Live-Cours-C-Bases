# Cours Langage C bases

## Objectifs de la formation

- Comprendre les concepts fondamentaux de la programmation en C.
- Être capable d'écrire, compiler et exécuter des programmes C simples.
- Maîtriser les types de données, les opérateurs, les structures de contrôle et les fonctions de base.
- Acquérir les bonnes pratiques de codage.
## Séance 1 : Introduction au Langage C et Environnement de Développement

### Objectifs pédagogiques

- Comprendre l'histoire et l'importance du langage C.
- Installer un environnement de développement C.
- Écrire, compiler et exécuter son premier programme C.
- Découvrir la structure minimale d'un programme C.
### Contenus

#### Historique et Importance du C

- Brève histoire du C (Bell Labs, Unix).
- Pourquoi le C est-il encore pertinent aujourd'hui ? (Systèmes d'exploitation, embarqué, performance).
- Les versions du standard C (C99, C11, C18, C23 - mentionner les nouveautés clés de C23 comme `bool`, `const`).
#### Préparation de l'Environnement de Développement

- Présentation des outils : Compilateur (GCC), Éditeur de texte/IDE (VS Code, Code::Blocks).
- Étapes d'installation de GCC et d'un IDE (ex: Code::Blocks).
- Configuration de l'IDE pour la compilation C.
#### Mon Premier Programme C

- Structure d'un programme C : `#include`, `main`, `return 0`.
- L'instruction `printf()` pour afficher du texte.
- Exemple de "Hello, World!".
- Compilation (`gcc nom_du_fichier.c -o nom_executable`) et exécution (`./nom_executable`).
#### Commentaires et Bonnes Pratiques

- L'importance des commentaires (`//` et `/* */`).
- Conventions de nommage simples.
- Lisibilité du code.
## Séance 2 : Les Fondamentaux du C

### Objectifs pédagogiques

- Comprendre les différents types de données en C.
- Déclarer et initialiser des variables.
- Utiliser les opérateurs arithmétiques, relationnels et logiques.
- Interagir avec l'utilisateur via `scanf()`.
### Contenus

#### Variables et Types de Données

- Qu'est-ce qu'une variable ? Déclaration, initialisation.
- Types entiers : `int`, `short`, `long`, `long long`, `unsigned`.
- Types flottants : `float`, `double`.
- Type caractère : `char`.
- Le type booléen en C23 (`_Bool` ou `bool` avec ``).
- Tailles et plages de valeurs.
#### Opérateurs en C

- Opérateurs arithmétiques : `+`, `-`, `*`, `/`, `%`.
- Opérateurs d'affectation : `=`, `+=`, `-=`, `*=`, `/=`, `%=`.
- Opérateurs d'incrémentation/décrémentation : `++`, `--`.
- Opérateurs relationnels : `==`, `!=`, ``, `=`.
- Opérateurs logiques : `&&` (ET), `||` (OU), `!` (NON).
- Priorité et associativité des opérateurs.
#### Entrées et Sorties Standard

- `printf()` : formatage de sortie (`%d`, `%f`, `%c`, `%s`).
- `scanf()` : lecture d'entrée utilisateur (`%d`, `%f`, `%c`, attention à `&`).
- Gestion des retours de `scanf()`.
#### Les Constantes

- Constantes littérales.
- Constantes symboliques avec `#define`.
- Constantes avec `const` (variables en lecture seule).
## Séance 3 : Structures de Contrôle

### Objectifs pédagogiques

- Maitriser les conditions (`if`, `else if`, `else`).
- Utiliser les boucles (`for`, `while`, `do-while`) pour répéter des actions.
- Comprendre l'utilité de `break` et `continue`.
### Contenus

#### Les Conditions

- L'instruction `if` : exécution conditionnelle.
- `if-else` : choix entre deux alternatives.
- `if-else if-else` : choix multiples.
- Conditions imbriquées.
- L'opérateur ternaire `? :`.
#### Les Boucles

- La boucle `for` : idéale pour un nombre connu d'itérations.
- La boucle `while` : répétition tant qu'une condition est vraie.
- La boucle `do-while` : exécution au moins une fois.
- Boucles infinies et comment les éviter.
#### Instructions de Saut

- `break` : sortir d'une boucle ou d'un `switch`.
- `continue` : passer à l'itération suivante d'une boucle.
- L'instruction `goto` (déconseillée, à éviter sauf cas très spécifiques).
#### Exercices Guidés de Structures de Contrôle

- Exemples d'utilisation combinée des conditions et boucles.
- Pseudo-code pour résoudre des problèmes simples.
## Séance 4 : Fonctions et Modularité

### Objectifs pédagogiques

- Comprendre le concept de fonction et son utilité pour la modularité.
- Déclarer, définir et appeler des fonctions.
- Passer des arguments par valeur et gérer les valeurs de retour.
- Utiliser des fonctions de bibliothèques standards.
### Contenus

#### Introduction aux Fonctions

- Pourquoi utiliser des fonctions ? (Réutilisabilité, modularité, lisibilité).
- Anatomie d'une fonction : type de retour, nom, paramètres, corps.
- Déclaration (prototype) et définition de fonction.
#### Passage d'Arguments et Valeurs de Retour

- Passage d'arguments par valeur (copie des données).
- L'instruction `return` et son rôle.
- Fonctions sans paramètres et/ou sans valeur de retour (`void`).
#### Fonctions de Bibliothèques Standards

- Présentation de quelques bibliothèques : `stdio.h` (déjà vu), `stdlib.h` (fonctions générales, `exit()`, `rand()`), `math.h` (`sqrt()`, `pow()`, `sin()`).
- Inclusion de bibliothèques avec `#include`.
#### Conception de Fonctions Simples

- Exemples de fonctions pour effectuer des tâches spécifiques (calculer un carré, afficher un message personnalisé).
- Décomposer un problème en sous-problèmes gérables par des fonctions.