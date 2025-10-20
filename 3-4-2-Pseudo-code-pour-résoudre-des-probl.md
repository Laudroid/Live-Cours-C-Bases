# Séance 3 : Structures de Contrôle (4 heures)

## Partie 4 : Exercices Guidés de Structures de Contrôle

### 2. Pseudo-code pour résoudre des problèmes simples

---

## 1. Introduction au pseudo-code

Le **pseudo-code** est une méthode d’expression informelle permettant de décrire un algorithme ou un programme de manière claire et lisible, indépendante d’un langage de programmation précis.

Il sert à :

- Concevoir la logique avant la programmation.
- Faciliter la compréhension et la communication entre programmeurs.
- Prévenir les erreurs en réfléchissant au flux général.

---

## 2. Principes du pseudo-code

- Utiliser des structures de contrôle classiques : `Si ... Alors`, `Tant que`, `Pour`, `Faire ... Tant que`.
- Employer un vocabulaire proche du langage parlé ou naturel.
- Rester simple et précis : ni trop détaillé, ni trop abstrait.
- Décomposer un problème en étapes séquentielles et logiques.

---

## 3. Exemples concrets

### Exemple 1 : Vérification de la parité d’un nombre

**Problème :** Afficher si un nombre est pair ou impair.

```plaintext
Début
    Lire nombre
    Si nombre modulo 2 = 0 Alors
        Afficher "Le nombre est pair"
    Sinon
        Afficher "Le nombre est impair"
    Fin Si
Fin
```

---

### Exemple 2 : Calcul de la somme des 10 premiers nombres entiers

```plaintext
Début
    somme <- 0
    Pour i allant de 1 à 10 faire
        somme <- somme + i
    Fin Pour
    Afficher somme
Fin
```

---

### Exemple 3 : Recherche d’un élément dans un tableau

```plaintext
Début
    Lire tableau T de taille n
    Lire valeur x
    trouvé <- faux
    i <- 0
    Tant que i < n et trouvé = faux faire
        Si T[i] = x Alors
            trouvé <- vrai
        Sinon
            i <- i + 1
        Fin Si
    Fin Tant que

    Si trouvé = vrai Alors
        Afficher "Valeur trouvée"
    Sinon
        Afficher "Valeur non trouvée"
    Fin Si
Fin
```

---

## 4. Diagramme Mermaid : Exemple de recherche dans un tableau

```mermaid
flowchart TD
    A[Début] --> B[Lire T, n, x]
    B --> C[i=0, trouvé=faux]
    C --> D{i < n et trouvé = faux ?}
    D -- Oui --> E[T[i] = x ?]
    E -- Oui --> F[trouvé = vrai]
    E -- Non --> G[i = i + 1]
    G --> C
    D -- Non --> H{trouvé = vrai ?}
    H -- Oui --> I[Afficher "Valeur trouvée"]
    H -- Non --> J[Afficher "Valeur non trouvée"]
    I --> K[Fin]
    J --> K
```

---

## 5. Conseils pour rédiger un pseudo-code efficace

- Préférer la clarté à la concision excessive.
- Bien définir les variables et les structures de données avant leur utilisation.
- Identifier clairement les conditions et boucles nécessaires.
- Utiliser des mots-clés cohérents et compréhensibles (par exemple, `Si`, `Sinon`, `Pour`, `Tant que`).
- Décomposer les problèmes complexes en sous-problèmes successifs.

---

## 6. Sources utilisées

- [Wikipedia - Pseudocode](https://fr.wikipedia.org/wiki/Pseudocode)  
- [OpenClassrooms - Algorithmes : Faites vos premiers pas](https://openclassrooms.com/fr/courses/19980-apprenez-a-programmer-en-c/19885-les-algorithmes)  
- [GeeksforGeeks - Pseudocode Introduction](https://www.geeksforgeeks.org/pseudocode-introduction/)  
- [Tutorialspoint - Introduction to Algorithms and Pseudocode](https://www.tutorialspoint.com/algorithm-analysis/index.htm)  

---

Le pseudo-code est un outil clé pour structurer avant de coder, il permet d'exprimer clairement des algorithmes et facilite la traduction en langage C ou tout autre langage de programmation. Il doit être simple, lisible et refléter la logique complète du problème.