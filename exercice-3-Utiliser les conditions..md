Salut à toutes et à tous !

Aujourd'hui, on se penche sur un concept fondamental en programmation : les **conditions**. C'est grâce à elles que nos programmes peuvent prendre des décisions et s'adapter aux différentes situations. Pour illustrer ça, nous allons construire un petit utilitaire simple mais très parlant.

---

## TP : L'Analyseur de Nombre Simple - Maîtrise des Conditions

### Objectif du TP

Mettre en pratique l'utilisation des structures conditionnelles (`if`, `else if`, `else`) pour permettre à un programme C de prendre des décisions basées sur la valeur d'une variable.

### Contexte / Mini-Projet : L'Analyseur de Nombre Simple

Imaginez que vous développez un petit utilitaire pour aider à classer des données numériques. La première étape, souvent, est de savoir si un nombre est positif, négatif ou s'il représente une absence de valeur (zéro).

Ce programme, bien que simple, est la base de nombreux systèmes de décision plus complexes. Votre mission est de créer un programme capable de classer un nombre entier donné par l'utilisateur.

### Énoncé de l'Exercice

Écrivez un programme en langage C qui réalise les actions suivantes :

1.  Demande à l'utilisateur de saisir un nombre entier.
2.  Lit ce nombre depuis l'entrée standard.
3.  Détermine si le nombre est :
    *   Strictement positif (supérieur à 0).
    *   Strictement négatif (inférieur à 0).
    *   Nul (égal à 0).
4.  Affiche le résultat à l'écran de manière claire et compréhensible pour l'utilisateur.

### Compétences Visées

*   Déclaration et utilisation de variables.
*   Lecture d'entrée utilisateur (`scanf`).
*   Utilisation des structures conditionnelles (`if`, `else if`, `else`).
*   Affichage de résultats (`printf`).
*   Logique de programmation de base.

### Ressources à Disposition

*   Votre cours et vos notes.
*   La documentation C en ligne (ex: cppreference.com, learn-c.org).
*   Et oui, l'Intelligence Artificielle (ChatGPT, Bard, Copilot, etc.). N'hésitez pas à l'utiliser comme un assistant intelligent pour explorer des idées, comprendre des erreurs, ou même générer des fragments de code. L'objectif est d'apprendre, pas de recopier aveuglément.

### Étapes Suggérées (pour vous guider)

1.  **Initialisation :** Incluez les bibliothèques nécessaires (au minimum `stdio.h` pour l'entrée/sortie). Déclarez votre fonction `main`.
2.  **Déclaration de variable :** Créez une variable de type `int` pour stocker le nombre que l'utilisateur va saisir.
3.  **Interaction utilisateur :**
    *   Utilisez `printf` pour inviter l'utilisateur à saisir un nombre entier.
    *   Utilisez `scanf` pour lire ce nombre et le stocker dans votre variable.
4.  **Logique conditionnelle :** C'est le cœur du TP.
    *   Utilisez une structure `if` pour vérifier si le nombre est positif.
    *   Utilisez un `else if` pour vérifier s'il est négatif.
    *   Utilisez un `else` pour gérer le cas restant (le nombre est nul).
5.  **Affichage du résultat :** Dans chaque bloc conditionnel, utilisez `printf` pour afficher un message clair indiquant si le nombre est positif, négatif ou nul.
6.  **Compilation et Test :** Compilez votre programme et testez-le avec différentes valeurs :
    *   Un nombre positif (ex: 10, 42)
    *   Un nombre négatif (ex: -5, -100)
    *   Zéro (0)

### Pour Aller Plus Loin (Optionnel)

Si vous avez terminé l'exercice principal et que vous souhaitez explorer davantage :

1.  **Validation de l'entrée :** Que se passe-t-il si l'utilisateur entre du texte au lieu d'un nombre ? Comment pourriez-vous gérer cela pour éviter un comportement inattendu (indice : regardez la valeur de retour de `scanf`) ?
2.  **Nombres pairs/impairs :** Modifiez le programme pour qu'il indique également si le nombre est pair ou impair (en plus d'être positif/négatif/nul).
3.  **Boucle :** Permettez à l'utilisateur d'analyser plusieurs nombres sans relancer le programme à chaque fois (indice : `while` ou `for`). Le programme pourrait demander "Voulez-vous analyser un autre nombre ? (o/n)".
4.  **Affichage formaté :** Affichez le nombre saisi par l'utilisateur directement dans le message de résultat (ex: "Le nombre 15 est positif.").

### Conseils du Formateur

*   **Découpez le problème :** Si vous utilisez l'IA, ne lui demandez pas directement "Donne-moi le code complet pour ce TP". Demandez-lui plutôt "Comment déclarer une variable en C ?", "Comment lire un entier avec scanf ?", "Quel est la syntaxe d'un if/else if/else ?". C'est bien plus formateur et cela vous aide à construire votre compréhension pas à pas.
*   **Comprenez avant de copier :** Chaque ligne de code doit avoir un sens pour vous. Si l'IA vous donne une solution, prenez le temps de la comprendre et de l'expliquer avec vos propres mots. C'est la meilleure façon d'apprendre.
*   **Testez rigoureusement :** Un bon programmeur teste son code avec tous les cas de figure possibles. Pensez aux cas limites !
*   **Amusez-vous !** La programmation est une suite de petits défis à résoudre. Chaque solution que vous trouvez est une petite victoire qui renforce vos compétences.

Bon courage et n'hésitez pas si vous avez des questions !