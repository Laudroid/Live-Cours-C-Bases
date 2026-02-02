Nom :
Prénom :


############################
######### PARTIE 1 #########
############################


## Questions

1. Que garantit exactement le standard C concernant la taille de `char` ?

   A. 1 bit

   B. 8 bits

   C. Au moins 8 bits

   D. Dépend de l’architecture

    Réponse :

2. Quelle expression provoque un comportement indéfini ?

   A. `i = i++;`

   B. `i += 1;`

   C. `++i;`

   D. `i = i + 1;`

    Réponse :

3. Que retourne `sizeof('A')` en C ?

   A. 1

   B. sizeof(char)

   C. sizeof(int)

   D. Erreur de compilation

    Réponse :

4. Quel est le type réel d’une constante chaîne "abc" ?

   A. char *

   B. const char *

   C. char[4]

   D. string

    Réponse :

5. Quelle déclaration est correcte ?

   A. `int *p, q;`

   B. `int (*p), q;`

   C. `int *p, *q;`

   D. B et C

    Réponse :

6. Quelle est la bonne façon de libérer de la mémoire allouée dynamiquement ?

   A) delete(ptr);

   B) free(ptr);

   C) release(ptr);

   D) ptr = NULL;

    Réponse :

7. Quel est le résultat de ce code ?

   ```c
   int a = 3, b = 2;
   int c = a > b ? a : b;
   printf("%d", c);
   ```

   A) 2

   B) 3

   C) 0

   D) 1

    Réponse :

8. Quel est le rôle de la fonction fgets() ?

    A) Lire dans un fichier

    B) Écrire dans un fichier

    C) Vider le tampon de sortie

    D) Fermer un fichier

    Réponse :

9. Quelle fonction est sûre face aux dépassements de tampon ?

   A. gets

   B. scanf("%s")

   C. fgets

   D. strcpy

    Réponse :

10. Quel est le résultat de ce code ?

    ```c
    int x = 10;
    int y = 20;
    int *p = &x;
    int *q = &y;
    *p = *q;
    printf("%d %d", x, y);
    ```

    A) 10 20

    B) 20 20

    C) 20 10

    D) 10 10

    Réponse :

11. Quel est le rôle de la fonction realloc() ?

    A) Libérer de la mémoire

    B) Réallouer de la mémoire avec une nouvelle taille

    C) Allouer de la mémoire initialisée à zéro

    D) Copier de la mémoire

    Réponse :

12. Quel est le type de `NULL` ?

    A. int

    B. void *

    C. macro dépendante

    D. char *

    Réponse :

13. Quel appel est incorrect ?

    A. free(p);

    B. free(NULL);

    C. free(&x);

    D. free(ptr_malloc);

    Réponse :

14. Quelle est la durée de vie d’une variable `static` locale ? <--- QUESTION ANNULEE

    A. Execution du Bloc

    B. Execution de la Fonction

    C. Execution du Programme

    D. Execution du Fichier

    Réponse :

15. Quelle est l’erreur dans ce code ?
    ```c
    int *p = malloc(10 * sizeof(int));
    int *q = p;
    free(p);
    free(q);
    ```

    A) Double free

    B) Fuite mémoire

    C) Accès après libération

    D) Mauvaise allocation

    Réponse :

16. Quel est le résultat de ce code ?

    ```c
    int a = 5;
    int b = (a++, a + a);
    printf("%d", b);
    ```

    A) 10

    B) 11

    C) 12

    D) 13

    Réponse :

17. Quelle est l’erreur dans ce code ?

    ```c
    int *p = malloc(sizeof(int));
    int *q = p;
    *p = 10;
    free(q);
    p = malloc(sizeof(int));
    *p = 20;
    ```

    A) Double free

    B) Fuite mémoire

    C) Accès après libération

    D) Aucune erreur

    Réponse :

18. Quel est le résultat de ce code ?

    ```c
    int a = 1;
    int b = 0;
    int c = a && b++;
    printf("%d %d %d", a, b, c);
    ```

    A) 1 0 0

    B) 1 1 0

    C) 1 0 1

    D) 0 1 0

    Réponse :

19. Quel est le résultat de `printf("%zu", sizeof(void*))` ?

    A. Taille inconnue

    B. Erreur

    C. Taille d’un pointeur

    D. 0

    Réponse :

20. Quelle est la bonne façon de déclarer un pointeur vers une fonction prenant un int et retournant un int ?

    A) int (*f)(int);

    B) int *f(int);

    C) int f(int*);

    D) int (*f)(int*);

    Réponse :

21. Quel est le problème ici ?

```c
int f() { return f(); }
```

A. Aucun problème

B. Stack overflow

C. Erreur compilation

D. Warning seulement

    Réponse :

