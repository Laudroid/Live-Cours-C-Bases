Voici deux solutions possibles pour le TP "Mini-QCM Interactif - Maîtrise du Contrôle de Flux", présentées sous forme de chapitres distincts.

---

### **Chapitre 1 : Solution Basique - QCM Séquentiel avec `if-else if-else`**

Cette solution implémente le QCM en posant chaque question séquentiellement et en utilisant des structures `if-else if-else` pour vérifier les réponses. Elle inclut la gestion du buffer d'entrée pour une meilleure robustesse.




```c
#include <stdio.h> // Nécessaire pour les fonctions d'entrée/sortie (printf, scanf).
#include <ctype.h> // Nécessaire pour la fonction tolower (convertit un caractère en minuscule).

// Fonction pour vider le buffer d'entrée après une lecture avec scanf.
// Ceci est crucial après scanf("%c", ...) pour éviter que le caractère '\n' restant
// ne soit lu par le scanf suivant.
void viderBuffer() {
    int c;
    while ((c = getchar()) != '\n' && c != EOF);
}

int main() {
    int score = 0;   // Variable pour stocker le score de l'utilisateur, initialisée à 0.
    char reponse_utilisateur; // Variable pour stocker la réponse de l'utilisateur (un caractère).

    // --- Question 1 ---
    printf("1. Quelle boucle garantit que le bloc de code sera exécuté au moins une fois ?\n");
    printf("\t(a) for\n");
    printf("\t(b) while\n");
    printf("\t(c) do-while\n");
    printf("Votre réponse : ");
    scanf(" %c", &reponse_utilisateur); // L'espace avant %c aide à ignorer les caractères blancs résiduels.
    viderBuffer(); // Vide le buffer d'entrée.

    reponse_utilisateur = tolower(reponse_utilisateur); // Convertit la réponse en minuscule.

    if (reponse_utilisateur == 'c') {
        printf("Bonne réponse !\n\n");
        score++;
    } else {
        printf("Mauvaise réponse. La bonne réponse était (c).\n\n");
    }

    // --- Question 2 ---
    printf("2. L'instruction 'break' permet de :\n");
    printf("\t(a) Sauter l'itération actuelle d'une boucle\n");
    printf("\t(b) Sortir complètement d'une boucle\n");
    printf("\t(c) Déclarer une nouvelle variable.\n");
    printf("Votre réponse : ");
    scanf(" %c", &reponse_utilisateur);
    viderBuffer();

    reponse_utilisateur = tolower(reponse_utilisateur);

    if (reponse_utilisateur == 'b') {
        printf("Bonne réponse !\n\n");
        score++;
    } else {
        printf("Mauvaise réponse. La bonne réponse était (b).\n\n");
    }

    // --- Question 3 ---
    printf("3. Pour vérifier si une variable 'age' est supérieure ou égale à 18, quelle est la condition correcte ?\n");
    printf("\t(a) age == 18\n");
    printf("\t(b) age >= 18\n");
    printf("\t(c) age > 18\n");
    printf("Votre réponse : ");
    scanf(" %c", &reponse_utilisateur);
    viderBuffer();

    reponse_utilisateur = tolower(reponse_utilisateur);

    if (reponse_utilisateur == 'b') {
        printf("Bonne réponse !\n\n");
        score++;
    } else {
        printf("Mauvaise réponse. La bonne réponse était (b).\n\n");
    }

    // --- Affichage du score final ---
    printf("--- QCM Terminé ---\n");
    printf("Votre score final est de %d/3.\n", score);

    return 0; // Indique que le programme s'est exécuté avec succès.
}
```




**Explication de la Solution 1 :**

*   **`#include <stdio.h>` et `#include <ctype.h>`** : Ces lignes incluent les bibliothèques nécessaires. `stdio.h` pour les entrées/sorties (`printf`, `scanf`, `getchar`) et `ctype.h` pour `tolower` (qui convertit un caractère en minuscule, rendant les réponses 'A' et 'a' équivalentes).
*   **`void viderBuffer() { ... }`** : Cette fonction est une bonne pratique pour nettoyer le "buffer" (zone de mémoire temporaire) des entrées clavier. Après avoir tapé une réponse et appuyé sur `Entrée`, le caractère `\n` (retour à la ligne) reste dans le buffer. Si non vidé, il pourrait être lu par le `scanf` suivant, causant des problèmes.
*   **`int score = 0;`** : Déclare et initialise la variable `score` à 0. Elle sera incrémentée pour chaque bonne réponse.
*   **`char reponse_utilisateur;`** : Déclare une variable de type `char` pour stocker la réponse de l'utilisateur (un seul caractère comme 'a', 'b', 'c').
*   **`printf(...)`** : Utilisé pour afficher les questions et les options de manière claire.
*   **`scanf(" %c", &reponse_utilisateur);`** : Lit un caractère depuis l'entrée standard.
    *   L'espace avant `%c` est une astuce pour `scanf` : il lui indique d'ignorer tout espace blanc (y compris les `\n` résiduels des saisies précédentes) avant de lire le caractère.
    *   `&reponse_utilisateur` est l'opérateur d'adresse, nécessaire pour que `scanf` puisse modifier la valeur de la variable.
