Voici deux solutions possibles pour le TP "Salutations Personnalisées – Fonctions sans retour et paramètres multiples", présentées sous forme de chapitres distincts.

---

### **Chapitre 1 : Solution Basique - Fonctions avec Paramètres Fixes**

Cette solution implémente la fonction `afficherBonjour` comme demandé et l'appelle plusieurs fois avec des valeurs prédéfinies dans la fonction `main`. C'est une approche directe pour comprendre le concept.


```c
#include <stdio.h> // Inclut la bibliothèque standard d'entrée/sortie, nécessaire pour printf.

// Déclaration (prototype) de la fonction afficherBonjour.
// 'void' indique qu'elle ne retourne aucune valeur.
// Elle prend un tableau de caractères (pour le nom) et un entier (pour l'âge).
void afficherBonjour(char nom[], int age);

int main() {
    // Déclaration et initialisation de variables pour le premier appel.
    char monNom1[] = "Alice";
    int monAge1 = 30;

    // Déclaration et initialisation de variables pour le deuxième appel.
    char monNom2[] = "Bob";
    int monAge2 = 25;

    // Appel de la fonction afficherBonjour avec les premières variables.
    printf("--- Premier appel ---\n");
    afficherBonjour(monNom1, monAge1);

    // Appel de la fonction afficherBonjour avec les deuxièmes variables.
    printf("--- Deuxième appel ---\n");
    afficherBonjour(monNom2, monAge2);

    // Appel de la fonction afficherBonjour directement avec des littéraux (valeurs fixes).
    printf("--- Troisième appel (avec des littéraux) ---\n");
    afficherBonjour("Carol", 42);

    return 0; // Indique que le programme s'est exécuté avec succès.
}

// Définition de la fonction afficherBonjour.
// Elle reçoit une copie de l'adresse du début de la chaîne 'nom' et la valeur de 'age'.
// Elle utilise ces informations pour afficher un message personnalisé.
void afficherBonjour(char nom[], int age) {
    // '%s' est le spécificateur de format pour une chaîne de caractères.
    // '%d' est le spécificateur de format pour un entier décimal.
    printf("Bonjour %s, vous avez %d ans !\n", nom, age);
}
```


**Explication de la Solution 1 :**

*   **`#include <stdio.h>`** : Cette ligne est essentielle car elle inclut les définitions de la fonction `printf` que nous utilisons pour l'affichage.
*   **`void afficherBonjour(char nom[], int age);`** : C'est le **prototype de la fonction**.
    *   `void` signifie que la fonction ne retourne aucune valeur après son exécution.
    *   `afficherBonjour` est le nom de la fonction.
    *   `char nom[]` déclare un paramètre qui est un tableau de caractères (une chaîne de caractères). En C, lorsqu'un tableau est passé à une fonction, c'est en réalité un pointeur vers le premier élément du tableau qui est passé. `char nom[]` est une syntaxe équivalente à `char *nom` dans le contexte d'un paramètre de fonction.
    *   `int age` déclare un paramètre de type entier.
*   **`int main() { ... }`** : La fonction principale où l'exécution du programme commence.
*   **`char monNom1[] = "Alice";` et `int monAge1 = 30;`** : Déclarent et initialisent des variables pour stocker un nom et un âge.
*   **`afficherBonjour(monNom1, monAge1);`** : C'est l'**appel de la fonction**. Les valeurs des variables `monNom1` et `monAge1` sont passées comme arguments à la fonction `afficherBonjour`.
*   **`afficherBonjour("Carol", 42);`** : Démontre que vous pouvez également passer des littéraux (valeurs fixes directement écrites dans le code) comme arguments à la fonction.
*   **`void afficherBonjour(char nom[], int age) { ... }`** : C'est la **définition de la fonction**. Elle contient le code qui sera exécuté lorsque la fonction est appelée.
*   **`printf("Bonjour %s, vous avez %d ans !\n", nom, age);`** : À l'intérieur de la fonction, `printf` utilise les paramètres `nom` et `age` pour construire et afficher le message personnalisé.

---

### **Chapitre 2 : Solution Avancée - Interaction Utilisateur et Robustesse**

Cette solution améliore la précédente en permettant à l'utilisateur de saisir son nom et son âge, en gérant les noms avec des espaces, et en incluant une validation basique pour l'âge. Elle utilise une boucle pour permettre plusieurs salutations.