22. Quelle est l’erreur dans ce code ?

    ```c
    int *p = malloc(10 * sizeof(int));
    p[10] = 0;
    ```

    A) Accès hors limites

    B) Fuite mémoire

    C) Warning seulement

    D) Mauvaise allocation

    Réponse :

23. Quel est le résultat de ce code ?

    ```c
    int a = 5;
    int b = (a = 3, a + 1);
    printf("%d", b);
    ```

    A) 3

    B) 4

    C) 5

    D) 6

    Réponse :

24. Quelle est la bonne façon de déclarer une énumération en C ?

    A) union { int a; float b; };

    B) struct { int a; float b; };

    C) enum { int a; float b; };

    D) Aucune bonne réponse

    Réponse :

25. Quel est le résultat de ce code ?

    ```c
    int a = 1;
    int b = (a++, a + a++, a);
    printf("%d", b);
    ```

    A) 1

    B) 2

    C) 3

    D) Comportement indéfini

    Réponse :

26. Quelle est la bonne façon de déclarer un pointeur vers un tableau de 10 entiers ?

    A) int (*p)[10];

    B) int *p[10];

    C) int p[10];

    D) int (*p)(10);

    Réponse :

27. Quelle est l’erreur dans ce code ?

    ```c
    int *p = malloc(sizeof(int));
    free(p);
    p = NULL;
    free(p);
    ```

    A) Double free

    B) Fuite mémoire

    C) Accès après libération

    D) Aucune erreur

    Réponse :

28. Quel est le résultat de ce code ?

    ```c
    int a = 1;
    int b = 0;
    int c = a || b++;
    printf("%d %d %d", a, b, c);
    ```

    A) 1 0 1

    B) 1 1 1

    C) 1 0 0

    D) 0 1 0

    Réponse :

29. Quelle est la bonne façon de déclarer un pointeur vers une fonction prenant un void* et retournant un void* ?

    A) void* (*f)(void*);

    B) void* f(*void);

    C) void* (*f)(void);

    D) void* f(void*);

    Réponse :

30. Quelle est la valeur de `sizeof(struct empty {})` ?

    A. 0

    B. 1

    C. Erreur

    D. Indéfini

    Réponse :

31. Quelle est l’erreur dans ce code ?

    ```c
    int *p = malloc(10 * sizeof(int));
    int *q = realloc(p, 20 * sizeof(int));
    if (q == NULL) free(p);
    p = q;
    ```

    A) Double free

    B) Fuite mémoire

    C) Accès après libération

    D) Aucune erreur

    Réponse :

32. Quel est le résultat de ce code ?

    ```c
    int a = 1;
    int b = (a = a + 1, ++a + 1);
    printf("%d", b);
    ```

    A) 1

    B) 2

    C) 3

    D) 4

    Réponse :

33. Quelle est la bonne façon de déclarer une structure contenant un pointeur vers elle-même ?

    A) struct Node { int data; struct Node* next; };

    B) struct Node { int data; Node* next; };

    C) struct Node { int data; struct Node next; };

    D) struct Node { int data; Node next; };

    Réponse :

34. Quel est le risque de double free ?

    A. Leak

    B. Crash / comportement indéfini

    C. Warning

    D. Rien

    Réponse :

35. Quelle est la principale difficulté du C ?

A. Syntaxe

B. Performance

C. Gestion mémoire

D. Portabilité

    Réponse :

36. Que garantit `fclose` ?

    A. Libération mémoire

    B. Flush buffer

    C. Fermeture FD

    D. Tout

    Réponse :

37. Quel est le rôle de `errno` ?

    A. Variable locale

    B. Code erreur global

    C. Exception

    D. Macro

    Réponse :

38. Que se passe-t-il si `realloc` échoue ?

    A. Mémoire libérée

    B. NULL et bloc intact

    C. Crash

    D. Rien

    Réponse :

39. Quel est le problème dans ce code ?

```c
int x = 5;
printf("%d %d", x++, x++);
```

A) Aucun

B) Ordre d’évaluation non défini

C) Erreur de compilation

D) Affiche toujours `5 6`

Réponse :

40. Quel est le problème dans ce code ?**

```c
char buf[10];
strncpy(buf, "abcdef", sizeof(buf));
printf("%s", buf);
```

A) Aucun

B) Fuite mémoire

C) Chaîne potentiellement non terminée par `\\0`

D) Buffer overflow

Réponse :

41. Quel est le résultat de ce code ?**

```c
int a = 0;
int b = sizeof(a++);
printf("%d %d", a, b);
```

A) 0 sizeof(int)

B) 1 sizeof(int)

C) 1 1

D) Comportement indéfini

Réponse :

42. Quel est le problème ici ?**

```c
int *p = malloc(sizeof *p);
if (!p) return;
*p = 42;
```

A) Aucun

B) Fuite mémoire

