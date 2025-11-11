Bonjour à toutes et à tous !

Nous allons démarrer notre exploration du langage C par un premier contact direct avec la machine. L'objectif de ce TP est de vous familiariser avec le cycle de vie d'un programme très simple : écriture du code, compilation, puis exécution.

---

### **TP 1 : Mon Premier Programme C - Affichage Personnalisé**

**Objectif Pédagogique :**
Prendre en main l'environnement de développement C en écrivant, compilant et exécutant un programme simple.

**Contexte :**
Chaque voyage commence par un premier pas. En programmation C, ce premier pas consiste souvent à faire interagir le programme avec l'utilisateur, même de la manière la plus basique : afficher du texte. Ce TP vous guide pour écrire votre tout premier programme C fonctionnel.

**Énoncé de l'Exercice :**
Écrivez un programme en langage C qui réalise les actions suivantes :
1.  Affiche votre prénom sur une première ligne.
2.  Affiche votre nom de famille sur la ligne suivante.
3.  Le programme doit ensuite se terminer proprement.

**Ressources Nécessaires :**
*   Un éditeur de texte (VS Code, Sublime Text, Notepad++, Vim, Emacs, etc.).
*   Un compilateur C (GCC est le plus courant et sera utilisé pour les exemples).
*   Un terminal ou une invite de commande.

**Étapes Détaillées :**

1.  **Création du fichier source :**
    Ouvrez votre éditeur de texte et créez un nouveau fichier. Enregistrez-le sous le nom `mon_premier_programme.c` (ou un nom similaire, l'extension `.c` est importante pour indiquer qu'il s'agit d'un fichier source C).

2.  **Écriture du code :**
    Dans ce fichier, écrivez le code C nécessaire pour accomplir l'énoncé. Pensez aux fonctions d'affichage standard et aux caractères spéciaux pour les retours à la ligne.

3.  **Compilation :**
    Ouvrez votre terminal (ou invite de commande) et naviguez jusqu'au répertoire où vous avez enregistré votre fichier `.c`. Utilisez la commande de compilation GCC :
    ```bash
    gcc mon_premier_programme.c -o mon_premier_programme
    ```
    *   `gcc` : C'est le nom du compilateur.
    *   `mon_premier_programme.c` : C'est votre fichier source.
    *   `-o mon_premier_programme` : Indique au compilateur de créer un fichier exécutable nommé `mon_premier_programme`.

    Si tout se passe bien, un fichier exécutable (sans extension sous Linux/macOS, ou `mon_premier_programme.exe` sous Windows) sera créé dans le même répertoire.

4.  **Exécution :**
    Dans le même terminal, exécutez votre programme :
    *   **Sous Linux/macOS :**
        ```bash
        ./mon_premier_programme
        ```
    *   **Sous Windows :**
        ```cmd
        .\mon_premier_programme.exe
        ```
        (ou simplement `mon_premier_programme` si votre système est configuré pour cela).

5.  **Vérification :**
    Assurez-vous que le programme affiche bien votre prénom et votre nom sur deux lignes distinctes, comme demandé.

---

**Conseils et Utilisation de l'IA :**

N'hésitez pas à consulter la documentation ou à utiliser des outils d'IA (comme ChatGPT, Copilot, etc.) si vous bloquez. L'objectif ici n'est pas de mémoriser chaque syntaxe dès le premier jour, mais de comprendre le *processus* : écrire, compiler, exécuter. Si l'IA vous donne une solution, prenez le temps de la lire, de la comprendre et d'expliquer *pourquoi* elle fonctionne. C'est en comprenant que vous apprendrez le plus.

**Pour aller plus loin (Optionnel) :**

Une fois que votre programme fonctionne, essayez d'ajouter une troisième ligne qui affiche un message de bienvenue personnalisé, par exemple : "Bienvenue, [Prénom] [Nom] !".