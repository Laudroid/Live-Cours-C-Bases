# Séance 3 : Structures de Contrôle (4 heures)

## Partie 2 : Les Boucles

### 4. Boucles infinies et comment les éviter

---

## 1. Définition d’une boucle infinie

Une **boucle infinie** est une boucle qui ne se termine jamais car sa condition de sortie n’est jamais atteinte ou ne peut jamais être fausse.

Cela provoque un blocage du programme, consommant souvent inutilement les ressources du processeur.

---

## 2. Comment une boucle infinie se produit-elle ?

- La condition de la boucle **reste toujours vraie**.
- La ou les variables contrôlant la condition **ne sont pas modifiées** à l’intérieur de la boucle.
- Une erreur logique dans la condition empêche la sortie.
- Mauvaise manipulation des variables, ou oubli d’un mécanisme d’arrêt.
- Boucle volontaire pour certains usages spécifiques, mais à maîtriser.

---

## 3. Exemples typiques de boucles infinies

### Exemple 1 : oubli de mise à jour de la variable de contrôle dans une boucle `while`

```c
int i = 0;
while (i < 10) {
    printf("%d\n", i);
    // i++ est oublié, la valeur reste 0 -> boucle infinie
}
```

### Exemple 2 : condition faussement toujours vraie dans une boucle `for`

```c
for (int j = 0; j >= 0; j++) {
    // j >= 0 est toujours vrai pour un entier signé qui déborde rarement,
    // sauf overflow défini par le compilateur - la boucle est potentiellement infinie
    printf("%d\n", j);
}
```

---

## 4. Diagramme Mermaid : boucle infinie typique

```mermaid
flowchart TD
    A[Initialisation] --> B[Évaluation condition (toujours vraie)]
    B --> C[Exécution bloc code]
    C --> B
    note right of B
        Cela ne se termine jamais
    end
```

---

## 5. Techniques pour éviter les boucles infinies

- **Modifier systématiquement la variable d’itération ou la condition** durant l'exécution de la boucle.
- Tester la boucle avec des **cas d’arrêt clairs et atteignables**.
- Privilégier une **structure claire** (ex : utiliser `for` quand on connaît le nombre d’itérations).
- Ajouter des **instructions d’arrêt explicites** (`break`) si besoin, dans des conditions bien définies.
- Ne pas dépendre uniquement de conditions complexes : simplifier les conditions ou les écrire clairement.
- Tester régulièrement la condition dans la boucle, et prévoir un système de sécurité (nombre maximal d’itérations, temporisation).

---

## 6. Exemples corrigés

### Correction de l’exemple 1

```c
int i = 0;
while (i < 10) {
    printf("%d\n", i);
    i++;  // Incrémentation nécessaire
}
```

### Utilisation judicieuse d’un `break` pour sortie conditionnelle

```c
int compteur = 0;

while (1) {  // boucle infinie intentionnelle
    printf("Compteur = %d\n", compteur);
    compteur++;
    if (compteur >= 10) {
        break;  // sortie de la boucle
    }
}
```

---

## 7. Quand une boucle infinie est-elle intentionnelle ?

- En programmation système (processus serveurs).
- Pour attendre un événement externe.
- Dans des implémentations d’attente active ou de pollings.
- Toujours associée à un mécanisme de sortie (ex : signal, interruption).

---

## 8. Sources utilisées

- [cppreference.com - While loop](https://en.cppreference.com/w/c/language/while)  
- [GeeksforGeeks - Infinite Loop in C](https://www.geeksforgeeks.org/infinite-loops-in-c-and-its-types/)  
- [TutorialsPoint - C Infinite loops](https://www.tutorialspoint.com/cprogramming/c_infinite_loop.htm)  
- ISO/IEC 9899:2018 (C18) – Chapitre 6.8.5 (boucles)

---

Une vigilance constante sur la condition d'arrêt et la modification correcte de la variable(s) de contrôle évite les boucles infinies non désirées. Cette bonne habitude permet d'assurer la robustesse et la stabilité des programmes.