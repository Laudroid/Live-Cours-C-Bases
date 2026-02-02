Voici deux solutions possibles pour le TP "Boucles en C - Répéter l'Action, Maîtriser le Flux", présentées sous forme de chapitres distincts.

---

### **Chapitre 1 : Solutions Basiques - Compteur `for` et Somme `while`**

Ce chapitre présente les solutions directes aux deux exercices principaux, en se concentrant sur l'utilisation correcte des boucles `for` et `while` selon les consignes.

#### **Exercice 1 : Le Compteur Simple (`for`)**

Ce programme utilise une boucle `for` pour afficher les nombres de 1 à 10.


```c
#include <stdio.h> // Inclut la bibliothèque standard d'entrée/sortie, nécessaire pour printf.

int main() {
    int i; // Déclare une variable entière 'i' qui servira de compteur.

    // Boucle for :
    // 1. Initialisation : i = 1 (le compteur commence à 1).
    // 2. Condition : i <= 10 (la boucle continue tant que i est inférieur ou égal à 10).
    // 3. Incrémentation : i++ (i est incrémenté de 1 à chaque fin d'itération).
    for (i = 1; i <= 10; i++) {
        // Affiche la valeur actuelle de i, suivie d'un retour à la ligne.
        printf("%d\n", i);
    }

    return 0; // Indique que le programme s'est exécuté avec succès.
}
```


**Explication de l'Exercice 1 :**

*   **`#include <stdio.h>`** : Cette ligne inclut la bibliothèque standard d'entrée/sortie, indispensable pour utiliser la fonction `printf`.
*   **`int main() { ... }`** : C'est le point d'entrée de tout programme C.
*   **`int i;`** : Déclare une variable entière `i`. C'est une convention courante d'utiliser `i` (pour "index" ou "itération") comme variable de compteur dans les boucles.
*   **`for (i = 1; i <= 10; i++) { ... }`** : C'est la boucle `for`. Elle est composée de trois parties séparées par des points-virgules :
    1.  **`i = 1`** (Initialisation) : Cette partie est exécutée une seule fois au début de la boucle. Elle initialise le compteur `i` à 1.
    2.  **`i <= 10`** (Condition) : Cette partie est évaluée avant chaque itération. Si la condition est vraie, le corps de la boucle est exécuté. Si elle est fausse, la boucle se termine.
    3.  **`i++`** (Incrémentation) : Cette partie est exécutée après chaque itération du corps de la boucle. Elle incrémente `i` de 1 (équivalent à `i = i + 1`).
*   **`printf("%d\n", i);`** : À chaque tour de boucle, cette ligne affiche la valeur actuelle de `i` (`%d` est le spécificateur de format pour un entier) suivie d'un retour à la ligne (`\n`).

#### **Exercice 2 : La Calculatrice de Somme Interactive (`while`)**

Ce programme utilise une boucle `while` pour additionner des nombres saisis par l'utilisateur jusqu'à ce que 0 soit entré.


```c
#include <stdio.h> // Inclut la bibliothèque standard d'entrée/sortie.

int main() {
    int somme = 0;   // Variable pour stocker la somme totale, initialisée à 0.
    int nombre;      // Variable pour stocker le nombre saisi par l'utilisateur.

    // Demande une première fois à l'utilisateur de saisir un nombre.
    // Cette saisie est cruciale pour initialiser la condition de la boucle while.
    printf("Entrez un nombre (0 pour terminer) : ");
    scanf("%d", &nombre);

    // Boucle while : continue tant que le nombre saisi n'est PAS 0.
    while (nombre != 0) {
        somme = somme + nombre; // Ajoute le nombre saisi à la somme totale.

        // Demande à nouveau à l'utilisateur de saisir un nombre.
        // Cette nouvelle saisie sera utilisée pour la prochaine évaluation de la condition de la boucle.
        printf("Entrez un nombre (0 pour terminer) : ");
        scanf("%d", &nombre);
    }

    // Une fois que la boucle se termine (nombre est 0), affiche la somme totale.
    printf("La somme des nombres saisis est : %d\n", somme);

    return 0; // Indique que le programme s'est exécuté avec succès.
}
```


**Explication de l'Exercice 2 :**

