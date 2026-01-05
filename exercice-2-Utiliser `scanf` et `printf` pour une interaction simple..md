Bonjour à toutes et à tous !

Nous allons ensemble réaliser un premier programme interactif en C. L'objectif est de vous familiariser avec les fonctions de base pour dialoguer avec l'utilisateur : `scanf` pour la saisie et `printf` pour l'affichage.

---

### **TP : Votre Premier Dialogue en C**

**Objectif pédagogique :**
Maîtriser l'utilisation des fonctions `scanf` et `printf` pour collecter et afficher des informations simples.

**Contexte / Mini-projet :**
Imaginez que vous développez un petit programme d'accueil personnalisé. Ce programme doit saluer l'utilisateur en utilisant son prénom et lui rappeler son âge. C'est un scénario simple, mais qui pose les bases de toute interaction utilisateur.

**Énoncé de l'exercice :**

Créez un programme en langage C qui réalise les étapes suivantes :

1.  **Demande le prénom** de l'utilisateur.
2.  **Demande l'âge** de l'utilisateur.
3.  **Affiche une phrase de salutation** personnalisée, reprenant le prénom et l'âge saisis.

**Exemple d'interaction attendue :**

```
Quel est votre prénom ?
Alice
Quel est votre âge ?
30
Bonjour Alice, vous avez 30 ans.
```

---

**Consignes et Conseils :**

*   **Inclusion de la bibliothèque :** N'oubliez pas d'inclure la bibliothèque standard d'entrée/sortie (`stdio.h`) au début de votre fichier.
*   **Déclaration de variables :**
    *   Pour le prénom, vous aurez besoin d'un tableau de caractères (par exemple, `char prenom[50];` pour un prénom de 49 caractères maximum + le caractère nul de fin de chaîne).
    *   Pour l'âge, une variable de type entier (`int`) sera appropriée.
*   **`printf` pour les invites :** Utilisez `printf` pour afficher des messages clairs à l'utilisateur, lui demandant son prénom et son âge.
*   **`scanf` pour la saisie :**
    *   Pour lire une chaîne de caractères (le prénom), utilisez le spécificateur de format `%s`.
    *   Pour lire un entier (l'âge), utilisez le spécificateur de format `%d`.
    *   **Attention :** Lorsque vous utilisez `scanf` pour lire une variable de type simple (comme un `int`), vous devez lui passer l'adresse de cette variable en utilisant l'opérateur `&` (par exemple, `scanf("%d", &age);`). Pour un tableau de caractères (comme `prenom`), le nom du tableau est déjà une adresse, donc pas besoin du `&` (par exemple, `scanf("%s", prenom);`).
*   **`printf` pour l'affichage final :** Construisez la phrase de salutation en utilisant les spécificateurs de format `%s` et `%d` pour insérer le prénom et l'âge dans la chaîne de caractères.

---

**Ressources utiles :**

*   La documentation C sur `scanf` et `printf` (une recherche rapide sur "man scanf" ou "man printf" en ligne vous donnera de nombreux détails).

---

**Pour aller plus loin (facultatif) :**

*   Que se passe-t-il si l'utilisateur entre un prénom avec des espaces (par exemple, "Jean Pierre") ? Comment pourriez-vous gérer cela ? (Indice : regardez du côté de `fgets`).
*   Comment pourriez-vous vérifier que l'âge saisi est bien un nombre et non du texte ? (Indice : la valeur de retour de `scanf` est utile ici).

---

**Un mot sur l'utilisation de l'IA :**

L'intelligence artificielle est un outil puissant et nous encourageons son utilisation pour vous aider dans votre apprentissage. N'hésitez pas à l'interroger pour :

*   Comprendre des concepts spécifiques.
*   Débloquer une situation si vous êtes coincé.
*   Explorer différentes manières de résoudre le problème.
*   Demander des explications sur un bout de code que vous ne comprenez pas.

Cependant, l'objectif principal reste votre compréhension et votre capacité à écrire du code. Utilisez l'IA comme un assistant pédagogique, pas comme un substitut à votre propre réflexion. Si l'IA vous donne une solution, prenez le temps de la lire, de la comprendre et de l'expliquer avec vos propres mots. C'est ainsi que vous progresserez le plus efficacement.

Bon courage et amusez-vous bien avec ce premier dialogue en C !