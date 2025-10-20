# Séance 2 : Les Fondamentaux du C (4 heures)

## Partie 3 : Entrées et Sorties Standard

### 3. Gestion des retours de `scanf()`

---

## 1. Le rôle du retour de `scanf()`

La fonction `scanf()` retourne un **entier** indiquant le nombre d’éléments qui ont été correctement lus et affectés aux variables fournies. Cette valeur permet de vérifier si la lecture s’est bien déroulée.

- En cas de succès total, le retour égale le nombre de spécificateurs de format dans la chaîne.
- En cas d’échec (ex : entrée incompatible), le retour est inférieur.
- En cas d'erreur critique (fin de fichier ou problème d'entrée), le retour peut être `EOF` (généralement -1).

---

## 2. Pourquoi gérer ce retour ?

- Éviter d’utiliser des données non valides (pouvant conduire à un comportement indéfini).
- Contrôler la validité de l’entrée utilisateur pour afficher un message d’erreur ou relancer la saisie.
- Assurer un programme robuste, capable de traiter les erreurs d’entrée.

---

## 3. Exemple simple de gestion du retour

```c
#include <stdio.h>

int main() {
    int age;
    printf("Entrez votre âge : ");

    int ret = scanf("%d", &age);

    if (ret == 1) {
        printf("Âge enregistré : %d\n", age);
    } else {
        printf("Erreur : entrée invalide.\n");
    }

    return 0;
}
```

**Explications :**

- `scanf("%d", &age)` doit lire un entier.
- Si `ret` vaut 1, la lecture a réussi.
- Sinon (par exemple, si l’utilisateur donne une lettre), on détecte l’erreur.

---

## 4. Gestion dans une boucle pour garantir une saisie valide

```c
#include <stdio.h>

int main() {
    int age;
    int ret;

    do {
        printf("Entrez votre âge : ");
        ret = scanf("%d", &age);

        if (ret != 1) {
            printf("Entrée invalide. Veuillez recommencer.\n");
            // Vider le buffer d'entrée pour supprimer la donnée incorrecte
            int c; 
            while ((c = getchar()) != '\n' && c != EOF);
        }
    } while (ret != 1);

    printf("Âge enregistré : %d\n", age);

    return 0;
}
```

**Points clés :**

- En cas d’échec, on vide le buffer d’entrée (`getchar()`) pour ne pas relire la même donnée erronée.
- La boucle continue jusqu’à obtention d’une lecture correcte.

---

## 5. Cas particulier : lecture multiple

```c
int a, b;
int ret = scanf("%d %d", &a, &b);

if (ret == 2) {
    printf("Vous avez saisi %d et %d\n", a, b);
} else {
    printf("Erreur lors de la saisie de deux entiers\n");
}
```

---

## 6. Diagramme Mermaid : gestion du retour `scanf()`

```mermaid
flowchart TD
    A[Appel de scanf()] --> B[Lecture des entrées selon format]
    B --> C{Nombre d'éléments lus == nombre attendu ?}
    C -->|Oui| D[Succès : utilisation des données]
    C -->|Non| E[Erreur : traiter saisie incorrecte]
    E --> F[Vider buffer d'entrée]
    F --> G[Demander de saisir de nouveau]
```

---

## 7. Bonnes pratiques

- Toujours tester la valeur de retour de `scanf()`.
- Nettoyer le buffer d’entrée après une erreur pour éviter la boucle infinie.
- Ne jamais supposer que `scanf()` lit parfaitement l’entrée utilisateur.
- Pour des interfaces plus complexes, envisager des méthodes de lecture sécurisées (`fgets`) et parsing manuel.

---

## 8. Sources utilisées

- cppreference.com - [scanf](https://en.cppreference.com/w/c/io/fscanf)  
- ISO/IEC 9899:2018 (C18 Standard) - Section 7.21.6.2  
- TutorialsPoint - [C - scanf() Function](https://www.tutorialspoint.com/c_standard_library/c_function_scanf.htm)  
- Learn-C.org - [Input/Output](https://www.learn-c.org/en/Input/Output)  

---

Gérer le retour de `scanf()` est la clé pour valider les données entrantes et garantir la fiabilité de la lecture, un élément indispensable pour tout programme interactif écrit en C.