*   **`int somme = 0;`** : Déclare et initialise la variable `somme` à 0. C'est important car nous allons y ajouter les nombres saisis.
*   **`int nombre;`** : Déclare la variable `nombre` qui stockera chaque nombre entré par l'utilisateur.
*   **Première `printf` et `scanf`** : Avant d'entrer dans la boucle `while`, il est nécessaire de demander une première fois un nombre. C'est cette valeur qui sera utilisée pour la première évaluation de la condition `nombre != 0`. Sans cette première lecture, la variable `nombre` aurait une valeur indéterminée, ce qui pourrait entraîner un comportement imprévisible de la boucle.
*   **`while (nombre != 0) { ... }`** : C'est la boucle `while`. Elle continue d'exécuter le bloc de code entre accolades tant que la condition `nombre != 0` (nombre est différent de 0) est vraie. Dès que `nombre` devient 0, la condition est fausse et la boucle se termine.
*   **`somme = somme + nombre;`** : À chaque itération, le nombre actuellement stocké dans `nombre` est ajouté à la `somme` cumulée.
*   **Deuxième `printf` et `scanf` dans la boucle** : Après avoir ajouté le nombre à la somme, le programme demande un nouveau nombre. Cette nouvelle valeur sera utilisée pour la *prochaine* évaluation de la condition `while`. C'est le mécanisme qui permet à l'utilisateur de contrôler la fin de la boucle en entrant 0.
*   **`printf("La somme des nombres saisis est : %d\n", somme);`** : Une fois la boucle terminée, le programme affiche le résultat final. Le 0 qui a mis fin à la boucle n'est pas inclus dans la somme car il n'est pas ajouté avant que la condition ne soit réévaluée.

---

### **Chapitre 2 : Solutions Avancées - Extensions et Robustesse**

Ce chapitre propose des solutions qui intègrent les défis "pour aller plus loin", ajoutant des fonctionnalités et améliorant la robustesse des programmes.

#### **Exercice 1 : Le Compteur Avancé (`for`)**

Ce programme combine les défis optionnels : afficher les nombres pairs de 1 à 20, puis les nombres de 10 à 1.


```c
#include <stdio.h> // Inclut la bibliothèque standard d'entrée/sortie.

int main() {
    int i; // Compteur de boucle.

    printf("--- Nombres pairs de 1 à 20 ---\n");
    // Boucle pour les nombres pairs de 1 à 20.
    // L'initialisation commence à 2 (premier nombre pair).
    // L'incrémentation est de 2 (i += 2) pour passer directement au nombre pair suivant.
    for (i = 2; i <= 20; i += 2) {
        printf("%d\n", i);
    }

    printf("\n--- Nombres de 10 à 1 (décroissant) ---\n");
    // Boucle pour les nombres de 10 à 1 en ordre décroissant.
    // L'initialisation commence à 10.
    // La condition est i >= 1 (la boucle continue tant que i est supérieur ou égal à 1).
    // La décrémentation est i-- (i est décrémenté de 1 à chaque fin d'itération).
    for (i = 10; i >= 1; i--) {
        printf("%d\n", i);
    }

    return 0; // Indique que le programme s'est exécuté avec succès.
}
```


**Explication de l'Exercice 1 Avancé :**

*   **Nombres pairs de 1 à 20** :
    *   `for (i = 2; i <= 20; i += 2)` : La boucle est initialisée à `i = 2` (le premier nombre pair). La condition `i <= 20` assure que nous allons jusqu'à 20. L'incrémentation `i += 2` (équivalent à `i = i + 2`) fait avancer le compteur de deux en deux, garantissant que seuls les nombres pairs sont traités.
*   **Nombres de 10 à 1 (décroissant)** :
    *   `for (i = 10; i >= 1; i--)` : Ici, la boucle est initialisée à `i = 10`. La condition `i >= 1` maintient la boucle tant que `i` est supérieur ou égal à 1. L'incrémentation est remplacée par une décrémentation `i--` (équivalent à `i = i - 1`) pour compter à rebours.

#### **Exercice 2 : La Calculatrice de Somme Avancée (`while`)**

Ce programme calcule la somme, la moyenne et le compte des nombres saisis, avec une gestion du buffer d'entrée.