```c
#include <stdio.h>  // Nécessaire pour printf, scanf, getchar.
#include <string.h> // Nécessaire pour strcspn (manipulation de chaînes).
#include <ctype.h>  // Nécessaire pour tolower (conversion de caractères).

// Déclaration (prototype) de la fonction afficherBonjour.
void afficherBonjour(char nom[], int age);

// Fonction utilitaire pour vider le buffer d'entrée.
// Ceci est crucial après scanf ou fgets pour éviter les problèmes de caractères résiduels.
void viderBuffer() {
    int c;
    while ((c = getchar()) != '\n' && c != EOF);
}

int main() {
    char nom_utilisateur[100]; // Tableau pour stocker le nom de l'utilisateur (jusqu'à 99 caractères + '\0').
    int age_utilisateur;       // Variable pour stocker l'âge de l'utilisateur.
    int saisie_valide;         // Pour vérifier la validité de la saisie de l'âge.
    char continuer_choix;      // Pour demander à l'utilisateur s'il veut continuer.

    printf("--- Programme de Salutation Personnalisée ---\n");

    // Boucle do-while pour permettre à l'utilisateur de saluer plusieurs personnes.
    do {
        // --- Saisie du nom ---
        printf("\nVeuillez entrer votre prénom (peut contenir des espaces) : ");
        // fgets est utilisé pour lire une ligne entière, y compris les espaces.
        // sizeof(nom_utilisateur) garantit que nous ne dépassons pas la taille du tableau.
        // stdin indique de lire depuis l'entrée standard (clavier).
        fgets(nom_utilisateur, sizeof(nom_utilisateur), stdin);

        // fgets inclut le caractère de nouvelle ligne ('\n') si l'utilisateur appuie sur Entrée.
        // Cette ligne trouve le '\n' et le remplace par '\0' (caractère de fin de chaîne).
        nom_utilisateur[strcspn(nom_utilisateur, "\n")] = '\0';

        // --- Saisie de l'âge avec validation ---
        do {
            printf("Veuillez entrer votre âge : ");
            // scanf retourne le nombre d'éléments lus avec succès.
            // Si l'utilisateur entre du texte au lieu d'un nombre, scanf retourne 0.
            saisie_valide = scanf("%d", &age_utilisateur);
            viderBuffer(); // Vide le buffer après la lecture (ou la tentative de lecture).

            if (saisie_valide != 1) {
                printf("Erreur : Veuillez entrer un nombre entier valide pour l'âge.\n");
            } else if (age_utilisateur <= 0 || age_utilisateur > 120) { // Validation de la plage d'âge.
                printf("Erreur : L'âge doit être entre 1 et 120 ans.\n");
                saisie_valide = 0; // Marque la saisie comme invalide pour redemander.
            }
        } while (saisie_valide != 1); // Répète tant que la saisie n'est pas un entier valide dans la plage.

        // Appel de la fonction afficherBonjour avec les données saisies par l'utilisateur.
        afficherBonjour(nom_utilisateur, age_utilisateur);

        // Demande à l'utilisateur s'il veut saluer une autre personne.
        printf("\nVoulez-vous saluer une autre personne ? (o/n) : ");
        scanf(" %c", &continuer_choix); // L'espace avant %c est important pour ignorer les blancs.
        viderBuffer(); // Vide le buffer après la lecture du choix.

        continuer_choix = tolower(continuer_choix); // Convertit le choix en minuscule.

    } while (continuer_choix == 'o'); // Continue la boucle si l'utilisateur a tapé 'o'.

    printf("\nProgramme terminé. Au revoir !\n");

    return 0; // Indique que le programme s'est exécuté avec succès.
}

// Définition de la fonction afficherBonjour (identique à la solution basique).
void afficherBonjour(char nom[], int age) {
    printf("Bonjour %s, vous avez %d ans !\n", nom, age);
}
```


**Explication de la Solution 2 :**

*   **`#include <string.h>` et `#include <ctype.h>`** :
    *   `string.h` est inclus pour la fonction `strcspn`, qui est utilisée pour nettoyer la chaîne lue par `fgets`.
    *   `ctype.h` est inclus pour la fonction `tolower`, utilisée pour rendre la réponse de l'utilisateur ('o' ou 'O') insensible à la casse.
*   **`void viderBuffer() { ... }`** : Cette fonction utilitaire est cruciale pour la robustesse. Elle nettoie le buffer d'entrée après chaque `scanf` ou `fgets`, évitant que des caractères résiduels (comme le `\n` après avoir appuyé sur `Entrée`) n'interfèrent avec les lectures suivantes.
*   **`char nom_utilisateur[100];`** : Déclare un tableau de caractères plus grand pour le nom, permettant de stocker des prénoms plus longs ou des noms composés.
*   **`fgets(nom_utilisateur, sizeof(nom_utilisateur), stdin);`** :
    *   `fgets` est utilisé à la place de `scanf("%s", ...)` pour lire le nom. L'avantage majeur de `fgets` est qu'il lit la ligne entière, y compris les espaces, jusqu'à la limite de taille spécifiée ou jusqu'à un retour à la ligne. Cela permet de saisir des noms comme "Jean Pierre".
    *   `sizeof(nom_utilisateur)` garantit que `fgets` ne débordera pas du tableau.
    *   `stdin` spécifie que l'entrée doit être lue depuis l'entrée standard (le clavier).
*   **`nom_utilisateur[strcspn(nom_utilisateur, "\n")] = '\0';`** : `fgets` inclut le caractère `\n` (retour à la ligne) dans la chaîne lue s'il est présent. Cette ligne trouve la position du `\n` et le remplace par `\0` (le caractère nul de fin de chaîne), nettoyant ainsi la chaîne pour un affichage correct.
*   **Validation de l'âge avec `do-while` et `scanf`'s return value** :
    *   **`do { ... } while (saisie_valide != 1);`** : Une boucle `do-while` est utilisée pour redemander l'âge tant que la saisie n'est pas valide.
    *   **`saisie_valide = scanf("%d", &age_utilisateur);`** : `scanf` retourne le nombre d'éléments qu'il a réussi à lire. Si l'utilisateur tape "trente" au lieu de "30", `scanf` ne lira aucun entier et retournera `0`.
    *   Des conditions supplémentaires (`else if (age_utilisateur <= 0 || age_utilisateur > 120)`) sont ajoutées pour valider la plage de l'âge, s'assurant qu'il est réaliste.
*   **Boucle principale `do-while` pour continuer** : Le programme entier est encapsulé dans une boucle `do-while` qui demande à l'utilisateur s'il souhaite saluer une autre personne. La boucle continue tant que l'utilisateur répond 'o' (ou 'O').
*   **`continuer_choix = tolower(continuer_choix);`** : Convertit le choix de l'utilisateur en minuscule pour une comparaison simple.

Cette solution avancée est plus robuste et interactive, offrant une meilleure expérience utilisateur et illustrant des concepts importants comme la gestion des chaînes avec espaces, la validation d'entrée, et l'utilisation de boucles pour des interactions répétitives.