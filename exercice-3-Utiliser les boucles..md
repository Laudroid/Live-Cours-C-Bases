Salut à toutes et à tous !

Aujourd'hui, on va mettre les mains dans le cambouis avec un TP essentiel : la maîtrise des boucles en C. Les boucles, c'est le moteur de la répétition dans vos programmes. Elles vous permettent d'exécuter un bloc de code plusieurs fois sans avoir à le réécrire. C'est un concept fondamental, et ce TP est conçu pour vous donner une base solide.

---

## TP : Boucles en C - Répéter l'Action, Maîtriser le Flux

### Objectif du TP

*   Comprendre et utiliser la boucle `for` pour des itérations avec un nombre de répétitions connu.
*   Comprendre et utiliser la boucle `while` pour des itérations basées sur une condition.
*   Développer une logique de programme simple pour des tâches répétitives.

### Prérequis

*   Notions de base en C : déclaration de variables, types de données (`int`), opérateurs arithmétiques, `printf()` et `scanf()`.
*   Savoir compiler et exécuter un programme C.

---

### Exercice 1 : Le Compteur Simple (`for`)

**Contexte du mini-projet :** Imaginez que vous devez créer un petit outil pour afficher une séquence numérique simple, par exemple, pour numéroter des éléments ou simplement compter. La boucle `for` est parfaite pour cela.

**Enoncé :**
Créez un programme C qui affiche les nombres entiers de 1 à 10, chacun sur une nouvelle ligne. Vous devez impérativement utiliser une boucle `for` pour réaliser cette tâche.

**Instructions :**

1.  Créez un nouveau fichier nommé `compteur_for.c`.
2.  Dans ce fichier, écrivez le code C nécessaire.
3.  Déclarez une variable entière qui servira de compteur pour votre boucle.
4.  Initialisez cette variable à 1.
5.  Définissez la condition de votre boucle pour qu'elle continue tant que le compteur est inférieur ou égal à 10.
6.  À chaque itération, incrémentez votre compteur de 1.
7.  À l'intérieur de la boucle, utilisez `printf()` pour afficher la valeur actuelle du compteur, suivie d'un retour à la ligne.

**Exemple de sortie attendue :**

```
1
2
3
4
5
6
7
8
9
10
```

**Conseil :** Rappelez-vous la structure de la boucle `for` : `for (initialisation; condition; incrémentation) { /* code à répéter */ }`.

---

### Exercice 2 : La Calculatrice de Somme Interactive (`while`)

**Contexte du mini-projet :** Vous souhaitez développer une petite calculatrice qui permet à l'utilisateur de saisir plusieurs nombres et d'en calculer la somme totale. L'utilisateur doit pouvoir décider quand il a fini de saisir des nombres, en entrant une valeur spécifique (ici, 0). La boucle `while` est idéale pour ce scénario, car le nombre d'itérations n'est pas connu à l'avance.

**Enoncé :**
Créez un programme C qui demande à l'utilisateur de saisir des nombres entiers. Le programme doit continuer à demander des nombres et à les additionner tant que l'utilisateur n'entre pas la valeur 0. Une fois que l'utilisateur a saisi 0, le programme doit afficher la somme totale de tous les nombres saisis (le 0 lui-même ne doit pas être inclus dans la somme). Vous devez utiliser une boucle `while`.

**Instructions :**

1.  Créez un nouveau fichier nommé `somme_while.c`.
2.  Dans ce fichier, écrivez le code C nécessaire.
3.  Déclarez une variable entière pour stocker la somme des nombres (initialisez-la à 0).
4.  Déclarez une autre variable entière pour stocker le nombre que l'utilisateur va saisir.
5.  Avant d'entrer dans la boucle `while`, demandez une première fois à l'utilisateur de saisir un nombre. C'est important pour initialiser la condition de la boucle.
6.  Mettez en place une boucle `while` dont la condition est que le nombre saisi par l'utilisateur est différent de 0.
7.  À l'intérieur de la boucle :
    *   Ajoutez le nombre saisi à votre variable de somme.
    *   Demandez à nouveau à l'utilisateur de saisir un nombre (cette nouvelle saisie sera utilisée pour la prochaine évaluation de la condition de la boucle).
8.  Une fois que la boucle se termine (c'est-à-dire quand l'utilisateur a entré 0), utilisez `printf()` pour afficher la somme totale.

**Exemple d'interaction et de sortie attendue :**

```
Entrez un nombre (0 pour terminer) : 5
Entrez un nombre (0 pour terminer) : 10
Entrez un nombre (0 pour terminer) : 2
Entrez un nombre (0 pour terminer) : 0
La somme des nombres saisis est : 17
```

**Conseil :** Pensez bien à l'ordre des opérations à l'intérieur de votre boucle `while`. La lecture d'un nouveau nombre doit se faire *après* l'addition du nombre précédent, et avant la prochaine vérification de la condition.

---

### Consignes Générales et Utilisation de l'IA

L'intelligence artificielle est un outil formidable pour l'apprentissage et la résolution de problèmes. N'hésitez pas à l'utiliser si vous êtes bloqués, pour comprendre un concept, ou même pour vérifier vos solutions.

Cependant, gardez à l'esprit que l'objectif principal de ce TP est *votre* apprentissage et votre compréhension. Si vous utilisez l'IA :

*   **Ne vous contentez pas de copier-coller.** Lisez attentivement le code généré.
*   **Comprenez chaque ligne.** Posez-vous la question : "Pourquoi cette ligne est-elle là ? Que fait-elle ?"
*   **Expliquez le code à voix haute** (ou mentalement) comme si vous l'expliquiez à quelqu'un d'autre.
*   **Modifiez le code.** Essayez de le simplifier, de le rendre plus clair, ou d'ajouter des fonctionnalités.
*   **Déboguez vous-même.** L'IA peut parfois générer du code qui ne fonctionne pas parfaitement ou qui n'est pas optimal. Votre capacité à identifier et corriger les erreurs est précieuse.

Le but est de développer votre autonomie et votre logique de programmation, pas seulement de produire un résultat.

---

### Pour aller plus loin (Optionnel)

Si vous avez terminé les exercices principaux et que vous vous sentez à l'aise, voici quelques défis supplémentaires :

1.  **Pour l'Exercice 1 (`for`) :**
    *   Modifiez le programme pour qu'il affiche uniquement les nombres pairs de 1 à 20.
    *   Modifiez-le pour qu'il affiche les nombres de 10 à 1 dans l'ordre décroissant.
2.  **Pour l'Exercice 2 (`while`) :**
    *   En plus de la somme, calculez et affichez la moyenne des nombres saisis (sans compter le 0).
    *   Comptez combien de nombres différents de 0 ont été saisis par l'utilisateur.

---

Bon courage à toutes et à tous ! N'hésitez pas à poser des questions si vous rencontrez des difficultés. C'est en forgeant qu'on devient forgeron, et en codant qu'on devient développeur !