Voici deux solutions possibles pour le TP "Création et Utilisation d'une Fonction Simple en C", présentées sous forme de chapitres distincts.

---

### **Chapitre 1 : Solution Basique - Carré et Hypoténuse Directs**

Cette solution implémente la fonction `calculerCarre` et l'utilise pour le calcul du carré d'un nombre, puis pour le calcul de l'hypoténuse, en suivant les consignes de manière directe.





```c
#include <stdio.h> // Nécessaire pour les fonctions d'entrée/sortie (printf, scanf).
#include <math.h>  // Nécessaire pour la fonction sqrt (racine carrée).

// Déclaration (prototype) de la fonction calculerCarre.
// C'est une bonne pratique de déclarer les fonctions avant main si elles sont définies après.
int calculerCarre(int nombre);

int main() {
    int nombre_saisi; // Variable pour stocker le nombre entré par l'utilisateur.
    int resultat_carre; // Variable pour stocker le résultat du carré.

    // --- Partie 1 : Calcul du carré d'un nombre ---
    printf("Veuillez entrer un nombre entier : ");
    scanf("%d", &nombre_saisi);

    // Appel de la fonction calculerCarre avec le nombre saisi.
    // Le résultat retourné par la fonction est stocké dans resultat_carre.
    resultat_carre = calculerCarre(nombre_saisi);

    // Affiche le résultat.
    printf("Le carré de %d est : %d\n", nombre_saisi, resultat_carre);

    // --- Partie 2 : Calcul de l'hypoténuse ---
    int coteA, coteB; // Variables pour les longueurs des côtés du triangle.
    double carre_hypotenuse; // Variable pour stocker la somme des carrés (peut être grand).
    double hypotenuse;       // Variable pour stocker le résultat final de l'hypoténuse.

    printf("\n--- Calcul de l'hypoténuse ---\n");
    printf("Veuillez entrer la longueur du côté A : ");
    scanf("%d", &coteA);

    printf("Veuillez entrer la longueur du côté B : ");
    scanf("%d", &coteB);

    // Utilisation de la fonction calculerCarre pour obtenir les carrés des côtés.
    carre_hypotenuse = calculerCarre(coteA) + calculerCarre(coteB);

    // Calcul de la racine carrée de la somme des carrés.
    // La fonction sqrt() prend un double et retourne un double.
    hypotenuse = sqrt(carre_hypotenuse);

    // Affiche la longueur de l'hypoténuse.
    // "%.2f" formate l'affichage pour deux chiffres après la virgule.
    printf("L'hypoténuse du triangle est : %.2f\n", hypotenuse);

    return 0; // Indique que le programme s'est exécuté avec succès.
}

// Définition de la fonction calculerCarre.
// Elle prend un entier 'n' en paramètre.
// Elle retourne le produit de 'n' par lui-même.
int calculerCarre(int n) {
    return n * n;
}
```





**Explication de la Solution 1 :**

*   **`#include <stdio.h>` et `#include <math.h>`** : `stdio.h` est inclus pour les fonctions `printf` et `scanf`. `math.h` est inclus spécifiquement pour la fonction `sqrt()` (racine carrée).
*   **`int calculerCarre(int nombre);`** : C'est le **prototype de la fonction**. Il indique au compilateur qu'une fonction nommée `calculerCarre` existe, qu'elle prend un `int` en paramètre et qu'elle retourne un `int`. Il est placé avant `main` pour que `main` puisse l'appeler.
*   **`int main() { ... }`** : La fonction principale où l'exécution du programme commence.
*   **`printf("Veuillez entrer un nombre entier : ");` et `scanf("%d", &nombre_saisi);`** : Ces lignes demandent à l'utilisateur de saisir un nombre et le stockent dans `nombre_saisi`.
*   **`resultat_carre = calculerCarre(nombre_saisi);`** : C'est l'**appel de la fonction**. La valeur de `nombre_saisi` est passée en argument à `calculerCarre`. La valeur retournée par `calculerCarre` est ensuite assignée à `resultat_carre`.
*   **`printf("Le carré de %d est : %d\n", nombre_saisi, resultat_carre);`** : Affiche le résultat du calcul du carré.
*   **Calcul de l'hypoténuse** :
    *   `int coteA, coteB;` : Variables pour les côtés du triangle.
    *   `double carre_hypotenuse;` et `double hypotenuse;` : Ces variables sont de type `double` car la racine carrée peut produire un nombre à virgule flottante. Il est bon de stocker la somme des carrés dans un `double` aussi pour éviter des problèmes de conversion implicite avant `sqrt`.
    *   `carre_hypotenuse = calculerCarre(coteA) + calculerCarre(coteB);` : La fonction `calculerCarre` est réutilisée ici pour obtenir les carrés des deux côtés, puis leurs sommes sont calculées.
    *   `hypotenuse = sqrt(carre_hypotenuse);` : La fonction `sqrt()` de `math.h` est appelée pour calculer la racine carrée.
    *   `printf("L'hypoténuse du triangle est : %.2f\n", hypotenuse);` : Affiche l'hypoténuse. Le spécificateur `%.2f` formate le `double` pour afficher seulement deux chiffres après la virgule.
*   **`int calculerCarre(int n) { return n * n; }`** : C'est la **définition de la fonction**. Elle prend un paramètre `n` de type `int` et retourne le résultat de `n * n`.

---

### **Chapitre 2 : Solution Avancée - Robustesse et Fonctions pour l'Hypoténuse**

Cette solution améliore la précédente en ajoutant une validation d'entrée pour les nombres saisis et en encapsulant le calcul de l'hypoténuse dans une fonction dédiée, démontrant une meilleure modularité.





