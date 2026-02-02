Voici deux solutions possibles pour le TP "QCM Interactif - Types de Données & Opérateurs en C", présentées sous forme de chapitres distincts.

---

### **Chapitre 1 : Solution Basique - QCM avec `if/else` et Modulo Simple**

Cette solution implémente le QCM en utilisant des structures `if/else` pour vérifier les réponses et intègre l'opérateur modulo (`%`) de manière simple pour un message final. Elle gère également le nettoyage du buffer d'entrée, une étape importante lors de l'utilisation de `scanf` avec des caractères.



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
    // Déclaration de la variable pour le score, de type long long pour illustrer sa capacité.
    long long score = 0;
    // Déclaration de la variable pour stocker la réponse de l'utilisateur (un caractère).
    char reponse;

    // --- Question 1 ---
    printf("1. Quel est le type de donnée le plus approprié pour stocker un nombre entier très grand (par exemple, plus de 2 milliards) ?\n");
    printf("\t(a) int\n");
    printf("\t(b) short\n");
    printf("\t(c) long long\n");
    printf("Votre réponse : ");
    scanf(" %c", &reponse); // L'espace avant %c aide à ignorer les caractères blancs résiduels.
    viderBuffer(); // Vide le buffer d'entrée.

    reponse = tolower(reponse); // Convertit la réponse en minuscule pour une comparaison flexible.

    if (reponse == 'c') {
        printf("Bonne réponse !\n\n");
        score++;
    } else {
        printf("Mauvaise réponse. La bonne réponse était (c).\n\n");
    }

    // --- Question 2 ---
    printf("2. Que fait l'opérateur '%%' ?\n"); // '%%' est utilisé pour afficher '%' littéralement.
    printf("\t(a) Division\n");
    printf("\t(b) Reste de la division (modulo)\n");
    printf("\t(c) Multiplication\n");
    printf("Votre réponse : ");
    scanf(" %c", &reponse);
    viderBuffer();

    reponse = tolower(reponse);

    if (reponse == 'b') {
        printf("Bonne réponse !\n\n");
        score++;
    } else {
        printf("Mauvaise réponse. La bonne réponse était (b).\n\n");
    }

    // --- Question 3 ---
    printf("3. Pour lire un entier depuis le clavier et le stocker dans une variable 'nombre', quelle est la syntaxe correcte ?\n");
    printf("\t(a) scanf(\"%%d\", nombre);\n");
    printf("\t(b) scanf(\"%%d\", &nombre);\n");
    printf("\t(c) printf(\"%%d\", nombre);\n");
    printf("Votre réponse : ");
    scanf(" %c", &reponse);
    viderBuffer();

    reponse = tolower(reponse);

    if (reponse == 'b') {
        printf("Bonne réponse !\n\n");
        score++;
    } else {
        printf("Mauvaise réponse. La bonne réponse était (b).\n\n");
    }

    // --- Affichage du score final ---
    printf("--- QCM Terminé ---\n");
    printf("Votre score final est de %lld/3.\n", score); // %lld pour afficher un long long.

    // Intégration de l'opérateur modulo pour un message bonus.
    if (score % 2 == 0 && score > 0) { // Si le score est pair et non nul.
        printf("Félicitations pour votre score pair ! C'est un bon signe.\n");
    } else if (score == 3) {
        printf("Parfait ! Un sans-faute, excellent travail !\n");
    } else {
        printf("Continuez à pratiquer, la persévérance est la clé !\n");
    }

    return 0; // Indique que le programme s'est exécuté avec succès.
}
```



**Explication de la Solution 1 :**

*   **`#include <stdio.h>` et `#include <ctype.h>`** : Ces lignes incluent les bibliothèques nécessaires. `stdio.h` pour les entrées/sorties (`printf`, `scanf`, `getchar`) et `ctype.h` pour `tolower` (qui convertit un caractère en minuscule, rendant les réponses 'A' et 'a' équivalentes).
*   **`void viderBuffer() { ... }`** : Cette fonction est une bonne pratique pour nettoyer le "buffer" (zone de mémoire temporaire) des entrées clavier. Après avoir tapé une réponse et appuyé sur `Entrée`, le caractère `\n` (retour à la ligne) reste dans le buffer. Si non vidé, il pourrait être lu par le `scanf` suivant, causant des problèmes.
*   **`long long score = 0;`** : Déclare la variable `score` comme un `long long`. Bien que pour 3 questions un `int` suffirait, l'énoncé suggère d'utiliser `long long` pour illustrer sa capacité à gérer de très grands nombres, ce qui est pertinent pour les types de données.
*   **`char reponse;`** : Déclare une variable de type `char` pour stocker la réponse de l'utilisateur (un seul caractère comme 'a', 'b', 'c').
*   **`printf("2. Que fait l'opérateur '%%' ?\n");`** : Notez le `%%`. Pour afficher le caractère `%` littéralement avec `printf`, il faut l'échapper en le doublant.
*   **`scanf(" %c", &reponse);`** : Lit un caractère. L'espace avant `%c` est une astuce pour `scanf` : il lui indique d'ignorer tout espace blanc (y compris les `\n` résiduels) avant de lire le caractère. L'opérateur `&` est utilisé pour passer l'adresse de la variable `reponse` à `scanf`.
*   **`reponse = tolower(reponse);`** : Convertit la réponse saisie par l'utilisateur en minuscule. Cela permet d'accepter 'a' ou 'A' comme réponse valide sans avoir à écrire `if (reponse == 'a' || reponse == 'A')`.
*   **`if (reponse == 'c') { ... } else { ... }`** : Ces structures conditionnelles vérifient si la réponse de l'utilisateur correspond à la bonne réponse. Si c'est le cas, le `score` est incrémenté.
*   **`printf("Votre score final est de %lld/3.\n", score);`** : Affiche le score final. `%lld` est le spécificateur de format pour afficher une variable de type `long long`.
*   **`if (score % 2 == 0 && score > 0) { ... }`** : Ici, l'opérateur modulo (`%`) est utilisé. `score % 2` calcule le reste de la division de `score` par 2. Si le reste est 0, cela signifie que `score` est un nombre pair. Le `&& score > 0` évite le message pour un score de 0.
*   **`return 0;`** : Indique au système d'exploitation que le programme s'est terminé sans erreur.

