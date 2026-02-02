
# TP – Gestion des fichiers en langage C

## Prérequis

* Bases du langage C
* Connaissance des types (`int`, `char`, tableaux, pointeurs simples)
* Utilisation d’un éditeur de code (VS Code, Code::Blocks, etc.)
* Compilation avec `gcc`

## Rappels théoriques

### Qu’est-ce qu’un fichier ?

Un fichier permet de stocker des données de manière **persistante**, même après l’arrêt du programme.

### Types de fichiers

* Fichiers texte (`.txt`)
* Fichiers binaires (`.dat`, `.bin`)

Dans ce TP, nous travaillerons **uniquement avec des fichiers texte**.

### Bibliothèque utilisée

```c
#include <stdio.h>
```

### Type principal

```c
FILE *fichier;
```

---

## Ouvrir et fermer un fichier (20 min)

### Syntaxe

```c
FILE *f = fopen("nom_du_fichier.txt", "mode");
```

### Modes principaux

| Mode | Signification                |
| ---- | ---------------------------- |
| `r`  | Lecture seule                |
| `w`  | Écriture (écrase le fichier) |
| `a`  | Ajout à la fin               |

### Toujours vérifier l’ouverture

```c
if (f == NULL) {
    printf("Erreur lors de l'ouverture du fichier\n");
    return 1;
}
```

### Ne pas oublier de fermer le fichier

```c
fclose(f);
```

### Exercice 1

* Créer un programme qui ouvre un fichier `test.txt`
* Afficher un message si le fichier ne peut pas être ouvert
* Fermer le fichier correctement

---

## Écriture dans un fichier

### Fonction `fprintf`

```c
fprintf(f, "Bonjour fichier !\n");
```

### Exercice 2

Créer un programme qui :

1. Ouvre un fichier `notes.txt` en écriture
2. Demande à l’utilisateur son prénom
3. Demande une note sur 20
4. Écrit dans le fichier sous la forme :

```
Alice : 15/20
```

Compiler, exécuter, puis ouvrir le fichier pour vérifier le contenu.

---

## Lecture depuis un fichier

### Lecture caractère par caractère

```c
char c;
while ((c = fgetc(f)) != EOF) {
    printf("%c", c);
}
```

### Lecture ligne par ligne

```c
char ligne[100];
while (fgets(ligne, 100, f) != NULL) {
    printf("%s", ligne);
}
```

### Exercice 3

* Ouvrir le fichier `notes.txt` en lecture
* Afficher son contenu ligne par ligne

---

## Gestion des erreurs et sécurité

### Bonnes pratiques essentielles

✅ Toujours vérifier `fopen`
✅ Limiter la taille des buffers
✅ Ne jamais faire confiance aux entrées utilisateur
✅ Toujours fermer les fichiers

### ❌ Exemple dangereux

```c
char nom[10];
scanf("%s", nom); // DANGEREUX
```

### Version plus sûre

```c
fgets(nom, 10, stdin);
```

### Exercice 4

Modifier les exercices précédents pour :

* Sécuriser toutes les entrées utilisateur
* Gérer proprement les erreurs

---

## Exercice final – Mini application

### 🎯 Objectif

Créer un programme `journal.c` qui :

1. Demande à l’utilisateur un message
2. Ajoute ce message dans un fichier `journal.txt`
3. Affiche ensuite **tout le contenu du journal**

### Contraintes

* Utiliser le mode `a`
* Gérer les erreurs
* Code clair et commenté

---

## Pour aller plus loin (bonus)

* Compter le nombre de lignes dans un fichier
* Créer un fichier de sauvegarde
* Découvrir les fichiers binaires (`fread`, `fwrite`)

---

**Fin du TP – Bravo**
