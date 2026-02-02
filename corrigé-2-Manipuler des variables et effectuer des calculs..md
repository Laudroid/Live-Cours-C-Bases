Voici deux solutions possibles pour le TP "Les Fondamentaux de l'Arithmétique en C", présentées sous forme de chapitres distincts.

---

### **Chapitre 1 : Solution Basique - Calculs Directs**

Cette solution est la plus simple et directe, elle suit les étapes de l'énoncé en déclarant les variables, en demandant les entrées, puis en affichant les résultats des opérations arithmétiques.



```c
#include <stdio.h> // Inclut la bibliothèque standard d'entrée/sortie, nécessaire pour printf et scanf.

int main() {
    // Déclaration des variables entières pour stocker les deux nombres saisis par l'utilisateur.
    int nombre1;
    int nombre2;

    // Déclaration des variables pour stocker les résultats des opérations.
    int somme;
    int difference;
    int produit;
    int division;

    // Demande à l'utilisateur d'entrer le premier nombre.
    printf("Entrez la première quantité (ex: stock initial) : ");
    // Lit l'entier saisi par l'utilisateur et le stocke dans 'nombre1'.
    // Le '&' est nécessaire pour passer l'adresse de la variable à scanf.
    scanf("%d", &nombre1);

    // Demande à l'utilisateur d'entrer le deuxième nombre.
    printf("Entrez la deuxième quantité (ex: mouvement de stock) : ");
    // Lit l'entier saisi par l'utilisateur et le stocke dans 'nombre2'.
    scanf("%d", &nombre2);

    // Effectue les opérations arithmétiques et stocke les résultats.
    somme = nombre1 + nombre2;
    difference = nombre1 - nombre2;
    produit = nombre1 * nombre2;
    // La division entière en C tronque la partie décimale.
    division = nombre1 / nombre2;

    // Affiche les résultats des opérations de manière claire.
    printf("\n--- Résultats des opérations ---\n");
    printf("Somme (Nouveau stock total) : %d\n", somme);
    printf("Différence (Variation nette) : %d\n", difference);
    printf("Produit (Valeur potentielle) : %d\n", produit);
    printf("Division (Lots possibles) : %d\n", division);

    return 0; // Indique que le programme s'est exécuté avec succès.
}
```



**Explication de la Solution 1 :**

*   **`#include <stdio.h>`** : Cette ligne est une directive de préprocesseur qui inclut le fichier d'en-tête `stdio.h`. Ce fichier contient les déclarations des fonctions d'entrée/sortie standard comme `printf` (pour afficher du texte) et `scanf` (pour lire l'entrée de l'utilisateur).
*   **`int main() { ... }`** : C'est la fonction principale de tout programme C. L'exécution du programme commence toujours ici. `int` indique que la fonction retournera un entier (généralement 0 pour indiquer le succès).
*   **`int nombre1;`**, **`int nombre2;`**, etc. : Ces lignes déclarent des variables de type `int` (entier). Elles sont utilisées pour stocker les nombres saisis par l'utilisateur et les résultats des calculs.
*   **`printf("Entrez la première quantité (ex: stock initial) : ");`** : Affiche un message à l'utilisateur pour lui demander de saisir une valeur.
*   **`scanf("%d", &nombre1);`** : Lit un entier depuis l'entrée standard (le clavier) et le stocke dans la variable `nombre1`.
    *   `%d` est un spécificateur de format qui indique à `scanf` qu'il doit lire un entier décimal.
    *   `&nombre1` est l'opérateur d'adresse. `scanf` a besoin de l'adresse mémoire de la variable pour pouvoir y écrire la valeur lue.
*   **`somme = nombre1 + nombre2;`** : Effectue l'opération d'addition et stocke le résultat dans la variable `somme`. Les opérateurs `+`, `-`, `*`, `/` sont les opérateurs arithmétiques de base en C.
*   **`printf("Somme (Nouveau stock total) : %d\n", somme);`** : Affiche le résultat de la somme. Le `%d` est un spécificateur de format qui sera remplacé par la valeur de la variable `somme`. `\n` est un caractère de nouvelle ligne.
*   **`return 0;`** : Termine la fonction `main` et indique au système d'exploitation que le programme s'est exécuté sans erreur.

---

### **Chapitre 2 : Solution Améliorée - Déclaration et Affichage Optimisés**

Cette solution est similaire à la première mais optimise légèrement la déclaration des variables et l'affichage des résultats en utilisant directement les expressions dans les appels à `printf`, ce qui peut rendre le code plus concis pour des calculs simples. Elle inclut également une gestion basique pour éviter la division par zéro.



```c
#include <stdio.h> // Inclut la bibliothèque standard d'entrée/sortie.

int main() {
    // Déclaration des variables entières pour les entrées utilisateur.
    int quantite_initiale;
    int mouvement_stock;

    // Demande à l'utilisateur d'entrer la quantité initiale.
    printf("Entrez la première quantité (ex: stock initial) : ");
    scanf("%d", &quantite_initiale);

    // Demande à l'utilisateur d'entrer le mouvement de stock.
    printf("Entrez la deuxième quantité (ex: mouvement de stock) : ");
    scanf("%d", &mouvement_stock);

    printf("\n--- Résultats des opérations ---\n");

    // Affiche la somme directement en calculant l'expression dans printf.
    printf("Somme (Nouveau stock total) : %d\n", quantite_initiale + mouvement_stock);

    // Affiche la différence.
    printf("Différence (Variation nette) : %d\n", quantite_initiale - mouvement_stock);

    // Affiche le produit.
    printf("Produit (Valeur potentielle) : %d\n", quantite_initiale * mouvement_stock);

    // Vérifie si le deuxième nombre est zéro avant d'effectuer la division.
    // Cela évite une erreur de division par zéro qui ferait planter le programme.
    if (mouvement_stock != 0) {
        printf("Division (Lots possibles) : %d\n", quantite_initiale / mouvement_stock);
    } else {
        printf("Division (Lots possibles) : Impossible de diviser par zéro.\n");
    }

    return 0; // Indique que le programme s'est exécuté avec succès.
}
```



**Explication de la Solution 2 :**

*   **Déclaration des variables** : Les variables sont nommées de manière plus descriptive (`quantite_initiale`, `mouvement_stock`) pour mieux correspondre au contexte du mini-projet.
*   **Calculs directs dans `printf`** : Au lieu de stocker les résultats dans des variables intermédiaires (`somme`, `difference`, etc.), les expressions arithmétiques (`quantite_initiale + mouvement_stock`) sont directement passées comme arguments à `printf`. Pour des calculs simples et non réutilisés, cela rend le code plus concis.
*   **Gestion de la division par zéro** :
    *   **`if (mouvement_stock != 0) { ... } else { ... }`** : C'est une structure conditionnelle. Avant d'effectuer la division, le programme vérifie si `mouvement_stock` est différent de zéro.
    *   Si `mouvement_stock` n'est pas zéro, la division est effectuée et affichée.
    *   Si `mouvement_stock` est zéro, un message d'erreur est affiché pour informer l'utilisateur que la division par zéro est impossible. C'est une amélioration importante pour la robustesse du programme.
*   Le reste du code (`#include <stdio.h>`, `int main()`, `scanf`, `return 0;`) fonctionne de la même manière que dans la première solution.

Ces deux solutions vous fournissent une base solide pour comprendre les opérations arithmétiques et l'interaction utilisateur en C. La deuxième solution introduit une bonne pratique de gestion d'erreur qui est cruciale en programmation.