---

### **Chapitre 2 : Solution Avancée - QCM avec Validation d'Entrée et `switch`**

Cette solution améliore la précédente en ajoutant une validation robuste des entrées utilisateur (s'assurant que l'utilisateur tape 'a', 'b' ou 'c') et utilise la structure `switch` pour vérifier les réponses, ce qui peut rendre le code plus lisible pour plusieurs options.



```c
#include <stdio.h> // Nécessaire pour printf, scanf, getchar.
#include <ctype.h> // Nécessaire pour tolower.

// Fonction pour vider le buffer d'entrée.
void viderBuffer() {
    int c;
    while ((c = getchar()) != '\n' && c != EOF);
}

int main() {
    long long score = 0;
    char reponse;
    int i; // Compteur de questions pour la boucle.

    // Tableau de bonnes réponses pour une meilleure organisation.
    // Les indices correspondent aux questions (0 pour Q1, 1 pour Q2, etc.).
    char bonnes_reponses[] = {'c', 'b', 'b'};

    // Tableau des questions et options (simplifié pour l'exemple, dans un vrai QCM on utiliserait des structures).
    const char *questions[] = {
        "1. Quel est le type de donnée le plus approprié pour stocker un nombre entier très grand (par exemple, plus de 2 milliards) ?\n\t(a) int\n\t(b) short\n\t(c) long long\n",
        "2. Que fait l'opérateur '%%' ?\n\t(a) Division\n\t(b) Reste de la division (modulo)\n\t(c) Multiplication\n",
        "3. Pour lire un entier depuis le clavier et le stocker dans une variable 'nombre', quelle est la syntaxe correcte ?\n\t(a) scanf(\"%%d\", nombre);\n\t(b) scanf(\"%%d\", &nombre);\n\t(c) printf(\"%%d\", nombre);\n"
    };

    for (i = 0; i < 3; i++) { // Boucle pour parcourir les 3 questions.
        printf("%s", questions[i]); // Affiche la question et ses options.

        // Boucle do-while pour la validation de l'entrée : demande tant que la réponse n'est pas 'a', 'b' ou 'c'.
        do {
            printf("Votre réponse (a, b ou c) : ");
            scanf(" %c", &reponse);
            viderBuffer(); // Vide le buffer après la lecture.

            reponse = tolower(reponse); // Convertit en minuscule.

            if (reponse != 'a' && reponse != 'b' && reponse != 'c') {
                printf("Entrée invalide. Veuillez taper 'a', 'b' ou 'c'.\n");
            }
        } while (reponse != 'a' && reponse != 'b' && reponse != 'c');

        // Utilisation de switch pour vérifier la réponse.
        switch (reponse) {
            case 'a':
            case 'b':
            case 'c': // Si la réponse est 'a', 'b' ou 'c', on vérifie si c'est la bonne.
                if (reponse == bonnes_reponses[i]) {
                    printf("Bonne réponse !\n\n");
                    score++;
                } else {
                    printf("Mauvaise réponse. La bonne réponse était (%c).\n\n", bonnes_reponses[i]);
                }
                break;
            default: // Ce cas ne devrait pas être atteint grâce à la validation do-while.
                printf("Une erreur inattendue s'est produite.\n\n");
                break;
        }
    }

    // --- Affichage du score final ---
    printf("--- QCM Terminé ---\n");
    printf("Votre score final est de %lld/3.\n", score);

    // Intégration de l'opérateur modulo pour un message personnalisé basé sur le score.
    if (score == 3) {
        printf("Félicitations, un sans-faute ! Vous maîtrisez le sujet.\n");
    } else if (score % 3 == 0 && score > 0) { // Si le score est un multiple de 3 (et non zéro).
        printf("Votre score est un multiple de 3 ! C'est un bon signe de progression.\n");
    } else if (score >= 1) {
        printf("Bonne tentative ! Continuez à réviser pour atteindre l'excellence.\n");
    } else {
        printf("N'abandonnez pas ! Chaque erreur est une opportunité d'apprendre.\n");
    }

    return 0;
}
```