*   **`reponse_utilisateur = tolower(reponse_utilisateur);`** : Convertit la réponse saisie par l'utilisateur en minuscule. Cela permet d'accepter 'a' ou 'A' comme réponse valide sans avoir à écrire des conditions complexes.
*   **`if (reponse_utilisateur == 'c') { ... } else { ... }`** : Ces structures conditionnelles vérifient si la réponse de l'utilisateur correspond à la bonne réponse pour la question en cours. Si c'est le cas, un message de succès est affiché et le `score` est incrémenté. Sinon, un message d'erreur est affiché.
*   **Répétition pour chaque question** : Les étapes d'affichage, de lecture et de vérification sont répétées pour les trois questions.
*   **`printf("Votre score final est de %d/3.\n", score);`** : Affiche le score total à la fin du QCM.
*   **`return 0;`** : Indique au système d'exploitation que le programme s'est terminé sans erreur.

---

### **Chapitre 2 : Solution Avancée - QCM Générique avec Boucle `for`, `do-while` et `switch`**

Cette solution améliore la précédente en rendant le QCM plus générique et robuste. Elle utilise un tableau pour stocker les questions et les bonnes réponses, une boucle `for` pour parcourir les questions, une boucle `do-while` pour valider l'entrée utilisateur, et une instruction `switch` pour la vérification des réponses.




```c
#include <stdio.h> // Nécessaire pour printf, scanf, getchar.
#include <ctype.h> // Nécessaire pour tolower.
#include <string.h> // Nécessaire pour strlen, bien que non utilisé directement ici, utile pour manipulation de chaînes.

// Structure pour représenter une question du QCM.
// Cela rend le QCM plus extensible et facile à gérer.
typedef struct {
    const char *question_text; // Texte de la question.
    const char *options_text;  // Texte des options (a, b, c).
    char correct_answer;       // La bonne réponse (ex: 'a', 'b', 'c').
} Question;

// Fonction pour vider le buffer d'entrée.
void viderBuffer() {
    int c;
    while ((c = getchar()) != '\n' && c != EOF);
}

int main() {
    int score = 0;
    char reponse_utilisateur;
    int i; // Compteur de boucle.

    // Définition des questions du QCM dans un tableau de structures Question.
    Question qcm_questions[] = {
        {"1. Quelle boucle garantit que le bloc de code sera exécuté au moins une fois ?",
         "\t(a) for\n\t(b) while\n\t(c) do-while\n",
         'c'},
        {"2. L'instruction 'break' permet de :",
         "\t(a) Sauter l'itération actuelle d'une boucle\n\t(b) Sortir complètement d'une boucle\n\t(c) Déclarer une nouvelle variable.\n",
         'b'},
        {"3. Pour vérifier si une variable 'age' est supérieure ou égale à 18, quelle est la condition correcte ?",
         "\t(a) age == 18\n\t(b) age >= 18\n\t(c) age > 18\n",
         'b'}
    };

    // Calcul du nombre de questions dans le QCM.
    // sizeof(qcm_questions) donne la taille totale du tableau en octets.
    // sizeof(qcm_questions[0]) donne la taille d'une seule structure Question en octets.
    // La division donne le nombre d'éléments.
    int nombre_questions = sizeof(qcm_questions) / sizeof(qcm_questions[0]);

    // Boucle for pour parcourir toutes les questions du QCM.
    for (i = 0; i < nombre_questions; i++) {
        // Affiche la question et ses options.
        printf("%s", qcm_questions[i].question_text);
        printf("%s", qcm_questions[i].options_text);

        // Boucle do-while pour la validation de l'entrée : demande tant que la réponse n'est pas 'a', 'b' ou 'c'.
        do {
            printf("Votre réponse (a, b ou c) : ");
            scanf(" %c", &reponse_utilisateur);
            viderBuffer(); // Vide le buffer après la lecture.

            reponse_utilisateur = tolower(reponse_utilisateur); // Convertit en minuscule.

            if (reponse_utilisateur != 'a' && reponse_utilisateur != 'b' && reponse_utilisateur != 'c') {
                printf("Entrée invalide. Veuillez taper 'a', 'b' ou 'c'.\n");
            }
        } while (reponse_utilisateur != 'a' && reponse_utilisateur != 'b' && reponse_utilisateur != 'c');

        // Utilisation de switch pour vérifier la réponse.
        switch (reponse_utilisateur) {
            case 'a':
            case 'b':
            case 'c': // Si la réponse est 'a', 'b' ou 'c', on vérifie si c'est la bonne.
                if (reponse_utilisateur == qcm_questions[i].correct_answer) {
                    printf("Bonne réponse !\n\n");
                    score++;
                } else {
                    printf("Mauvaise réponse. La bonne réponse était (%c).\n\n", qcm_questions[i].correct_answer);
                }
                break;
            default: // Ce cas ne devrait pas être atteint grâce à la validation do-while.
                printf("Une erreur inattendue s'est produite.\n\n");
                break;
        }
    }

    // --- Affichage du score final ---
    printf("--- QCM Terminé ---\n");
    printf("Votre score final est de %d/%d.\n", score, nombre_questions);

    // Message personnalisé en fonction du score.
    if (score == nombre_questions) {
        printf("Félicitations, un sans-faute ! Vous maîtrisez parfaitement le sujet.\n");
    } else if (score >= nombre_questions / 2) {
        printf("Bon travail ! Vous avez une bonne compréhension, continuez à réviser.\n");
    } else {
        printf("Revoyez les bases. Chaque erreur est une opportunité d'apprendre !\n");
    }

    return 0;
}
```




