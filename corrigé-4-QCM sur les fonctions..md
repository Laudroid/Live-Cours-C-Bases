Voici deux solutions possibles pour le TP "Maîtrise des Fonctions en C - Un Calculateur Modulaire", présentées sous forme de chapitres distincts.

---

### **Chapitre 1 : Solution Basique - Calculateur Modulaire Simple**

Cette solution implémente toutes les fonctions requises par l'énoncé, en se concentrant sur la structure modulaire et l'utilisation des types de retour et des paramètres. La saisie des nombres est simple, sans validation robuste.

#### **Réponses au QCM**

1.  **Quel est le rôle principal d'une fonction en C ?**
    *   (b) Regrouper des instructions pour une tâche spécifique
2.  **Si une fonction ne renvoie aucune valeur, quel type de retour doit-elle avoir ?**
    *   (c) `void`
3.  **Le prototype d'une fonction est :**
    *   (b) Sa déclaration avant son utilisation

#### **Code du Mini-Projet**


```c
#include <stdio.h> // Inclut la bibliothèque standard d'entrée/sortie pour printf et scanf.

// --- Prototypes des fonctions ---
// Déclarations des fonctions pour informer le compilateur de leur existence,
// de leurs paramètres et de leurs types de retour avant leur utilisation dans main.
void afficherBienvenue();
int saisirNombre(int ordre);
int calculerSomme(int n1, int n2, int n3);
float calculerMoyenne(int somme, int nombreDeValeurs);
void afficherResultat(float moyenne);

int main() {
    int nombre1, nombre2, nombre3; // Variables pour stocker les trois nombres saisis.
    int somme_totale;              // Variable pour stocker la somme des nombres.
    float moyenne_finale;          // Variable pour stocker la moyenne calculée.

    afficherBienvenue(); // Appel de la fonction pour afficher le message de bienvenue.

    // Appel de la fonction saisirNombre trois fois pour obtenir les entrées utilisateur.
    // Le paramètre 'ordre' permet de personnaliser le message d'invitation.
    nombre1 = saisirNombre(1);
    nombre2 = saisirNombre(2);
    nombre3 = saisirNombre(3);

    // Appel de la fonction calculerSomme avec les trois nombres.
    somme_totale = calculerSomme(nombre1, nombre2, nombre3);

    // Appel de la fonction calculerMoyenne.
    // Le nombre de valeurs est fixe à 3 pour ce TP.
    moyenne_finale = calculerMoyenne(somme_totale, 3);

    // Appel de la fonction afficherResultat pour présenter la moyenne.
    afficherResultat(moyenne_finale);

    return 0; // Indique que le programme s'est exécuté avec succès.
}

// --- Définitions des fonctions ---

// Fonction qui affiche un message de bienvenue. Ne retourne rien (void).
void afficherBienvenue() {
    printf("Bienvenue dans le Calculateur de Moyenne Simple !\n");
    printf("Ce programme vous aidera à calculer la moyenne de trois nombres entiers.\n\n");
}

// Fonction qui demande à l'utilisateur de saisir un nombre entier.
// Prend un entier 'ordre' pour personnaliser le message (ex: 1er, 2ème).
// Retourne l'entier saisi.
int saisirNombre(int ordre) {
    int nombre;
    printf("Saisissez le %der nombre : ", ordre); // Note: %der est une astuce pour l'affichage (1er, 2ème, 3ème).
    scanf("%d", &nombre); // Lit l'entier saisi par l'utilisateur.
    // Dans cette version basique, il n'y a pas de gestion d'erreur si l'utilisateur ne saisit pas un nombre.
    return nombre;
}

// Fonction qui calcule la somme de trois nombres entiers.
// Prend trois entiers en paramètres et retourne leur somme (entier).
int calculerSomme(int n1, int n2, int n3) {
    return n1 + n2 + n3;
}

// Fonction qui calcule la moyenne.
// Prend la somme totale (entier) et le nombre de valeurs (entier).
// Retourne la moyenne sous forme de nombre flottant (float).
float calculerMoyenne(int somme, int nombreDeValeurs) {
    // Conversion explicite de 'somme' en 'float' avant la division.
    // Cela garantit que la division est une opération flottante, et non une division entière
    // qui tronquerait la partie décimale du résultat.
    return (float)somme / nombreDeValeurs;
}

// Fonction qui affiche la moyenne calculée. Ne retourne rien (void).
// Prend la moyenne (float) en paramètre.
void afficherResultat(float moyenne) {
    // "%.1f" formate l'affichage du nombre flottant pour n'avoir qu'un chiffre après la virgule.
    printf("\nLa moyenne des nombres saisis est : %.1f\n", moyenne);
}
```