**Explication de la Solution 2 :**

*   **`char bonnes_reponses[] = {'c', 'b', 'b'};`** : Un tableau est utilisé pour stocker les bonnes réponses. Cela rend le code plus facile à modifier si les bonnes réponses changent, et plus extensible si de nouvelles questions sont ajoutées.
*   **`const char *questions[] = { ... };`** : Un tableau de pointeurs vers des chaînes de caractères est utilisé pour stocker les questions et leurs options. C'est une manière plus organisée de gérer le contenu du QCM.
*   **`for (i = 0; i < 3; i++) { ... }`** : Une boucle `for` est utilisée pour itérer sur les questions. Cela rend le code plus compact et plus facile à étendre si vous ajoutez d'autres questions.
*   **`do { ... } while (reponse != 'a' && reponse != 'b' && reponse != 'c');`** : Cette boucle `do-while` est une amélioration majeure pour la robustesse. Elle s'assure que l'utilisateur saisit une réponse valide ('a', 'b' ou 'c') avant de passer à la vérification. Si l'entrée est invalide, un message d'erreur est affiché et la question est redemandée.
*   **`switch (reponse) { ... }`** : Au lieu de multiples `if/else if`, une structure `switch` est utilisée pour vérifier la réponse. Pour un petit nombre de cas, c'est souvent une question de préférence, mais pour un grand nombre de cas, `switch` peut être plus lisible.
    *   Les `case 'a': case 'b': case 'c':` sans `break` permettent de regrouper les cas où la réponse est une option valide, puis de vérifier si elle correspond à `bonnes_reponses[i]`.
    *   `break;` est essentiel pour sortir du bloc `switch` une fois qu'un cas a été traité.
*   **`if (score % 3 == 0 && score > 0) { ... }`** : L'opérateur modulo est utilisé ici pour afficher un message spécial si le score est un multiple de 3 (et non zéro), ajoutant une touche de personnalisation basée sur les performances de l'utilisateur.
*   Le reste des concepts (`printf`, `scanf`, `tolower`, `viderBuffer`, `return 0`) est similaire à la première solution, mais leur intégration dans une structure plus organisée et robuste est l'objectif de cette solution avancée.