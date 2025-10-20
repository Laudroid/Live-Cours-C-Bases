
## **Thème 1 – Types et variables** (Exercices 1 à 5)

### **Exercice 1 – Bonjour le monde**

Écrire un programme qui affiche :

```
Bonjour, monde !
```

---

### **Exercice 2 – Affichage de variables**

Déclarer trois variables : un entier, un flottant et un caractère.
Les initialiser et les afficher à l’écran avec `printf()`.

---

### **Exercice 3 – Calcul simple**

Écrire un programme qui lit deux entiers `a` et `b` et affiche :

* leur somme
* leur différence
* leur produit
* et leur quotient (attention à la division entière !)

---

### **Exercice 4 – Conversion de température**

Lire une température en degrés Celsius et afficher son équivalent en Fahrenheit :

> °F = °C × 9 / 5 + 32

---

### **Exercice 5 – Aire d’un cercle**

Lire le rayon d’un cercle et afficher son aire.

> Aire = π × r²
> (Utiliser une constante `#define PI 3.14159`)

---

## **Thème 2 – Boucles et conditions** (Exercices 6 à 10)

### **Exercice 6 – Pair ou impair**

Lire un entier et afficher s’il est **pair** ou **impair**.

---

### **Exercice 7 – Plus grand de trois nombres**

Lire trois entiers et afficher le plus grand des trois.

---

### **Exercice 8 – Somme de 1 à N**

Lire un entier `N` et calculer la somme de tous les entiers de 1 à N à l’aide d’une **boucle for**.

---

### **Exercice 9 – Table de multiplication**

Lire un entier `n` et afficher sa **table de multiplication** (de 1 à 10).

Exemple pour `n = 3` :

```
3 x 1 = 3
3 x 2 = 6
...
3 x 10 = 30
```

---

### **Exercice 10 – Compte à rebours**

Afficher un **compte à rebours** de 10 à 0, puis afficher `"Décollage !"`.
(Utiliser une boucle `while`.)

---

## **Thème 3 – Tableaux** (Exercices 11 à 15)

### **Exercice 11 – Lecture et affichage**

Déclarer un tableau de 5 entiers.
Demander à l’utilisateur de saisir les 5 valeurs, puis les afficher à l’écran.

---

### **Exercice 12 – Moyenne**

Lire 5 notes (nombres réels) dans un tableau, puis afficher leur **moyenne**.

---

### **Exercice 13 – Plus grande valeur**

Lire 10 entiers dans un tableau et afficher la **plus grande valeur**.

---

### **Exercice 14 – Comptage d’occurrences**

Lire 10 entiers et demander ensuite un nombre `x`.
Afficher combien de fois `x` apparaît dans le tableau.

---

### **Exercice 15 – Inversion de tableau**

Lire 5 entiers dans un tableau, puis afficher les valeurs **dans l’ordre inverse**.

Exemple :
Entrée → `1 2 3 4 5`
Sortie → `5 4 3 2 1`

---

## **Thème 4 – Fonctions** (Exercices 16 à 20)

### **Exercice 16 – Fonction somme**

Écrire une fonction `int somme(int a, int b)` qui retourne la somme de deux entiers.
Tester la fonction dans le `main()`.

---

### **Exercice 17 – Valeur absolue**

Écrire une fonction `int valeurAbsolue(int n)` qui retourne la valeur absolue de `n`.
Exemples :
`-5 → 5`, `3 → 3`

---

### **Exercice 18 – Factorielle**

Écrire une fonction `int factorielle(int n)` qui calcule la **factorielle** de `n`.

> Exemple : 5! = 1 × 2 × 3 × 4 × 5 = 120

---

### **Exercice 19 – Échange de valeurs**

Écrire une fonction `void echanger(int *a, int *b)` qui échange les valeurs de deux entiers à l’aide de pointeurs.
Exemple :
Avant → a=2, b=5
Après → a=5, b=2

---

### **Exercice 20 – Vérification de nombre premier**

Écrire une fonction `int estPremier(int n)` qui retourne 1 si `n` est premier, sinon 0.
L’utiliser dans le `main()` pour afficher :

```
7 est un nombre premier
```

ou

```
9 n’est pas un nombre premier
```