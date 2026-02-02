Bonjour à toutes et à tous !

Ce TP est conçu pour vous permettre de manipuler concrètement les structures de contrôle de flux en C, qui sont le cœur de la logique de tout programme. Vous allez développer un petit QCM interactif, ce qui est un excellent moyen d'appliquer ces concepts.

---

**TP: Mini-QCM Interactif - Maîtrise du Contrôle de Flux**

**Objectif du TP :**
L'objectif est de renforcer votre compréhension et votre capacité à utiliser les structures de contrôle de flux fondamentales en langage C : les conditions (`if`, `else if`, `else`) et les boucles (`for`, `while`, `do-while`). Vous allez créer un programme simple qui illustre ces mécanismes.

**Prérequis :**
*   Connaissance des bases du langage C (déclaration de variables, types de données, `printf`, `scanf`).
*   Un environnement de développement C fonctionnel (compilateur GCC, éditeur de texte ou IDE).

**Scénario du mini-projet :**
Vous allez développer un programme console qui pose une série de questions à choix multiples. Pour chaque question, le programme devra :
1.  Afficher la question et ses options de réponse.
2.  Demander à l'utilisateur de saisir sa réponse.
3.  Vérifier si la réponse est correcte.
4.  Maintenir un score et l'afficher à la fin du QCM.

Ce projet, bien que modeste, vous donnera l'occasion de mettre les mains dans le cambouis avec les conditions et les boucles.

**Les questions du QCM à intégrer :**

Voici les questions que votre programme devra poser à l'utilisateur :

1.  Quelle boucle garantit que le bloc de code sera exécuté au moins une fois ?
    (a) `for`
    (b) `while`
    (c) `do-while`

2.  L'instruction `break` permet de :
    (a) Sauter l'itération actuelle d'une boucle
    (b) Sortir complètement d'une boucle
    (c) Déclarer une nouvelle variable.

3.  Pour vérifier si une variable `age` est supérieure ou égale à 18, quelle est la condition correcte ?
    (a) `age == 18`
    (b) `age >= 18`
    (c) `age > 18`

**Consignes de réalisation :**

Votre programme sera un fichier `.c` unique.

**Étape 1 : Préparation du projet**
*   Créez un nouveau fichier nommé `qcm_flux.c`.
*   Incluez la bibliothèque `stdio.h` pour gérer les entrées et sorties.
*   Dans votre fonction `main`, déclarez une variable entière `score` et initialisez-la à 0.

**Étape 2 : Gestion de la première question**
*   Utilisez `printf` pour afficher clairement la première question et ses trois options.
*   Déclarez une variable de type `char` (par exemple `reponse_utilisateur`) pour stocker la réponse de l'utilisateur.
*   Utilisez `scanf` pour lire le caractère saisi par l'utilisateur. Une petite astuce pour éviter les problèmes avec le caractère de nouvelle ligne (`\n`) laissé par `scanf` est d'ajouter un espace avant le `%c` : `scanf(" %c", &reponse_utilisateur);`.

**Étape 3 : Vérification de la réponse 1**
*   Mettez en place une structure `if-else if-else` pour évaluer la `reponse_utilisateur`.
    *   Si la réponse est correcte (par exemple, 'c' ou 'C' pour la question 1), affichez un message de succès et incrémentez la variable `score`.
    *   Sinon, affichez un message indiquant que la réponse est incorrecte.

**Étape 4 : Répétition pour les questions suivantes**
*   Répétez les étapes 2 et 3 pour la deuxième et la troisième question. Veillez à bien adapter les questions, les options et les réponses correctes.

**Étape 5 : Affichage du résultat final**
*   Une fois toutes les questions posées et traitées, utilisez `printf` pour afficher le score total de l'utilisateur.

---

**Pistes d'amélioration et pour aller plus loin (optionnel) :**

Ces suggestions sont là pour vous encourager à explorer davantage et à rendre votre QCM plus robuste.

*   **Validation de l'entrée :** Que se passe-t-il si l'utilisateur saisit un chiffre ou une chaîne de caractères au lieu de 'a', 'b' ou 'c' ? Comment pourriez-vous utiliser une boucle `do-while` (tiens, comme la question 1 du QCM !) pour demander à l'utilisateur de saisir à nouveau sa réponse tant qu'elle n'est pas valide ?
*   **Structure du QCM :** Pour un QCM plus grand, répéter le code pour chaque question n'est pas très efficace. Comment pourriez-vous utiliser un tableau de chaînes de caractères (pour les questions et les options) et une boucle `for` ou `while` pour parcourir toutes les questions de manière plus générique ?
*   **L'instruction `switch` :** Pour la vérification des réponses, l'instruction `switch` peut être une alternative élégante à `if-else if-else` lorsque vous avez plusieurs cas discrets à gérer.

---

**Utilisation de l'IA (ChatGPT, Copilot, etc.) :**

L'IA est un outil formidable pour l'apprentissage et le développement, et son utilisation est tout à fait pertinente. L'objectif est d'apprendre et de comprendre, pas de "faire faire" sans effort. Voici comment l'utiliser intelligemment pour ce TP :

*   **Comprendre un concept :** Si une structure de contrôle de flux vous semble obscure, demandez à l'IA de vous l'expliquer avec des exemples clairs et simples.
*   **Débogage :** Si votre code ne compile pas ou ne se comporte pas comme attendu, copiez le message d'erreur ou décrivez le problème à l'IA. Elle peut souvent vous aider à identifier la cause.
*   **Explorer des alternatives :** Une fois que vous avez une solution fonctionnelle, n'hésitez pas à demander : "Comment pourrais-je améliorer ce code ?" ou "Y a-t-il d'autres façons d'implémenter la vérification des réponses en C ?"
*   **Générer des exemples ciblés :** Demandez-lui des petits bouts de code pour des tâches spécifiques, par exemple : "Comment lire un caractère en C en ignorant les caractères blancs résiduels ?"
*   **À éviter :** Demander "Donne-moi le code complet pour ce TP". Si vous optez pour cette approche, prenez le temps d'analyser *chaque ligne* du code généré, de le modifier, et de pouvoir l'expliquer. L'objectif principal est votre apprentissage et votre maîtrise du code.

Bon courage pour ce TP ! N'hésitez pas à expérimenter et à poser des questions si vous rencontrez des difficultés.