```c
#include <stdio.h> // Inclut la bibliothèque standard d'entrée/sortie.

// Fonction pour vider le buffer d'entrée.
// Utile après scanf pour éviter que le caractère '\n' ne soit lu par les scanf suivants.
void viderBuffer() {
    int c;
    while ((c = getchar()) != '\n' && c != EOF);
}

int main() {
    int somme = 0;         // Somme des nombres.
    int nombre;            // Nombre saisi par l'utilisateur.
    int count = 0;         // Compteur de nombres saisis (différents de 0).
    double moyenne = 0.0;  // Moyenne des nombres. Utilisation de double pour une meilleure précision.
    int saisie_valide;     // Pour la validation de l'entrée.

    printf("--- Calculatrice de Somme et Moyenne ---\n");
    printf("Entrez des nombres entiers (0 pour terminer).\n");

    // Boucle do-while pour s'assurer qu'au moins une saisie est tentée.
    do {
        // Boucle interne pour la validation de l'entrée.
        do {
            printf("Entrez un nombre : ");
            saisie_valide = scanf("%d", &nombre); // Tente de lire un entier.
            viderBuffer(); // Vide le buffer après la saisie.

            if (saisie_valide != 1) { // Si la saisie n'est pas un entier valide.
                printf("Erreur : Veuillez entrer un nombre entier valide.\n");
            }
        } while (saisie_valide != 1); // Répète tant que la saisie n'est pas valide.

        if (nombre != 0) { // Si le nombre n'est pas 0 (le terminateur).
            somme += nombre; // Ajoute le nombre à la somme (équivalent à somme = somme + nombre).
            count++;         // Incrémente le compteur de nombres.
        }

    } while (nombre != 0); // La boucle principale continue tant que l'utilisateur n'entre pas 0.

    printf("\n--- Résultats ---\n");
    printf("La somme des nombres saisis est : %d\n", somme);
    printf("Nombre de valeurs saisies (hors 0) : %d\n", count);

    if (count > 0) { // Évite la division par zéro si aucun nombre n'a été saisi.
        moyenne = (double)somme / count; // Calcule la moyenne. (double) force la division flottante.
        printf("La moyenne des nombres saisis est : %.2f\n", moyenne); // %.2f pour 2 décimales.
    } else {
        printf("Aucun nombre valide n'a été saisi pour calculer une moyenne.\n");
    }

    return 0; // Indique que le programme s'est exécuté avec succès.
}
```


**Explication de l'Exercice 2 Avancé :**

*   **`void viderBuffer() { ... }`** : Cette fonction est réutilisée pour garantir que le buffer d'entrée est propre après chaque `scanf`, ce qui est essentiel pour la robustesse, surtout avec la validation d'entrée.
*   **`int count = 0;`** : Une nouvelle variable `count` est ajoutée pour suivre le nombre de valeurs différentes de 0 saisies par l'utilisateur.
*   **`double moyenne = 0.0;`** : La variable `moyenne` est déclarée comme un `double` pour stocker un nombre à virgule flottante, ce qui est nécessaire pour une moyenne précise.
*   **`int saisie_valide;`** : Utilisée pour vérifier la valeur de retour de `scanf` et valider que l'utilisateur a bien entré un entier.
*   **Boucle `do-while` externe** : La structure `do-while` est utilisée pour la boucle principale. Cela garantit que le programme demande au moins une fois un nombre.
*   **Boucle `do-while` interne pour la validation** : Une boucle `do-while` imbriquée est utilisée pour valider l'entrée de chaque nombre. Si `scanf` ne lit pas un entier (`saisie_valide != 1`), un message d'erreur est affiché et la saisie est redemandée.
*   **`if (nombre != 0) { ... }`** : Le nombre n'est ajouté à la `somme` et le `count` n'est incrémenté que si le nombre saisi n'est pas 0 (le signal de terminaison).
*   **Calcul de la moyenne** :
    *   **`if (count > 0) { ... }`** : Une vérification est faite pour s'assurer que `count` est supérieur à 0 avant de calculer la moyenne. Cela évite une division par zéro si l'utilisateur entre 0 dès la première saisie.
    *   **`moyenne = (double)somme / count;`** : Le `(double)` devant `somme` est un "cast". Il force la variable `somme` à être traitée comme un `double` avant la division. Sans cela, la division `somme / count` serait une division entière (tronquant la partie décimale), même si `moyenne` est un `double`.
    *   **`printf("La moyenne des nombres saisis est : %.2f\n", moyenne);`** : `%f` est le spécificateur de format pour un `double`. `%.2f` formate l'affichage pour n'avoir que deux chiffres après la virgule.

Ces solutions avancées démontrent comment construire des programmes plus robustes et fonctionnels en combinant les boucles avec la validation d'entrée et des calculs supplémentaires.