#### **Explication de la Solution 1 :**

*   **`#include <stdio.h>`** : Cette ligne inclut la bibliothèque d'entrée/sortie standard, essentielle pour utiliser `printf` (affichage) et `scanf` (saisie).
*   **Prototypes de fonctions** : Toutes les fonctions (`afficherBienvenue`, `saisirNombre`, etc.) sont déclarées avant la fonction `main`. Cela permet au compilateur de savoir comment appeler ces fonctions (quels paramètres elles attendent et quel type elles retournent) avant même de voir leur code complet.
*   **`main` function** : C'est le chef d'orchestre du programme. Elle appelle les autres fonctions dans l'ordre logique pour réaliser la tâche.
*   **`void afficherBienvenue()`** : Une fonction simple qui ne prend aucun paramètre et ne retourne aucune valeur (`void`). Son rôle est purement d'afficher un message.
*   **`int saisirNombre(int ordre)`** : Cette fonction prend un paramètre `ordre` (un entier) pour personnaliser le message d'invitation ("Saisissez le 1er nombre : ", etc.). Elle utilise `scanf` pour lire un entier et le retourne (`int`).
*   **`int calculerSomme(int n1, int n2, int n3)`** : Prend trois entiers en paramètres et retourne leur somme. Le type de retour est `int` car la somme de trois entiers est un entier.
*   **`float calculerMoyenne(int somme, int nombreDeValeurs)`** : Prend la somme et le nombre de valeurs. Pour obtenir une moyenne avec des décimales, il est crucial de convertir au moins l'un des opérandes en `float` (ici, `(float)somme`) avant la division. Le résultat est un `float`.
*   **`void afficherResultat(float moyenne)`** : Prend la moyenne calculée (`float`) et l'affiche. Le format `%.1f` est utilisé avec `printf` pour limiter l'affichage à une décimale.
*   **Définitions des fonctions** : Le code complet de chaque fonction est placé après `main`. C'est une pratique courante en C.

---

### **Chapitre 2 : Solution Avancée - Robustesse et Messages Personnalisés**

Cette solution reprend la structure modulaire et ajoute des améliorations pour la robustesse (validation des entrées) et l'interactivité (messages personnalisés), répondant ainsi aux pistes d'amélioration.

#### **Réponses au QCM**

1.  **Quel est le rôle principal d'une fonction en C ?**
    *   (b) Regrouper des instructions pour une tâche spécifique
2.  **Si une fonction ne renvoie aucune valeur, quel type de retour doit-elle avoir ?**
    *   (c) `void`
3.  **Le prototype d'une fonction est :**
    *   (b) Sa déclaration avant son utilisation

#### **Code du Mini-Projet**


