# Séance 2 : Les Fondamentaux du C (4 heures)

## Partie 3 : Entrées et Sorties Standard

### 1. `printf()` : formatage de sortie (`%d`, `%f`, `%c`, `%s`)

---

## 1. Présentation de `printf()`

`printf()` est une fonction standard du langage C (définie dans `<stdio.h>`) utilisée pour afficher des données formatées sur la sortie standard, généralement la console.

Son prototype principal est :

```c
int printf(const char *format, ...);
```

- `format` : chaîne de caractères spécifiant le format de sortie, pouvant contenir du texte brut et des spécificateurs de format.
- `...` : liste variable d’arguments correspondant aux spécificateurs.

---

## 2. Spécificateurs de format courants

| Spécificateur | Type de données attendu       | Description                            | Exemple                     |
|---------------|-------------------------------|--------------------------------------|-----------------------------|
| `%d`          | `int`                         | Affiche un entier en base décimale   | `printf("%d", 42);`         |
| `%f`          | `float` ou `double`           | Affiche un nombre à virgule flottante| `printf("%f", 3.14);`       |
| `%c`          | `char`                        | Affiche un caractère unique           | `printf("%c", 'A');`        |
| `%s`          | `char *` (chaîne de caractères)| Affiche une chaîne de caractères     | `printf("%s", "Bonjour");`  |

---

## 3. Fonctionnement basique

- Les spécificateurs indiquent à `printf` comment interpréter les arguments correspondants.
- L'ordre des arguments après le format doit correspondre strictement aux spécificateurs.
- Le retour de la fonction est le nombre de caractères affichés (utile pour vérifier l'affichage).

---

## 4. Exemples illustratifs

```c
#include <stdio.h>

int main() {
    int age = 25;
    float taille = 1.75;
    char initiale = 'J';
    char nom[] = "Dupont";

    printf("Nom: %s\n", nom);
    printf("Initiale: %c\n", initiale);
    printf("Âge: %d ans\n", age);
    printf("Taille: %f mètres\n", taille);

    return 0;
}
```

**Sortie attendue :**

```
Nom: Dupont
Initiale: J
Âge: 25 ans
Taille: 1.750000 mètres
```

---

## 5. Contrôle de l’affichage des nombres à virgule flottante

Par défaut `%f` affiche 6 chiffres après la virgule. Pour spécifier le nombre de décimales, utilisez la syntaxe `%.nf` où `n` est un nombre entier.

```c
printf("Taille avec 2 décimales: %.2f mètres\n", taille);
```

Sortie :

```
Taille avec 2 décimales: 1.75 mètres
```

---

## 6. Séquence d’échappement communes

- `\n` : saut de ligne
- `\t` : tabulation horizontale
- `\\` : antislash littéral
- `\"` : guillemet double littéral

---

## 7. Diagramme Mermaid : fonctionnement de `printf()`

```mermaid
flowchart TD
    A[Appel de printf()] --> B[Analyse de la chaîne de format]
    B --> C{Trouve un spécificateur ?}
    C -->|Oui| D[Lire l’argument correspondant]
    D --> E[Convertir l’argument selon le spécificateur]
    E --> F[Écrire dans la sortie standard]
    C -->|Non| F
    F --> G[Continuer jusqu'à fin de chaîne]
    G --> H[Retourner le nombre de caractères affichés]
```

---

## 8. Bonnes pratiques

- Toujours vérifier le type des arguments et leur correspondance exacte avec les spécificateurs pour éviter des comportements indéfinis.
- Utiliser la précision lorsque nécessaire pour contrôler l’affichage des flottants.
- Pour afficher d’autres types (hexadécimal `%x`, octal `%o`, pointeurs `%p`, etc.), se référer à la documentation.
- Privilégier les chaînes formatées dans des buffers sécurisés (ex : `snprintf`) dans du code plus avancé pour éviter les risques d’erreur.

---

## 9. Sources utilisées

- cppreference.com - [printf](https://en.cppreference.com/w/c/io/fprintf)  
- ISO/IEC 9899:2018 (C18 Standard) - Chapitre 7.21.6.1  
- TutorialsPoint - [C - printf() Function](https://www.tutorialspoint.com/c_standard_library/c_function_printf.htm)  
- GNU GCC Documentation - [printf Format](https://gcc.gnu.org/onlinedocs/libstdc++/manual/io.html)  

---

La fonction `printf` est une des principales interfaces de sortie en C, permettant par son système de formatage puissant d’afficher aussi bien du texte simple que des données diverses en formats contrôlés, facilitant le débogage et l’interaction utilisateur.