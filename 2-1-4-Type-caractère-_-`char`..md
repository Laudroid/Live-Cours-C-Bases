# Séance 2 : Les Fondamentaux du C (4 heures)

## Partie 1 : Variables et Types de Données

### 4. Type caractère : `char`

---

## 1. Définition et utilité du type `char`

Le type `char` en langage C est conçu pour stocker un **caractère unique**. Il occupe typiquement 1 octet (8 bits), permettant de représenter 256 valeurs possibles (de 0 à 255 en non signé).

Même si `char` sert principalement à manipuler des caractères ASCII, sa nature intrinsèque est celle d'un petit entier, ce qui le rend parfois utilisé pour stocker des valeurs numériques très compactes.

---

## 2. Représentation en mémoire

- Un `char` peut être **signé** ou **non signé** selon le compilateur et la plateforme.
- La norme C ne définit pas explicitement la nature signée par défaut.
- Les caractères ASCII standards vont de 0 à 127.
- Au-delà, des codages comme ASCII étendu ou UTF-8 interviennent (indice au-delà du scope `char` simple).

---

## 3. Déclaration et initialisation

```c
char lettre = 'A';      // caractère seul dans des apostrophes
char code = 65;         // valeur ASCII entière équivalente à 'A'
```

Le caractère est toujours indiqué entre guillemets simples `'`.

---

## 4. Manipulation des caractères

- Les opérations arithmétiques sont autorisées (car `char` est un entier sous-jacent).
- On peut incrémenter ou décrémenter un `char`.
- Permet de parcourir facilement des alphabets ou codes ASCII.

---

## 5. Exemples pratiques

```c
#include <stdio.h>

int main() {
    char c1 = 'Z';
    char c2 = 90;           // code ASCII de 'Z'
    char c3 = c1 + 1;       // caractère suivant (ici '[')

    printf("c1 = %c\n", c1);
    printf("c2 = %c\n", c2);
    printf("c3 = %c\n", c3);

    return 0;
}
```

**Sortie :**
```
c1 = Z
c2 = Z
c3 = [
```

---

## 6. Diagramme Mermaid : représentation simple du type `char`

```mermaid
graph LR
    A[char (1 octet)] --> B[Valeur entière: 0 à 255]
    A --> C[Caractère ASCII]
    B --> D[Opérations arithmétiques]
    C --> E[Stocke un symbole unique]
```

---

## 7. Particularités et bonnes pratiques

- Pour manipuler des chaînes de caractères, `char` est utilisé dans des **tableaux terminés par '\0'** (caractère nul).
- Utiliser correctement les conversions entre `char` et `int` évite les erreurs liées au signe.
- Pour des caractères Unicode plus complexes, il faut envisager d’autres types ou bibliothèques spécifiques.
- Toujours initialiser les variables `char` avant usage.

---

## 8. Sources utilisées

- cppreference.com - [char type](https://en.cppreference.com/w/c/language/char)  
- ISO/IEC 9899:2018 – Langage C standard (section sur les types de base)  
- TutorialsPoint - [C Char Data Type](https://www.tutorialspoint.com/cprogramming/c_data_types.htm)  
- Stack Overflow - [Is char signed or unsigned in C?](https://stackoverflow.com/questions/2609689/is-char-signed-or-unsigned-in-c)  

---

Le type `char` forme la base de la manipulation des symboles en C. Sa compréhension, tant comme caractère qu’entier compact, est fondamentale pour toute gestion à bas niveau des données textuelles.