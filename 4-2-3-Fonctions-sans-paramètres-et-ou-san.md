# Séance 4 : Fonctions et Modularité (4 heures)

## Partie 2 : Passage d'Arguments et Valeurs de Retour

### 3. Fonctions sans paramètres et/ou sans valeur de retour (`void`)

---

## 1. Introduction au type `void`

- Le mot-clé `void` en C signifie **absence de type** ou **absence de valeur**.
- Utilisé pour indiquer qu'une fonction **ne retourne aucune valeur** ou qu'elle **ne prend pas de paramètres**.

---

## 2. Fonctions sans paramètres

### 2.1 Syntaxe

```c
void fonctionSansParam(void) {
    // code de la fonction
}
```

- Le `(void)` indique explicitement que la fonction ne prend **aucun argument**.
- Ceci contraste avec une liste vide `()`, qui en C anciennnement laissait entendre une liste de paramètres inconnue, mais désormais `(void)` est recommandé.

### 2.2 Exemple

```c
#include <stdio.h>

void afficherBonjour(void) {
    printf("Bonjour!\n");
}

int main() {
    afficherBonjour();
    return 0;
}
```

- Appeler `afficherBonjour()` ne nécessite aucun argument.
- Le `(void)` dans la déclaration rend explicite l'absence de paramètres.

---

## 3. Fonctions sans valeur de retour (`void`)

### 3.1 Syntaxe

```c
void fonctionSansRetour(int param) {
    // traitement sans retour
}
```

- La fonction effectue des opérations mais **ne retourne rien** à son appelant.
- Utilisation typique pour des actions d'affichage, modification via pointeurs, ou manipulation d’I/O.

### 3.2 Exemple

```c
#include <stdio.h>

void afficherValeur(int n) {
    printf("La valeur est %d\n", n);
}

int main() {
    afficherValeur(10);
    return 0;
}
```

---

## 4. Fonctions sans paramètres et sans valeur de retour

- Combinaison des deux cas : la fonction ne reçoit aucune entrée et ne retourne aucune sortie.

### Exemple

```c
#include <stdio.h>

void afficherMessage(void) {
    printf("Message fixe\n");
}

int main() {
    afficherMessage();
    return 0;
}
```

---

## 5. Diagramme Mermaid : fonctions avec ou sans paramètres/valeur de retour

```mermaid
graph TD
    A[Début fonction] --> B{Paramètres ?}
    B -- Oui --> C[Reçoit des paramètres]
    B -- Non --> D[Pas de paramètres (void)]
    C --> E{Valeur de retour ?}
    D --> E
    E -- Oui --> F[Retourne une valeur]
    E -- Non --> G[Ne retourne rien (void)]
    F --> H[Fin fonction]
    G --> H
```

---

## 6. Récapitulatif

| Fonction                         | Syntaxe                           | Usage typique                   |
|---------------------------------|---------------------------------|--------------------------------|
| Avec paramètres et retour        | `int f(int x)`                  | Calculs, transformations        |
| Sans paramètres, avec retour     | `int f(void)`                   | Renvoi constantes ou infos      |
| Avec paramètres, sans retour     | `void f(int x)`                 | Actions sans résultat attendu   |
| Sans paramètres, sans retour     | `void f(void)`                  | Tâches fixes, affichages, alertes |

---

## 7. Sources utilisées

- [cppreference.com - `void` in functions](https://en.cppreference.com/w/c/language/function)  
- [GeeksforGeeks - Void Functions in C](https://www.geeksforgeeks.org/void-functions-in-c/)  
- [TutorialsPoint - C Void Functions](https://www.tutorialspoint.com/cprogramming/c_void_functions.htm)  
- ISO/IEC 9899:2018 (C18) – Chapitre 6.7

---

Utiliser les fonctions sans paramètres et/ou sans valeur de retour contribue à structurer clairement les responsabilités dans un programme : exécuter une action sans nécessiter d'entrées ou sans renvoyer de résultat. Cela simplifie l'interface fonctionnelle selon le besoin.