C) Accès invalide

D) Mauvais test d’erreur

Réponse :


43. Quel est le résultat de ce code ?**

```c
int a = 1;
int b = a+++a;
printf("%d", b);
```

A) Erreur de compilation

B) 2

C) 3

D) Comportement indéfini

Réponse :

44. Quelle est la sortie possible de ce programme ?**

```c
int x = 0;
if (x = 1)
    printf("A");
else
    printf("B");
```

A) B

B) Rien

C) A

D) Comportement indéfini

Réponse :



############################
######### PARTIE 2 #########
############################

**Instructions :**

* Toutes les questions demandent une analyse argumentée.
* Vous pouvez proposer des corrections ou améliorations lorsque cela est pertinent.
* Justifiez toujours vos réponses en vous appuyant sur le fonctionnement interne du C (mémoire, pointeurs, standards, I/O, système…).

---

## Exercice 1 — Gestion de la mémoire et pointeurs

On vous fournit le code suivant :

```c
#include <stdio.h>
#include <stdlib.h>

int* build_array(size_t n) {
    int* arr = malloc(n * sizeof(int));
    for (size_t i = 0; i <= n; i++) {
        arr[i] = i * 2;
    }
    return arr;
}

int main() {
    int* data = build_array(10);
    free(data);
    printf("%d\n", data[5]);
    return 0;
}
```

### **Questions :**

1. Identifiez toutes les erreurs (logiques, mémoire, sécurité) présentes dans ce programme.
   Expliquez en quoi elles sont problématiques.

Réponse :




2. Proposez une version corrigée de la fonction `build_array`.
   Justifiez vos choix (conditions, tailles, gestion d’erreur, const…).

Réponse :




3. Expliquez pourquoi l’accès `data[5]` après `free(data)` est dangereux même si cela “semble fonctionner”.
   Argumentez en termes de modèle mémoire et comportement indéfini.

Réponse :





---

## Exercice 2 — Pointeurs de fonction et `restrict`

Le mot-clé `restrict` est un qualificateur de pointeur qui indique au compilateur que, pendant toute la durée de vie du pointeur, la zone mémoire qu’il référence ne sera accessible que par ce pointeur.

Autrement dit : aucun autre pointeur ne pointera vers la même zone mémoire.

Important : restrict n’est pas une optimisation automatique, c’est une promesse contractuelle que fait le développeur au compilateur.

Considérez le code suivant :

```c
void apply(int *restrict a, int *restrict b, size_t n, int (*op)(int, int)) {
    for (size_t i = 0; i < n; i++) {
        a[i] = op(a[i], b[i]);
    }
}

int add(int x, int y) { return x + y; }

int main() {
    int t[] = {1, 2, 3};
    apply(t, t, 3, add);
    return 0;
}
```

### **Questions :**

1. Expliquez pourquoi ce code viole les garanties liées au qualificatif `restrict`.

Réponse :





2. Décrivez les conséquences potentielles sur l’optimisation ou le comportement du programme.

Réponse :





3. Proposez une manière correcte d’utiliser cette fonction dans `main` ou modifiez la fonction pour éviter le problème.

Réponse :





---

## Exercice 3 — Analyse de structures de données

On vous fournit un extrait de gestion d’une liste doublement chaînée :

```c
typedef struct Node {
    int value;
    struct Node* next;
    struct Node* prev;
} Node;

void insert_after(Node* n, Node* new_node) {
    new_node->next = n->next;
    n->next = new_node;
    new_node->prev = n;
    if (n->next != NULL) {
        n->next->prev = new_node;
    }
}
```

### **Questions :**

1. Expliquez pourquoi ce code contient un bug. (Vous devrez analyser la séquence des affectations next, prev)

Réponse :





2. Proposez une version corrigée en expliquant l’ordre nécessaire des opérations.

Réponse :





---

## Exercice 4 — Manipulation de fichiers binaires

Voici un code censé écrire puis lire une structure dans un fichier binaire :

```c
typedef struct {
    int id;
    double score;
} Record;

void save(const Record* r) {
    FILE* f = fopen("data.bin", "w");
    fwrite(r, sizeof(Record), 1, f);
    fclose(f);
}

Record load() {
    Record r;
    FILE* f = fopen("data.bin", "r");
    fread(&r, sizeof(Record), 1, f);
    fclose(f);
    return r;
}
```

### **Questions :**

1. Analysez les erreurs dans l’utilisation des modes d’ouverture des fichiers.
   Expliquez leur impact sur les flux binaires.

Réponse :





2. Expliquez pourquoi il est nécessaire de vérifier le résultat des `fopen`, `fread`, `fwrite`.
   Donnez des exemples de scénarios réels où cela échouerait.

Réponse :





3. Proposez des corrections et vos justifications.

Réponse :





