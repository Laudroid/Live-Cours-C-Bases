# Séance 4 : Fonctions et Modularité (4 heures)

## Partie 1 : Introduction aux Fonctions

### 3. Déclaration (prototype) et définition de fonction

---

## 1. Différence entre déclaration et définition

En langage C, **déclaration** (ou prototype) et **définition** d’une fonction sont deux concepts distincts mais complémentaires.

- **Déclaration (prototype) :** informe le compilateur de l’existence d’une fonction, son nom, son type de retour et ses paramètres, sans fournir le corps.  
- **Définition :** fournit l’implémentation complète, avec le corps de la fonction.

---

### 1.1 Déclaration de fonction (Prototype)

- Se place généralement en début de fichier source, dans un fichier d’en-tête (`.h`), ou avant la fonction `main`.
- Permet au compilateur de vérifier les appels à la fonction même si la définition se trouve plus bas dans le code ou dans un autre fichier.
- Syntaxe :

```c
type_de_retour nom_de_fonction(type_param1, type_param2, ...);
```

**Exemple :**

```c
int addition(int a, int b);
```

---

### 1.2 Définition de la fonction

- Contient le corps complet, avec instructions.
- Place où le comportement de la fonction est réellement codé.
- Syntaxe :

```c
type_de_retour nom_de_fonction(type_param1 param1, type_param2 param2, ...) {
    // corps de la fonction
}
```

**Exemple :**

```c
int addition(int a, int b) {
    return a + b;
}
```

---

## 2. Exemple complet avec déclaration et définition séparées

```c
#include <stdio.h>

// Déclaration du prototype
int multiplication(int x, int y);

int main() {
    int resultat = multiplication(4, 5);
    printf("Résultat : %d\n", resultat);
    return 0;
}

// Définition de la fonction
int multiplication(int x, int y) {
    return x * y;
}
```

- La déclaration permet à `main()` d’appeler `multiplication()` avant la définition complète.
- Si on omet la déclaration et que la définition vient après `main()`, le compilateur signale une erreur.

---

## 3. Cas particulier : définition sans déclaration préalable

- Valide si la définition est placée avant la première utilisation.
- Exemple :

```c
#include <stdio.h>

int somme(int a, int b) {
    return a + b;
}

int main() {
    printf("%d\n", somme(3, 4));
    return 0;
}
```

---

## 4. Diagramme Mermaid : liens entre déclaration, définition et appel

```mermaid
flowchart LR
    A[Déclaration (prototype)]
    B[Définition (corps)]
    C[Appel de la fonction]
    C -->|utilise| A
    C -->|utilise| B
    A --> B
```

---

## 5. Conseils pratiques

- Toujours déclarer les fonctions avant leur premier appel pour une meilleure portabilité et lisibilité.
- Utiliser des fichiers d’en-tête (`.h`) pour stocker les prototypes et garantir la cohérence lors du développement multi-fichiers.
- Les prototypes facilitent la détection d’erreurs typographiques ou de mauvais paramètres durant la compilation.

---

## 6. Sources utilisées

- [cppreference.com - Function Declaration](https://en.cppreference.com/w/c/language/function)  
- [GeeksforGeeks - Function declaration and prototype in C](https://www.geeksforgeeks.org/function-declaration-definition-and-call-in-c/)  
- [TutorialsPoint - C Function Declaration & Definition](https://www.tutorialspoint.com/cprogramming/c_functions.htm)  
- ISO/IEC 9899:2018 (C18) – Section 6.7

---

Le prototype (déclaration) et la définition constituent la base de la gestion des fonctions en C, garantissant que le compilateur connaisse les détails nécessaires pour générer un code correct et éviter les erreurs d’appel durant la compilation.