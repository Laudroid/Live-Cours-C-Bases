Bonjour à toutes et à tous,

Ce TP est conçu pour renforcer votre compréhension des fonctions en langage C, un concept fondamental pour écrire du code structuré et maintenable.

---

### **TP : Maîtrise des Fonctions en C - Un Calculateur Modulaire**

**Contexte**
Les fonctions sont le mécanisme central en C pour organiser votre code. Elles permettent de découper un programme en blocs logiques, chacun dédié à une tâche spécifique. Cette approche améliore la clarté, facilite le débogage et rend le code plus réutilisable.

**Objectif du TP**
Répondre aux questions d'un QCM sur les fonctions et appliquer ces concepts dans un mini-projet de développement.

---

**Énoncé du QCM**

1.  **Quel est le rôle principal d'une fonction en C ?**
    *   (a) Afficher du texte
    *   (b) Regrouper des instructions pour une tâche spécifique
    *   (c) Déclarer des variables

2.  **Si une fonction ne renvoie aucune valeur, quel type de retour doit-elle avoir ?**
    *   (a) `int`
    *   (b) `char`
    *   (c) `void`

3.  **Le prototype d'une fonction est :**
    *   (a) La définition complète de la fonction
    *   (b) Sa déclaration avant son utilisation
    *   (c) L'appel de la fonction

---

**Mini-Projet : Calculateur de Moyenne Simple**

Pour mettre en pratique les concepts du QCM, vous allez développer un petit programme en C. Ce programme calculera la moyenne de trois nombres entiers saisis par l'utilisateur. L'objectif est de structurer ce programme de manière modulaire en utilisant plusieurs fonctions.

**Fonctionnalités attendues**

Votre programme devra :
1.  Afficher un message de bienvenue ou une instruction claire pour l'utilisateur.
2.  Demander à l'utilisateur de saisir trois nombres entiers, un par un.
3.  Calculer la somme de ces trois nombres.
4.  Calculer la moyenne de ces trois nombres.
5.  Afficher le résultat de la moyenne avec une précision d'une décimale.

**Consignes de Réalisation**

Pour ce mini-projet, vous devrez impérativement structurer votre code en utilisant les fonctions suivantes (ou des fonctions ayant des rôles similaires) :

*   `void afficherBienvenue();`
    *   **Rôle :** Afficher un message de bienvenue ou une instruction.
    *   **Type de retour :** `void` (elle ne renvoie aucune valeur).

*   `int saisirNombre(int ordre);`
    *   **Rôle :** Demander à l'utilisateur de saisir un nombre entier et le retourner. Le paramètre `ordre` pourra être utilisé pour personnaliser le message (ex: "Saisissez le 1er nombre : ", "Saisissez le 2ème nombre : ").
    *   **Type de retour :** `int` (elle renvoie le nombre saisi).

*   `int calculerSomme(int n1, int n2, int n3);`
    *   **Rôle :** Calculer la somme des trois nombres passés en paramètres.
    *   **Type de retour :** `int` (elle renvoie la somme).

*   `float calculerMoyenne(int somme, int nombreDeValeurs);`
    *   **Rôle :** Calculer la moyenne à partir de la somme et du nombre de valeurs. Soyez attentif aux types pour obtenir une moyenne flottante.
    *   **Type de retour :** `float` (elle renvoie la moyenne).

*   `void afficherResultat(float moyenne);`
    *   **Rôle :** Afficher la moyenne calculée de manière conviviale.
    *   **Type de retour :** `void` (elle ne renvoie aucune valeur).

**Structure du code**

*   **Prototypes :** Déclarez les prototypes de toutes vos fonctions au début de votre fichier `.c`, avant la fonction `main`.
*   **Définitions :** Placez les définitions complètes de vos fonctions *après* la fonction `main`.

**Conseils et utilisation des outils d'IA**

*   **Découpage :** Abordez le projet par petites étapes. Commencez par `main` et `afficherBienvenue`, puis ajoutez `saisirNombre`, et ainsi de suite. Testez chaque fonction au fur et à mesure de son implémentation.
*   **Prototypes :** Rappelez-vous que les prototypes sont des déclarations qui informent le compilateur de l'existence, du nom, des paramètres et du type de retour d'une fonction, avant même qu'il ne voie sa définition complète.
*   **Utilisation de l'IA :** Les outils d'intelligence artificielle peuvent être des assistants très utiles. N'hésitez pas à les solliciter pour :
    *   Obtenir des explications claires sur un concept que vous ne maîtrisez pas (ex: "Explique-moi la différence entre déclaration et définition de fonction en C").
    *   Vous aider à débugger une erreur spécifique ("Pourquoi mon programme plante-t-il à cette ligne ?").
    *   Explorer des manières alternatives de résoudre un problème ("Comment pourrais-je rendre ma fonction `saisirNombre` plus robuste face à des entrées non numériques ?").
    *   Générer des ébauches de code pour certaines fonctions.

    L'objectif principal est que vous compreniez le code que vous produisez. Si vous utilisez l'IA, soyez critique : analysez ses propositions, et assurez-vous de pouvoir expliquer *votre* solution et de justifier chaque choix de conception. L'IA est un outil pour augmenter votre compréhension, pas pour la remplacer.

**Validation**

Votre solution sera considérée comme valide si :
*   Le QCM est correctement répondu.
*   Le programme compile sans erreur ni avertissement.
*   Le programme exécute correctement toutes les fonctionnalités demandées.
*   Le code est structuré en fonctions comme spécifié, avec des prototypes corrects.
*   Le code est lisible et bien organisé.

Bon courage !