Voici deux solutions possibles pour le TP "L'Analyseur de Nombre Simple", présentées sous forme de chapitres distincts.

---

### **Chapitre 1 : Solution Basique - Analyse Positive/Négative/Nulle**

Cette solution implémente la logique fondamentale demandée : lire un nombre entier et déterminer s'il est positif, négatif ou nul en utilisant les structures conditionnelles `if`, `else if` et `else`.




```c
#include <stdio.h> // Inclut la bibliothèque standard d'entrée/sortie, nécessaire pour printf et scanf.

int main() {
    int nombre; // Déclare une variable entière pour stocker le nombre saisi par l'utilisateur.

    // Demande à l'utilisateur de saisir un nombre entier.
    printf("Veuillez saisir un nombre entier : ");
    // Lit l'entier saisi par l'utilisateur et le stocke dans la variable 'nombre'.
    // Le '%d' est le spécificateur de format pour un entier décimal.
    // L'opérateur '&' est utilisé pour passer l'adresse de la variable à scanf.
    scanf("%d", &nombre);

    // Début de la structure conditionnelle pour analyser le nombre.
    if (nombre > 0) { // Si le nombre est strictement supérieur à 0.
        printf("Le nombre %d est positif.\n", nombre);
    } else if (nombre < 0) { // Sinon, si le nombre est strictement inférieur à 0.
        printf("Le nombre %d est négatif.\n", nombre);
    } else { // Sinon (le seul cas restant est si le nombre est égal à 0).
        printf("Le nombre %d est nul.\n", nombre);
    }
    // Fin de la structure conditionnelle.

    return 0; // Indique que le programme s'est exécuté avec succès.
}
```




**Explication de la Solution 1 :**

*   **`#include <stdio.h>`** : Cette ligne est une directive de préprocesseur qui inclut le fichier d'en-tête `stdio.h`. Ce fichier fournit les déclarations des fonctions d'entrée/sortie standard comme `printf` (pour afficher du texte sur la console) et `scanf` (pour lire l'entrée de l'utilisateur).
*   **`int main() { ... }`** : C'est la fonction principale de tout programme C. L'exécution du programme commence toujours ici. `int` indique que la fonction `main` retournera un entier (conventionnellement 0 pour un succès).
*   **`int nombre;`** : Déclare une variable nommée `nombre` de type `int`. Le type `int` est utilisé pour stocker des nombres entiers.
*   **`printf("Veuillez saisir un nombre entier : ");`** : Affiche un message à l'utilisateur pour l'inviter à saisir un nombre.
*   **`scanf("%d", &nombre);`** : Lit un entier depuis l'entrée standard (le clavier) et stocke cette valeur dans la variable `nombre`.
    *   `%d` est le spécificateur de format pour indiquer à `scanf` qu'il doit lire un entier décimal.
    *   `&nombre` est l'opérateur d'adresse. `scanf` a besoin de l'adresse mémoire de la variable pour pouvoir y écrire la valeur lue.
*   **`if (nombre > 0) { ... }`** : C'est la première condition. Si la valeur de `nombre` est strictement supérieure à 0, le bloc de code entre accolades est exécuté.
*   **`else if (nombre < 0) { ... }`** : Si la première condition (`nombre > 0`) est fausse, le programme passe à cette condition. Si `nombre` est strictement inférieur à 0, ce bloc est exécuté.
*   **`else { ... }`** : Si aucune des conditions précédentes n'est vraie (c'est-à-dire que `nombre` n'est ni positif ni négatif), alors le nombre doit être 0. Ce bloc est exécuté dans ce cas.
*   **`printf("Le nombre %d est positif.\n", nombre);`** : Affiche le résultat. Le `%d` est un spécificateur de format qui sera remplacé par la valeur de la variable `nombre`. Le `\n` crée un retour à la ligne.
*   **`return 0;`** : Indique au système d'exploitation que le programme s'est terminé avec succès.

---

### **Chapitre 2 : Solution Avancée - Analyse Complète avec Validation et Boucle**

Cette solution intègre les améliorations suggérées dans la section "Pour aller plus loin" : validation de l'entrée, détermination si le nombre est pair ou impair, affichage formaté, et une boucle pour analyser plusieurs nombres sans relancer le programme.