**Explication de la Solution 2 :**

*   **`#include <string.h>`** : Bien que non directement utilisé pour une fonction spécifique dans cette version, il est souvent utile pour la manipulation de chaînes de caractères, surtout si l'on devait copier ou concaténer des textes.
*   **`typedef struct { ... } Question;`** : Une structure `Question` est définie. Cela permet de regrouper logiquement toutes les informations relatives à une seule question (le texte de la question, les options, et la bonne réponse). C'est une approche beaucoup plus propre et extensible pour gérer un QCM.
*   **`Question qcm_questions[] = { ... };`** : Un tableau de structures `Question` est créé et initialisé avec toutes les questions du QCM. Cela rend le QCM très facile à étendre : il suffit d'ajouter de nouvelles entrées à ce tableau.
*   **`int nombre_questions = sizeof(qcm_questions) / sizeof(qcm_questions[0]);`** : Cette ligne calcule dynamiquement le nombre de questions dans le tableau. C'est une bonne pratique car si vous ajoutez ou supprimez des questions, le programme s'adapte automatiquement sans avoir à modifier manuellement le nombre d'itérations de la boucle.
*   **`for (i = 0; i < nombre_questions; i++) { ... }`** : Une boucle `for` est utilisée pour parcourir toutes les questions du tableau. À chaque itération, `qcm_questions[i]` fait référence à la question actuelle.
*   **`printf("%s", qcm_questions[i].question_text);`** : Accède aux membres de la structure `Question` pour afficher le texte de la question et des options.
*   **Boucle `do-while` pour la validation de l'entrée** : Cette boucle est une amélioration majeure pour la robustesse. Elle s'assure que l'utilisateur saisit une réponse valide ('a', 'b' ou 'c') avant de passer à la vérification. Si l'entrée est invalide, un message d'erreur est affiché et la question est redemandée.
*   **`switch (reponse_utilisateur) { ... }`** : Au lieu de multiples `if-else if`, une structure `switch` est utilisée pour vérifier la réponse. Pour un petit nombre de cas, c'est souvent une question de préférence, mais pour un grand nombre de cas, `switch` peut être plus lisible.
    *   Les `case 'a': case 'b': case 'c':` sans `break` permettent de regrouper les cas où la réponse est une option valide, puis de vérifier si elle correspond à `qcm_questions[i].correct_answer`.
    *   `break;` est essentiel pour sortir du bloc `switch` une fois qu'un cas a été traité.
*   **Message personnalisé en fonction du score** : À la fin du QCM, un message personnalisé est affiché en fonction du score obtenu, offrant un retour plus engageant à l'utilisateur.

Cette solution avancée démontre comment structurer un programme de manière plus modulaire et extensible, tout en intégrant des techniques de validation d'entrée et en utilisant différentes structures de contrôle de flux de manière efficace.