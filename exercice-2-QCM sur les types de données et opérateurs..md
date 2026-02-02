Bonjour à toutes et à tous,

Ce TP est conçu pour vous permettre de manipuler concrètement les concepts de types de données et d'opérateurs en langage C. L'idée est de passer de la compréhension théorique à une application pratique immédiate.

---

### **TP : QCM Interactif - Types de Données & Opérateurs en C**

**Objectif du TP :**
Consolider votre compréhension des types de données fondamentaux et des opérateurs essentiels en langage C en développant un petit programme interactif.

**Compétences Visées :**
*   Déclarer et utiliser différents types de données (notamment `int`, `long long`).
*   Utiliser l'opérateur arithmétique de modulo (`%`).
*   Gérer les entrées utilisateur (`scanf`).
*   Afficher des informations formatées (`printf`).
*   Mettre en œuvre des structures conditionnelles (`if/else`) pour la logique de programme.

**Ressources :**
N'hésitez pas à consulter la documentation officielle, vos notes de cours, et bien sûr, à solliciter les outils d'IA pour vous aider dans la conception ou le débogage de votre code. L'important est de comprendre ce que vous faites et pourquoi.

---

**Énoncé du QCM (Rappel) :**

Voici les questions sur lesquelles nous allons travailler. Pour chaque question, la bonne réponse est (a), (b) ou (c).

1.  Quel est le type de donnée le plus approprié pour stocker un nombre entier très grand (par exemple, plus de 2 milliards) ?
    (a) `int`
    (b) `short`
    (c) `long long`

2.  Que fait l'opérateur `%` ?
    (a) Division
    (b) Reste de la division (modulo)
    (c) Multiplication

3.  Pour lire un entier depuis le clavier et le stocker dans une variable `nombre`, quelle est la syntaxe correcte ?
    (a) `scanf("%d", nombre);`
    (b) `scanf("%d", &nombre);`
    (c) `printf("%d", nombre);`

---

**Mini-Projet : Votre Premier QCM Interactif**

Votre tâche est de créer un programme C qui pose les trois questions du QCM ci-dessus à l'utilisateur, lit ses réponses, vérifie si elles sont correctes, et affiche un score final.

**Consignes Détaillées :**

1.  **Initialisation :**
    *   Déclarez une variable pour stocker le score de l'utilisateur. Pour illustrer le QCM, utilisez un type de donnée capable de gérer des nombres potentiellement plus grands que `int` si le QCM s'allongeait, par exemple `long long`. Initialisez-la à 0.

2.  **Boucle de Questions (ou séquentiel) :**
    Pour chaque question du QCM :
    *   **Affichage :** Utilisez `printf` pour afficher la question et ses options à l'utilisateur.
    *   **Lecture de la réponse :** Utilisez `scanf` pour lire la réponse de l'utilisateur. La réponse sera un caractère (`'a'`, `'b'`, ou `'c'`). N'oubliez pas l'opérateur `&` pour `scanf` et le spécificateur de format approprié pour un caractère (`%c`).
    *   **Vérification :** Utilisez des structures conditionnelles (`if` ou `if/else if/else`) pour comparer la réponse de l'utilisateur avec la bonne réponse.
    *   **Mise à jour du score :** Si la réponse est correcte, incrémentez la variable de score.

3.  **Intégration de l'opérateur `%` (Bonus/Illustration) :**
    *   Trouvez un moyen d'intégrer l'opérateur `%` (modulo) dans votre programme. Par exemple, vous pourriez :
        *   Afficher un message spécial si le score est un multiple de 2 ou 3.
        *   Ou, si vous vous sentez créatif, l'utiliser pour un calcul annexe (par exemple, "il vous reste X chances avant un bonus" si vous aviez un système de vies). L'idée est de le manipuler.

4.  **Affichage Final :**
    *   Une fois toutes les questions posées, utilisez `printf` pour afficher le score total de l'utilisateur.

---

**Points d'attention & Conseils :**

*   **Types de données :** Réfléchissez au type le plus adapté pour stocker la *réponse* de l'utilisateur (un caractère ?).
*   **Opérateurs :** Assurez-vous de bien comprendre l'utilité de `%` et de l'appliquer correctement dans votre code.
*   **Entrées/Sorties :** Maîtrisez l'utilisation de `scanf` (avec l'opérateur d'adresse `&`) et `printf` pour une interaction fluide.
*   **Logique :** La structure `if/else` est votre meilleure amie pour la vérification des réponses.
*   **Clarté du code :** Commentez votre code pour expliquer les parties importantes et utilisez des noms de variables explicites.

---

**Livraison :**

Un fichier `.c` contenant votre programme. Assurez-vous que le code compile sans erreur et s'exécute correctement.

Bon courage, et amusez-vous bien avec ce premier pas vers l'interactivité en C !