```c
#include <stdio.h> // Inclut la bibliothèque standard d'entrée/sortie.
#include <ctype.h> // Inclut la bibliothèque pour tolower.

// Fonction pour vider le buffer d'entrée.
// Ceci est crucial après scanf si l'utilisateur entre une valeur non attendue (ex: texte au lieu d'un nombre).
void viderBuffer() {
    int c;
    while ((c = getchar()) != '\n' && c != EOF);
}

int main() {
    int nombre;             // Variable pour stocker le nombre saisi.
    int saisie_valide;      // Variable pour vérifier si scanf a lu un entier.
    char continuer_choix;   // Variable pour stocker le choix de l'utilisateur de continuer.

    // Boucle principale pour permettre à l'utilisateur d'analyser plusieurs nombres.
    do {
        // Boucle pour la validation de l'entrée : redemande tant que la saisie n'est pas un entier valide.
        do {
            printf("\nVeuillez saisir un nombre entier : ");
            saisie_valide = scanf("%d", &nombre); // scanf retourne le nombre d'éléments lus avec succès.
            viderBuffer(); // Vide le buffer après la lecture (ou la tentative de lecture).

            if (saisie_valide != 1) { // Si scanf n'a pas réussi à lire un entier.
                printf("Erreur : Veuillez entrer un nombre entier valide.\n");
            }
        } while (saisie_valide != 1); // Répète tant que la saisie n'est pas valide.

        // --- Analyse du nombre (positif/négatif/nul) ---
        if (nombre > 0) {
            printf("Le nombre %d est positif", nombre);
        } else if (nombre < 0) {
            printf("Le nombre %d est négatif", nombre);
        } else {
            printf("Le nombre %d est nul", nombre);
        }

        // --- Analyse du nombre (pair/impair) ---
        // L'opérateur modulo (%) donne le reste de la division.
        // Si le reste de la division par 2 est 0, le nombre est pair.
        if (nombre != 0) { // On ne teste pas pair/impair pour 0, car c'est un cas particulier.
            if (nombre % 2 == 0) {
                printf(" et pair.\n");
            } else {
                printf(" et impair.\n");
            }
        } else {
            printf(".\n"); // Pour le cas où le nombre est 0.
        }

        // Demande à l'utilisateur s'il veut analyser un autre nombre.
        printf("Voulez-vous analyser un autre nombre ? (o/n) : ");
        scanf(" %c", &continuer_choix); // L'espace avant %c est important.
        viderBuffer(); // Vide le buffer après la lecture du choix.

        // Convertit le choix en minuscule pour une comparaison flexible.
        continuer_choix = tolower(continuer_choix);

    } while (continuer_choix == 'o'); // Continue la boucle si l'utilisateur a tapé 'o'.

    printf("Merci d'avoir utilisé l'analyseur de nombre. Au revoir !\n");

    return 0; // Indique que le programme s'est exécuté avec succès.
}
```




**Explication de la Solution 2 :**

*   **`#include <ctype.h>`** : Cette bibliothèque est ajoutée pour utiliser la fonction `tolower()`, qui convertit un caractère en minuscule. Cela permet de gérer les réponses 'O' et 'o' de l'utilisateur de manière équivalente.
*   **`void viderBuffer() { ... }`** : Cette fonction est cruciale pour la robustesse du programme. Après chaque `scanf`, elle nettoie le buffer d'entrée de tout caractère résiduel (comme le `\n` après avoir appuyé sur `Entrée`). Cela évite des comportements inattendus lors des lectures suivantes, surtout si l'utilisateur saisit du texte invalide.
*   **`do { ... } while (continuer_choix == 'o');`** : C'est la boucle principale du programme. Elle permet d'exécuter l'analyse de nombre au moins une fois (`do`) et de la répéter tant que l'utilisateur répond 'o' (ou 'O') à la question "Voulez-vous analyser un autre nombre ?".
*   **Validation de l'entrée pour le nombre** :
    *   **`saisie_valide = scanf("%d", &nombre);`** : `scanf` retourne le nombre d'éléments qu'il a réussi à lire. Si l'utilisateur entre du texte au lieu d'un nombre, `scanf` retourne `0`.
    *   **`if (saisie_valide != 1) { ... }`** : Cette condition vérifie si `scanf` a bien lu un entier. Si ce n'est pas le cas, un message d'erreur est affiché, et la boucle `do-while` interne redemande une saisie.
*   **Analyse Pair/Impair** :
    *   **`if (nombre % 2 == 0) { ... } else { ... }`** : L'opérateur modulo (`%`) est utilisé ici. `nombre % 2` calcule le reste de la division de `nombre` par 2. Si le reste est 0, le nombre est pair ; sinon, il est impair. Une condition `if (nombre != 0)` est ajoutée pour gérer le cas de 0, qui n'est généralement pas classé comme pair ou impair dans ce contexte.
*   **Affichage formaté** : Le nombre saisi (`%d`) est directement inclus dans les messages de résultat (`printf("Le nombre %d est positif", nombre);`) pour une meilleure clarté.
*   **Choix de continuer** : Le programme demande à l'utilisateur s'il souhaite continuer. La réponse est lue avec `scanf(" %c", &continuer_choix);` (l'espace avant `%c` est toujours utile) et convertie en minuscule avec `tolower()` pour accepter les deux casses.

Cette solution avancée est plus robuste et interactive, offrant une meilleure expérience utilisateur et illustrant des concepts importants comme la validation d'entrée et les boucles.