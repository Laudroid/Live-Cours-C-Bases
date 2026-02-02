Salut à toutes et à tous !

Aujourd'hui, on va s'attaquer à un pilier de la programmation : les fonctions. C'est le moyen le plus efficace de structurer votre code, de le rendre réutilisable et plus facile à comprendre. Pas de panique, on commence en douceur avec un exemple concret.

---

### **TP : Création et Utilisation d'une Fonction Simple en C**

**Objectif Pédagogique :**
*   Comprendre la déclaration et la définition d'une fonction en C.
*   Savoir passer un paramètre à une fonction et récupérer sa valeur de retour.
*   Structurer un programme simple en utilisant une fonction dédiée.

**Contexte / Prérequis :**
Vous devriez être à l'aise avec les bases du langage C : la déclaration de variables, les types de données (`int`, `float`), la lecture d'entrée utilisateur (`scanf`) et l'affichage (`printf`).

---

#### **Énoncé du TP : Le Carré d'un Nombre**

Votre mission, si vous l'acceptez, est de créer un programme C qui réalise l'opération suivante :

1.  **Définissez une fonction** nommée `calculerCarre`.
    *   Cette fonction prendra **un seul paramètre** de type entier (`int`).
    *   Elle devra **retourner** la valeur du carré de ce nombre (c'est-à-dire le nombre multiplié par lui-même). Le type de retour sera également un entier (`int`).

2.  Dans la fonction principale `main` :
    *   Demandez à l'utilisateur de saisir un nombre entier.
    *   Appelez votre fonction `calculerCarre` en lui passant le nombre saisi par l'utilisateur.
    *   Affichez le résultat retourné par la fonction de manière claire.

**Exemple d'exécution attendue :**

```
Veuillez entrer un nombre entier : 7
Le carré de 7 est : 49
```

---

#### **Mini-Projet : Calcul de l'Hypoténuse d'un Triangle Rectangle**

Pour aller un peu plus loin et voir l'utilité de votre fonction `calculerCarre` dans un contexte légèrement plus large, nous allons l'intégrer dans un petit programme qui calcule la longueur de l'hypoténuse d'un triangle rectangle.

**Rappel :** Le théorème de Pythagore stipule que dans un triangle rectangle, le carré de la longueur de l'hypoténuse (le côté opposé à l'angle droit) est égal à la somme des carrés des longueurs des deux autres côtés. Soit $a^2 + b^2 = c^2$, où $c$ est l'hypoténuse.

**Votre tâche supplémentaire :**

1.  Dans votre fonction `main`, après avoir résolu l'énoncé précédent :
    *   Demandez à l'utilisateur de saisir la longueur du premier côté (par exemple, `coteA`).
    *   Demandez à l'utilisateur de saisir la longueur du deuxième côté (par exemple, `coteB`).
    *   **Utilisez votre fonction `calculerCarre`** pour obtenir le carré de `coteA` et le carré de `coteB`.
    *   Calculez la somme de ces deux carrés.
    *   Pour trouver l'hypoténuse `c`, vous devrez calculer la racine carrée de cette somme. La fonction `sqrt()` de la bibliothèque `math.h` est votre amie pour cela. N'oubliez pas d'inclure `#include <math.h>` et de compiler avec l'option `-lm` (par exemple, `gcc mon_programme.c -o mon_programme -lm`).
    *   Affichez la longueur de l'hypoténuse.

**Exemple d'exécution attendue pour le mini-projet :**

```
Veuillez entrer la longueur du côté A : 3
Veuillez entrer la longueur du côté B : 4
L'hypoténuse du triangle est : 5.00
```
*(Notez que le résultat de `sqrt` sera un `double` ou `float`, donc l'affichage devra s'adapter.)*

---

#### **Conseils et Points d'Attention :**

*   **Déclaration de la fonction :** Pensez à déclarer votre fonction `calculerCarre` avant `main` (ou à utiliser un prototype de fonction).
*   **Types de données :** Soyez attentifs aux types que vous utilisez pour les paramètres, les retours et les variables. Pour le mini-projet, la racine carrée renvoie un `double`, il faudra donc adapter vos variables pour stocker ce résultat.
*   **Lisibilité :** Un code bien indenté et des noms de variables clairs sont toujours appréciés.
*   **Utilisation de l'IA :** L'utilisation d'outils d'IA (ChatGPT, Copilot, etc.) est encouragée pour vous aider à comprendre, déboguer ou même générer des parties de code. Cependant, l'objectif est votre apprentissage. Ne vous contentez pas de copier-coller sans comprendre.
    *   **Questionnez le code :** Si l'IA vous donne une solution, demandez-vous "Pourquoi cette ligne ?", "Que fait cette fonction ?", "Y a-t-il une autre façon de faire ?".
    *   **Expliquez-le :** Essayez d'expliquer le code généré par l'IA à voix haute (ou à un canard en plastique). Si vous y arrivez, c'est que vous avez compris.
    *   **Déboguez avec l'IA :** Si vous avez une erreur, décrivez-la à l'IA et demandez-lui des pistes pour la résoudre. C'est un excellent moyen d'apprendre le débogage.

---

Bon courage et amusez-vous bien avec ces premières fonctions ! C'est une étape clé pour devenir un programmeur C aguerri.