
## **Thème 1 – Types et variables**

---

### **Exercice 1 – Bonjour le monde**

```c
#include <stdio.h>

int main() {
    printf("Bonjour, monde !\n");
    return 0;
}
```

---

### **Exercice 2 – Affichage de variables**

```c
#include <stdio.h>

int main() {
    int entier = 10;
    float reel = 3.14;
    char caractere = 'A';

    printf("Entier : %d\n", entier);
    printf("Flottant : %.2f\n", reel);
    printf("Caractère : %c\n", caractere);

    return 0;
}
```

---

### **Exercice 3 – Calcul simple**

```c
#include <stdio.h>

int main() {
    int a, b;
    printf("Entrez deux entiers : ");
    scanf("%d %d", &a, &b);

    printf("Somme : %d\n", a + b);
    printf("Différence : %d\n", a - b);
    printf("Produit : %d\n", a * b);
    if (b != 0)
        printf("Quotient : %d\n", a / b);
    else
        printf("Division impossible (b = 0)\n");

    return 0;
}
```

---

### **Exercice 4 – Conversion de température**

```c
#include <stdio.h>

int main() {
    float celsius, fahrenheit;
    printf("Entrez la température en °C : ");
    scanf("%f", &celsius);

    fahrenheit = celsius * 9 / 5 + 32;
    printf("%.2f °C = %.2f °F\n", celsius, fahrenheit);

    return 0;
}
```

---

### **Exercice 5 – Aire d’un cercle**

```c
#include <stdio.h>
#define PI 3.14159

int main() {
    float r, aire;
    printf("Entrez le rayon : ");
    scanf("%f", &r);

    aire = PI * r * r;
    printf("Aire du cercle : %.2f\n", aire);

    return 0;
}
```

---

## **Thème 2 – Boucles et conditions**

---

### **Exercice 6 – Pair ou impair**

```c
#include <stdio.h>

int main() {
    int n;
    printf("Entrez un entier : ");
    scanf("%d", &n);

    if (n % 2 == 0)
        printf("%d est pair.\n", n);
    else
        printf("%d est impair.\n", n);

    return 0;
}
```

---

### **Exercice 7 – Plus grand de trois nombres**

```c
#include <stdio.h>

int main() {
    int a, b, c;
    printf("Entrez trois entiers : ");
    scanf("%d %d %d", &a, &b, &c);

    int max = a;
    if (b > max) max = b;
    if (c > max) max = c;

    printf("Le plus grand est : %d\n", max);
    return 0;
}
```

---

### **Exercice 8 – Somme de 1 à N**

```c
#include <stdio.h>

int main() {
    int n, somme = 0;
    printf("Entrez N : ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++)
        somme += i;

    printf("Somme = %d\n", somme);
    return 0;
}
```

---

### **Exercice 9 – Table de multiplication**

```c
#include <stdio.h>

int main() {
    int n;
    printf("Entrez un nombre : ");
    scanf("%d", &n);

    for (int i = 1; i <= 10; i++)
        printf("%d x %d = %d\n", n, i, n * i);

    return 0;
}
```

---

### **Exercice 10 – Compte à rebours**

```c
#include <stdio.h>

int main() {
    int i = 10;
    while (i >= 0) {
        printf("%d\n", i);
        i--;
    }
    printf("Décollage !\n");
    return 0;
}
```

---

## **Thème 3 – Tableaux**

---

### **Exercice 11 – Lecture et affichage**

```c
#include <stdio.h>

int main() {
    int tab[5];
    for (int i = 0; i < 5; i++) {
        printf("Entrez la valeur %d : ", i + 1);
        scanf("%d", &tab[i]);
    }

    printf("Valeurs saisies : ");
    for (int i = 0; i < 5; i++)
        printf("%d ", tab[i]);
    printf("\n");

    return 0;
}
```

---

### **Exercice 12 – Moyenne**

```c
#include <stdio.h>

int main() {
    float notes[5], somme = 0;
    for (int i = 0; i < 5; i++) {
        printf("Note %d : ", i + 1);
        scanf("%f", &notes[i]);
        somme += notes[i];
    }
    printf("Moyenne = %.2f\n", somme / 5);
    return 0;
}
```

---

### **Exercice 13 – Plus grande valeur**

```c
#include <stdio.h>

int main() {
    int tab[10], max;
    for (int i = 0; i < 10; i++) {
        printf("Valeur %d : ", i + 1);
        scanf("%d", &tab[i]);
    }

    max = tab[0];
    for (int i = 1; i < 10; i++)
        if (tab[i] > max)
            max = tab[i];

    printf("Plus grande valeur : %d\n", max);
    return 0;
}
```

---

### **Exercice 14 – Comptage d’occurrences**

```c
#include <stdio.h>

int main() {
    int tab[10], x, count = 0;
    for (int i = 0; i < 10; i++) {
        printf("Valeur %d : ", i + 1);
        scanf("%d", &tab[i]);
    }

    printf("Entrez le nombre à chercher : ");
    scanf("%d", &x);

    for (int i = 0; i < 10; i++)
        if (tab[i] == x)
            count++;

    printf("%d apparaît %d fois.\n", x, count);
    return 0;
}
```

---

### **Exercice 15 – Inversion de tableau**

```c
#include <stdio.h>

int main() {
    int tab[5];
    for (int i = 0; i < 5; i++) {
        printf("Valeur %d : ", i + 1);
        scanf("%d", &tab[i]);
    }

    printf("Tableau inversé : ");
    for (int i = 4; i >= 0; i--)
        printf("%d ", tab[i]);
    printf("\n");

    return 0;
}
```

---

## **Thème 4 – Fonctions**

---

### **Exercice 16 – Fonction somme**

```c
#include <stdio.h>

int somme(int a, int b) {
    return a + b;
}

int main() {
    int x, y;
    printf("Entrez deux nombres : ");
    scanf("%d %d", &x, &y);
    printf("Somme = %d\n", somme(x, y));
    return 0;
}
```

---

### **Exercice 17 – Valeur absolue**

```c
#include <stdio.h>

int valeurAbsolue(int n) {
    return (n < 0) ? -n : n;
}

int main() {
    int n;
    printf("Entrez un nombre : ");
    scanf("%d", &n);
    printf("Valeur absolue : %d\n", valeurAbsolue(n));
    return 0;
}
```

---

### **Exercice 18 – Factorielle**

```c
#include <stdio.h>

int factorielle(int n) {
    int f = 1;
    for (int i = 1; i <= n; i++)
        f *= i;
    return f;
}

int main() {
    int n;
    printf("Entrez un nombre : ");
    scanf("%d", &n);
    printf("%d! = %d\n", n, factorielle(n));
    return 0;
}
```

---

### **Exercice 19 – Échange de valeurs**

```c
#include <stdio.h>

void echanger(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x = 2, y = 5;
    printf("Avant échange : x=%d, y=%d\n", x, y);
    echanger(&x, &y);
    printf("Après échange : x=%d, y=%d\n", x, y);
    return 0;
}
```

---

### **Exercice 20 – Vérification de nombre premier**

```c
#include <stdio.h>

int estPremier(int n) {
    if (n < 2) return 0;
    for (int i = 2; i * i <= n; i++)
        if (n % i == 0)
            return 0;
    return 1;
}

int main() {
    int n;
    printf("Entrez un nombre : ");
    scanf("%d", &n);

    if (estPremier(n))
        printf("%d est un nombre premier.\n", n);
    else
        printf("%d n'est pas un nombre premier.\n", n);

    return 0;
}
```
