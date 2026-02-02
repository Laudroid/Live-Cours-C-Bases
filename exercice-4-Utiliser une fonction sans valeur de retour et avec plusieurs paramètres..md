Bonjour à toutes et à tous !

Nous allons aborder un concept fondamental en C : les fonctions. Plus précisément, nous allons nous concenter sur celles qui ne renvoient pas de valeur et qui acceptent plusieurs informations en entrée. C'est une étape clé pour écrire du code modulaire et réutilisable.

---

## TP : Salutations Personnalisées – Fonctions sans retour et paramètres multiples

### Objectif du TP

Maîtriser l'utilisation de fonctions qui ne renvoient pas de valeur (`void`) et qui acceptent plusieurs paramètres. C'est une brique essentielle pour structurer vos programmes et les rendre plus lisibles et maintenables.

### Contexte / Scénario

Imaginez que vous développez un petit module pour un système de gestion d'utilisateurs. Ce module a pour unique but de saluer les personnes de manière personnalisée. Pour l'instant, nous nous concentrons sur l'affichage simple d'un message de bienvenue, en utilisant les informations de base de l'utilisateur : son nom et son âge. Ce mini-projet, bien que simple, pose les bases de la modularité et de la réutilisation de code.

### Énoncé du TP / Tâches à réaliser

1.  **Déclarez et définissez une fonction nommée `afficherBonjour`.**
    *   Cette fonction ne doit pas retourner de valeur (utilisez le mot-clé `void`).
    *   Elle doit accepter deux paramètres :
        *   Un nom, qui sera une chaîne de caractères (pour ce TP, utilisez `char nom[]`).
        *   Un âge, qui sera un entier (`int age`).
    *   À l'intérieur de `afficherBonjour`, affichez le message suivant sur la console, en remplaçant `[Nom]` et `[âge]` par les valeurs passées en paramètres :
        `Bonjour [Nom], vous avez [âge] ans !`

2.  **Dans la fonction `main` :**
    *   Déclarez quelques variables pour stocker un nom et un âge (par exemple, `char monNom[] = "Alice"; int monAge = 30;`).
    *   Appelez la fonction `afficherBonjour` en lui passant ces variables.
    *   N'hésitez pas à faire plusieurs appels avec des noms et âges différents pour tester votre fonction.

### Conseils et Pistes

*   **Utilisation de l'IA :** N'hésitez pas à solliciter un assistant IA pour vous aider sur la syntaxe spécifique du C, notamment pour la déclaration de fonctions, l'utilisation de `printf` avec des chaînes de caractères (`%s`) et des entiers (`%d`). C'est un outil puissant pour accélérer votre apprentissage.
*   **Compréhension avant Copier/Coller :** L'objectif n'est pas de copier-coller sans comprendre. Demandez à l'IA d'expliquer chaque ligne de code qu'elle génère. Posez des questions comme : "Pourquoi `void` ?", "Comment fonctionne `char nom[]` ?", "Quel est le rôle de `%s` dans `printf` ?".
*   **Testez et Expérimentez :** Une fois que vous avez une solution, modifiez-la. Changez les messages, ajoutez un troisième paramètre (par exemple, une ville), voyez ce qui se passe. C'est en expérimentant que l'on apprend le mieux.
*   **Structure du code :** Pensez à inclure l'en-tête `<stdio.h>` pour pouvoir utiliser la fonction `printf`.

### Exemple de Résultat Attendu

Si vous appelez votre fonction plusieurs fois, vous devriez obtenir un affichage similaire à ceci :

```
Bonjour Alice, vous avez 30 ans !
Bonjour Bob, vous avez 25 ans !
Bonjour Carol, vous avez 42 ans !
```

Bon courage pour ce TP ! C'est en pratiquant que l'on maîtrise le mieux les bases.