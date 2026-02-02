# Fichiers de sauvegarde et structures personnalisées en C

---

## Contexte pédagogique

Dans un programme réel, les données doivent être **conservées** même après la fermeture de l’application.
Dans cette extension, nous allons simuler un **mini système bancaire** permettant de :

* créer des comptes
* enregistrer ces comptes dans un fichier
* relire les comptes depuis un fichier

Les données seront stockées grâce à des **structures (`struct`)** et sauvegardées dans des **fichiers**.

---

## Prérequis

* Avoir réalisé le TP précédent sur les fichiers
* Savoir utiliser une structure en C
* Savoir compiler un programme avec `gcc`

---

## Rappels sur les structures (15 min)

### Définition d’une structure

```c
typedef struct {
    int numero;
    char titulaire[50];
    float solde;
} Compte;
```

Cette structure représente un **compte bancaire simplifié**.

### Déclaration d’une variable

```c
Compte c1;
```

### Tableau de structures

```c
Compte comptes[100];
int nbComptes = 0;
```

---

## Création d’un compte bancaire (20 min)

### Objectif

Permettre à l’utilisateur de créer un compte bancaire en saisissant les informations.

### Exercice 1

Écrire une fonction :

```c
Compte creerCompte();
```

Elle devra :

1. Demander un numéro de compte
2. Demander le nom du titulaire
3. Demander le solde initial
4. Retourner un `Compte`

### Sécurité

* Utiliser `fgets` pour les chaînes
* Vérifier que le solde est positif

---

## Sauvegarde des comptes dans un fichier (30 min)

### Principe

Chaque compte sera sauvegardé **sur une ligne** du fichier `comptes.txt` :

```
1;Alice;1200.50
2;Bob;350.00
```

### Écriture dans un fichier

```c
fprintf(f, "%d;%s;%.2f\n", c.numero, c.titulaire, c.solde);
```

### Exercice 2

Écrire une fonction :

```c
void sauvegarderComptes(Compte comptes[], int nb);
```

Cette fonction devra :

* Ouvrir `comptes.txt` en écriture
* Sauvegarder tous les comptes
* Gérer les erreurs d’ouverture
* Fermer le fichier

---

## Chargement des comptes depuis un fichier (30 min)

### Lecture avec `fscanf`

```c
fscanf(f, "%d;%49[^;];%f", &c.numero, c.titulaire, &c.solde);
```

### Exercice 3

Écrire une fonction :

```c
int chargerComptes(Compte comptes[]);
```

Elle devra :

* Ouvrir `comptes.txt` en lecture
* Lire chaque ligne du fichier
* Remplir le tableau de comptes
* Retourner le nombre de comptes chargés

### Sécurité

* Vérifier la valeur de retour de `fscanf`
* Ne jamais dépasser la taille du tableau

---

## Mini application complète (25 min)

### Objectif

Créer un programme `banque.c` avec un menu simple :

```
1. Ajouter un compte
2. Afficher les comptes
3. Sauvegarder les comptes
4. Charger les comptes
0. Quitter
```

### Règles

* Les comptes sont stockés en mémoire
* La sauvegarde est manuelle
* Le chargement écrase les données en mémoire

### Exercice final

Implémenter le menu et toutes les fonctionnalités associées.

---

## Critères de réussite

✔ Le programme compile sans erreur
✔ Les comptes sont correctement sauvegardés
✔ Les comptes sont correctement relus
✔ Aucune saisie non sécurisée
✔ Code lisible et commenté

---

## Pour aller plus loin (bonus)

* Ajouter des dépôts / retraits
* Vérifier les doublons de numéro de compte
* Sauvegarder automatiquement à la fermeture
* Version fichier binaire (`fwrite` / `fread`)

---

## Extension Sécurité – Validation et cohérence des comptes bancaires

Cette extension vise à introduire des **bonnes pratiques de sécurité logique** et de **validation métier**, indispensables dans toute application manipulant des données sensibles.

---

## Objectifs de l’extension sécurité

À l’issue de cette partie, l’étudiant sera capable de :

* Valider les données saisies par l’utilisateur
* Garantir la cohérence des soldes bancaires
* Empêcher des opérations interdites
* Rendre l’application plus robuste face aux erreurs

---

## Validation des données à la saisie

### Règles de validation

Lors de la création d’un compte :

* Le numéro de compte doit être **strictement positif**
* Le numéro de compte doit être **unique**
* Le nom du titulaire ne doit pas être vide
* Le solde initial doit être **supérieur ou égal à 0**

### Exercice 6

Créer une fonction :

```c
int estNumeroUnique(Compte comptes[], int nb, int numero);
```

Elle retourne :

* `1` si le numéro est unique
* `0` sinon

Utiliser cette fonction lors de la création d’un compte.

---

## Sécurisation des opérations bancaires

### Dépôt d’argent

Règles :

* Le montant doit être strictement positif
* Le compte doit exister

```c
int depot(Compte *c, float montant);
```

La fonction retourne :

* `1` si l’opération est valide
* `0` sinon

---

### Retrait d’argent

Règles essentielles :

* Le montant doit être strictement positif
* Le solde ne doit jamais devenir négatif

```c
int retrait(Compte *c, float montant);
```

Si le retrait est impossible, le solde ne doit pas être modifié.

---

## Contrôle de cohérence globale

### Vérification des comptes chargés depuis le fichier

Lors du chargement des comptes :

* Refuser les comptes avec un solde négatif
* Refuser les numéros de compte dupliqués
* Afficher un message d’erreur clair

### Exercice 7

Modifier la fonction `chargerComptes` pour :

* Ignorer les lignes invalides
* Compter et afficher le nombre d’erreurs détectées

---

## Sécurisation du menu utilisateur

### Bonnes pratiques

* Vérifier systématiquement les choix du menu
* Refuser toute option inconnue
* Éviter les boucles infinies dues à des entrées invalides

### Exercice 8

Mettre en place une fonction :

```c
int lireChoixMenu();
```

Elle doit :

* Lire une entrée utilisateur
* Vérifier qu’elle est valide
* Redemander la saisie si nécessaire

---

## Mini scénario de test (sécurité)

Tester les cas suivants :

* Création d’un compte avec solde négatif
* Création de deux comptes avec le même numéro
* Retrait supérieur au solde
* Chargement d’un fichier corrompu