```c
#include <stdio.h>  // Inclut la bibliothèque standard d'entrée/sortie.
#include <stdlib.h> // Inclut EXIT_SUCCESS pour une meilleure sémantique de retour.

// --- Prototypes des fonctions ---
void afficherBienvenue();
int saisirNombre(int ordre);
int calculerSomme(int n1, int n2, int n3);
float calculerMoyenne(int somme, int nombreDeValeurs);
void afficherResultat(float moyenne);

// --- Fonction utilitaire pour vider le buffer d'entrée ---
// Cette fonction est essentielle pour gérer les entrées invalides avec scanf.
// Elle consomme tous les caractères restants dans le buffer jusqu'au '\n' ou EOF.
void viderBuffer() {
    int c;
    while ((c = getchar()) != '\n' && c != EOF);
}

int main() {
    int nombre1, nombre2, nombre3;
    int somme_totale;
    float moyenne_finale;

    afficherBienvenue();

    // Saisie des trois nombres en utilisant la fonction saisirNombre,
    // qui inclut maintenant une validation robuste.
    nombre1 = saisirNombre(1);
    nombre2 = saisirNombre(2);
    nombre3 = saisirNombre(3);

    somme_totale = calculerSomme(nombre1, nombre2, nombre3);
    moyenne_finale = calculerMoyenne(somme_totale, 3);
    afficherResultat(moyenne_finale);

    return EXIT_SUCCESS; // Utilisation de EXIT_SUCCESS pour indiquer un succès.
}

// --- Définitions des fonctions ---

void afficherBienvenue() {
    printf("Bienvenue dans le Calculateur de Moyenne Modulaire Avancé !\n");
    printf("Ce programme vous guidera pour calculer la moyenne de trois nombres entiers.\n\n");
}

// Fonction pour saisir un nombre entier avec validation d'entrée.
// Prend un entier 'ordre' pour personnaliser le message.
// Retourne l'entier valide saisi par l'utilisateur.
int saisirNombre(int ordre) {
    int nombre;
    int saisie_valide; // Stocke la valeur de retour de scanf.
    // Tableau de chaînes pour personnaliser les messages (1er, 2ème, 3ème).
    const char *suffixes[] = {"1er", "2ème", "3ème"};

    do {
        // Affiche le message d'invitation personnalisé en utilisant le tableau de suffixes.
        printf("Saisissez le %s nombre : ", suffixes[ordre - 1]); // ordre-1 car les tableaux sont basés sur 0.
        saisie_valide = scanf("%d", &nombre); // Tente de lire un entier.
        viderBuffer(); // Vide le buffer d'entrée après chaque tentative de lecture.

        if (saisie_valide != 1) { // Si scanf n'a pas réussi à lire un entier (retourne 0).
            printf("Erreur : Veuillez entrer un nombre entier valide.\n");
        }
    } while (saisie_valide != 1); // Répète la boucle tant que la saisie n'est pas valide.

    return nombre;
}

int calculerSomme(int n1, int n2, int n3) {
    return n1 + n2 + n3;
}

// Fonction pour calculer la moyenne, avec une protection contre la division par zéro.
float calculerMoyenne(int somme, int nombreDeValeurs) {
    if (nombreDeValeurs == 0) {
        // Retourne 0.0f si le nombre de valeurs est zéro pour éviter une erreur de division par zéro.
        // C'est une gestion d'erreur simple pour ce cas.
        return 0.0f;
    }
    return (float)somme / nombreDeValeurs; // Division flottante.
}

// Fonction qui affiche la moyenne calculée avec un message personnalisé.
void afficherResultat(float moyenne) {
    printf("\nLa moyenne calculée est : %.1f\n", moyenne);

    // Ajout de messages personnalisés en fonction de la moyenne obtenue.
    if (moyenne >= 15.0f) {
        printf("Excellent travail ! Votre moyenne est très bonne.\n");
    } else if (moyenne >= 10.0f) {
        printf("Bonne moyenne, continuez vos efforts pour l'améliorer.\n");
    } else {
        printf("Il y a de la marge pour s'améliorer. N'hésitez pas à réviser les bases.\n");
    }
}
```


#### **Explication de la Solution 2 :**

*   **`#include <stdlib.h>`** : Inclus pour la constante `EXIT_SUCCESS`, qui est une alternative plus sémantique à `return 0;` pour indiquer que le programme s'est terminé avec succès.
*   **`void viderBuffer()`** : Cette fonction utilitaire est cruciale. Elle nettoie le buffer d'entrée après chaque `scanf`. Si l'utilisateur tape du texte au lieu d'un nombre, ce texte reste dans le buffer et pourrait causer des problèmes lors des `scanf` suivants. `viderBuffer` résout ce problème.
*   **`int saisirNombre(int ordre)` (Améliorée)** :
    *   **Validation d'entrée** : Cette fonction est maintenant beaucoup plus robuste. Elle utilise une boucle `do-while` et la valeur de retour de `scanf` (`saisie_valide`). `scanf` retourne le nombre d'éléments qu'il a réussi à lire. Si l'utilisateur entre du texte au lieu d'un entier, `scanf` retourne `0`. La boucle redemande la saisie tant que l'entrée n'est pas un entier valide.
    *   **Messages personnalisés** : Un tableau `const char *suffixes[]` est utilisé pour stocker les suffixes ("1er", "2ème", "3ème"). Cela rend le code plus propre et plus facile à maintenir que d'utiliser des `if/else` pour chaque ordre.
*   **`float calculerMoyenne(int somme, int nombreDeValeurs)` (Améliorée)** :
    *   **Protection contre la division par zéro** : Un `if (nombreDeValeurs == 0)` est ajouté. Si `nombreDeValeurs` est 0, la fonction retourne `0.0f` pour éviter une erreur de division par zéro qui ferait planter le programme.
*   **`void afficherResultat(float moyenne)` (Améliorée)** :
    *   **Messages personnalisés** : Des conditions `if-else if-else` sont ajoutées pour afficher des messages de feedback différents à l'utilisateur en fonction de la moyenne obtenue. Cela rend le programme plus interactif et engageant.
*   **`return EXIT_SUCCESS;`** : Dans `main`, `EXIT_SUCCESS` est utilisé pour indiquer une fin de programme normale.

Cette solution avancée démontre comment les fonctions peuvent être utilisées non seulement pour structurer le code, mais aussi pour encapsuler des logiques plus complexes comme la validation d'entrée et la gestion d'erreurs, rendant le programme plus fiable et convivial.