# Séance 1 : Introduction au Langage C et Environnement de Développement (3 heures)

## Partie 4 : Commentaires et Bonnes Pratiques

### 1. L’importance des commentaires (`//` et `/* */`)

---

Les commentaires sont des blocs ou des lignes de texte dans le code source qui ne sont pas exécutées par le compilateur. Ils servent à documenter le code, faciliter sa compréhension et son maintien dans le temps. En C, les commentaires peuvent être écrits de deux manières principales.

---

## 1.1 Types de commentaires en langage C

### Commentaires sur une seule ligne : `//`

- Introduits en C99, ils commencent avec `//` et s’étendent jusqu’à la fin de la ligne.
- Utiles pour des remarques brèves.

Exemple :

```c
int x = 5;  // Déclaration d'une variable entière x
```

---

### Commentaires multilignes : `/* ... */`

- Encadrent un bloc de texte, peuvent s’étendre sur plusieurs lignes.
- Utilisés pour des explications plus longues ou désactiver temporairement du code.

Exemple :

```c
/*
   Ce programme affiche un message de bienvenue
   et initialise une variable.
*/
int main() {
    printf("Bienvenue!\n");
    return 0;
}
```

---

## 1.2 Bonnes pratiques pour les commentaires

- **Soyez clairs et concis** : un commentaire doit apporter une valeur ajoutée sans répéter ce que le code fait déjà explicitement.
- **Expliquez le pourquoi, pas le comment** : préférez des commentaires qui expliquent la logique ou la raison d’un choix plutôt que la simple description de l’instruction.
- **Tenez-les à jour** : un commentaire obsolète peut être plus nuisible qu’utile.
- **Utilisez les commentaires pour structurer votre code** : séparer les sections, expliquer les étapes importantes.

---

## 1.3 Exemple illustré

```c
#include <stdio.h>

int main() {
    int compteur = 0;          // Initialisation du compteur à zéro
    
    /* Boucle qui s'exécute 10 fois */
    while (compteur < 10) {
        printf("Valeur : %d\n", compteur);
        compteur++;            // Incrémentation du compteur
    }
    
    return 0;                  // Fin normale du programme
}
```

---

## 1.4 Impact sur la compilation

- Le compilateur ignore complètement les commentaires.
- Les commentaires n’occupent pas d’espace en mémoire lors de l’exécution.

---

## 1.5 Diagramme Mermaid : Rôle des commentaires dans le cycle de vie du code

```mermaid
flowchart LR
    A[Écriture du code] --> B[Ajout des commentaires]
    B --> C[Compilation (commentaires ignorés)]
    C --> D[Exécutable]
    D --> E[Maintenance du code]
    E -->|Commentaires clairs| F[Facilite compréhension & modification]
    E -->|Commentaires absents ou obsolètes| G[Complexifie la maintenance]
```

---

## Sources utilisées

- ISO/IEC 9899:2018 – Langage C standard  
- cppreference.com - [Commentaires en C](https://en.cppreference.com/w/c/language/comments)  
- GNU GCC documentation - [Preprocessing and comments](https://gcc.gnu.org/onlinedocs/cpp/Preprocessor-Implementation.html)  
- TutorialsPoint - [C Comments](https://www.tutorialspoint.com/cprogramming/c_comments.htm)  

---

Les commentaires sont un outil indispensable pour un code lisible, partageable et maintenable. Une bonne utilisation améliore la collaboration et réduit le risque d’erreurs lors des évolutions ultérieures.