```c
#include <stdio.h> // Nécessaire pour printf, scanf, getchar.
#include <math.h>  // Nécessaire pour sqrt.
#include <stdlib.h> // Nécessaire pour EXIT_SUCCESS.

// Prototype de la fonction pour calculer le carré.
int calculerCarre(int nombre);

// Prototype de la fonction pour calculer l'hypoténuse.
// Elle prend deux doubles (pour les côtés) et retourne un double.
double calculerHypotenuse(double cote1, double cote2);

// Fonction utilitaire pour vider le buffer d'entrée.
void viderBuffer() {
    int c;
    while ((c = getchar()) != '\n' && c != EOF);
}

// Fonction pour lire un entier avec validation.
int lireEntierValide(const char *message) {
    int nombre;
    int saisie_valide;

    do {
        printf("%s", message);
        saisie_valide = scanf("%d", &nombre);
        viderBuffer(); // Vide le buffer après la saisie.

        if (saisie_valide != 1) {
            printf("Erreur : Veuillez entrer un nombre entier valide.\n");
        }
    } while (saisie_valide != 1);

    return nombre;
}

int main() {
    int nombre_saisi;
    int resultat_carre;

    // --- Partie 1 : Calcul du carré d'un nombre (avec validation) ---
    nombre_saisi = lireEntierValide("Veuillez entrer un nombre entier : ");
    resultat_carre = calculerCarre(nombre_saisi);
    printf("Le carré de %d est : %d\n", nombre_saisi, resultat_carre);

    // --- Partie 2 : Calcul de l'hypoténuse (avec validation et fonction dédiée) ---
    int coteA_int, coteB_int; // Lecture des côtés en int.
    double hypotenuse_resultat;

    printf("\n--- Calcul de l'hypoténuse ---\n");
    coteA_int = lireEntierValide("Veuillez entrer la longueur du côté A : ");
    coteB_int = lireEntierValide("Veuillez entrer la longueur du côté B : ");

    // Appel de la fonction calculerHypotenuse, en convertissant les int en double.
    hypotenuse_resultat = calculerHypotenuse((double)coteA_int, (double)coteB_int);

    printf("L'hypoténuse du triangle est : %.2f\n", hypotenuse_resultat);

    return EXIT_SUCCESS; // Utilisation de EXIT_SUCCESS pour indiquer le succès.
}

// Définition de la fonction calculerCarre.
int calculerCarre(int n) {
    return n * n;
}

// Définition de la fonction calculerHypotenuse.
// Elle prend deux côtés (double) et retourne l'hypoténuse (double).
double calculerHypotenuse(double cote1, double cote2) {
    // Utilise la fonction calculerCarre (qui prend un int) en castant les doubles en int.
    // Attention : cela tronque la partie décimale si les côtés étaient des doubles.
    // Pour une précision maximale, il faudrait une version de calculerCarre pour double.
    double somme_carres = (double)calculerCarre((int)cote1) + (double)calculerCarre((int)cote2);
    // Ou, plus directement et sans dépendre de calculerCarre(int):
    // double somme_carres = cote1 * cote1 + cote2 * cote2;
    return sqrt(somme_carres);
}
```





**Explication de la Solution 2 :**

*   **`#include <stdlib.h>`** : Inclus pour `EXIT_SUCCESS`, une constante standard pour indiquer que le programme s'est terminé avec succès, alternative à `return 0;`.
*   **`double calculerHypotenuse(double cote1, double cote2);`** : Un prototype pour une nouvelle fonction `calculerHypotenuse` est ajouté. Elle prend deux `double` en paramètres et retourne un `double`.
*   **`void viderBuffer() { ... }`** : La fonction `viderBuffer` est réutilisée pour nettoyer le buffer d'entrée.
*   **`int lireEntierValide(const char *message) { ... }`** : Une nouvelle fonction utilitaire est créée pour lire un entier de manière robuste. Elle affiche un message, tente de lire un entier avec `scanf`, vide le buffer, et redemande la saisie en boucle (`do-while`) tant que l'entrée n'est pas un entier valide. Cela rend le `main` plus propre et la lecture des entrées plus fiable.
*   **`nombre_saisi = lireEntierValide("Veuillez entrer un nombre entier : ");`** : Dans `main`, la lecture des nombres est maintenant déléguée à `lireEntierValide`, ce qui simplifie le code de `main`.
*   **`hypotenuse_resultat = calculerHypotenuse((double)coteA_int, (double)coteB_int);`** : Le calcul de l'hypoténuse est maintenant encapsulé dans sa propre fonction. Les `int` lus sont convertis en `double` (`(double)coteA_int`) avant d'être passés à `calculerHypotenuse` pour assurer la précision des calculs flottants.
*   **Définition de `calculerHypotenuse`** :
    *   `double somme_carres = (double)calculerCarre((int)cote1) + (double)calculerCarre((int)cote2);` : Ici, pour réutiliser `calculerCarre` qui attend un `int`, les `double` `cote1` et `cote2` sont temporairement convertis en `int` (`(int)cote1`). **Attention :** cela tronque la partie décimale. Si les côtés pouvaient être des nombres à virgule flottante, il serait préférable d'avoir une version de `calculerCarre` qui prend un `double` ou de calculer directement `cote1 * cote1 + cote2 * cote2` comme indiqué en commentaire. Cette solution montre la réutilisation mais souligne aussi les limites des conversions de type.
    *   `return sqrt(somme_carres);` : Retourne la racine carrée de la somme des carrés.
*   **`return EXIT_SUCCESS;`** : Utilisation de la constante `EXIT_SUCCESS` (définie dans `stdlib.h`) comme alternative plus sémantique à `return 0;`.

Cette solution avancée met en évidence l'importance de la modularité avec des fonctions dédiées, la robustesse grâce à la validation d'entrée, et la gestion des types de données pour des calculs précis.