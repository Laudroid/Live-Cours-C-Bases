Bonjour à toutes et à tous !

Nous allons démarrer notre exploration du langage C avec un premier TP très concret. L'objectif est de poser les bases de la manipulation des données et des opérations arithmétiques, des compétences fondamentales pour tout programmeur.

---

### **TP 1 : Les Fondamentaux de l'Arithmétique en C - Gestion de Stock Simplifiée**

**Objectif Pédagogique :**
À l'issue de ce TP, vous serez capable de :
*   Déclarer et manipuler des variables de type entier (`int`).
*   Effectuer des opérations arithmétiques de base (`+`, `-`, `*`, `/`).
*   Interagir avec l'utilisateur pour la saisie de données (`scanf`).
*   Afficher des résultats de manière claire (`printf`).
*   Comprendre la structure minimale d'un programme C.

**Contexte (Mini-projet) :**
Imaginez que vous travaillez sur un petit système de gestion de stock. Votre tâche est de créer un programme simple qui aide à suivre l'évolution de deux quantités d'articles. Par exemple, un stock initial et une quantité ajoutée ou retirée. Ce programme sera la brique de base pour des systèmes plus complexes.

**Énoncé de l'Exercice :**

Votre programme doit :

1.  **Demander à l'utilisateur** d'entrer deux nombres entiers. Pour le contexte de notre mini-projet, nous pouvons les imaginer comme une `quantite_initiale` et une `quantite_ajoutee_ou_retiree`, mais vous êtes libre de les nommer comme vous le souhaitez dans votre code.
2.  **Calculer et afficher** les résultats des opérations suivantes entre ces deux nombres :
    *   La **somme** (représentant le nouveau stock total).
    *   La **différence** (représentant la variation nette ou la différence entre les deux quantités).
    *   Le **produit** (utile si l'on devait calculer une valeur totale, par exemple, ou une projection).
    *   La **division** (pour répartir une quantité en lots égaux, par exemple).
3.  **Assurez-vous que les messages** d'invitation à la saisie et les affichages des résultats sont clairs et explicites pour l'utilisateur.

**Consignes Techniques :**

*   Utilisez le type de variable `int` pour stocker vos nombres et les résultats des calculs.
*   N'oubliez pas d'inclure la bibliothèque standard d'entrée/sortie (`stdio.h`) pour pouvoir utiliser `printf` et `scanf`.
*   Pour la division, gardez à l'esprit que la division entre deux entiers en C donne un résultat entier (par exemple, `10 / 3` donnera `3`). C'est le comportement attendu pour ce TP.

**Conseils pour l'apprentissage (y compris avec l'IA) :**

L'utilisation d'outils d'intelligence artificielle est une réalité et peut être une aide précieuse dans votre apprentissage. N'hésitez pas à les solliciter si vous bloquez, si vous souhaitez explorer différentes manières d'aborder le problème, ou simplement pour vérifier votre compréhension.

Cependant, l'objectif principal de ce TP est votre *compréhension* et votre *maîtrise* des concepts. Utilisez l'IA comme un assistant intelligent, pas un substitut à votre réflexion :

*   **Posez des questions ciblées :** Au lieu de demander "Donne-moi le code pour ce TP", essayez des questions comme :
    *   "Comment puis-je demander à l'utilisateur d'entrer un nombre entier en C ?"
    *   "Quelle est la syntaxe pour afficher le résultat d'une somme en C ?"
    *   "Explique-moi ce que fait la fonction `scanf`."
    *   "Comment déclarer une variable de type entier en C ?"
*   **Analysez le code généré :** Si l'IA vous fournit un morceau de code, prenez le temps de le lire attentivement, ligne par ligne. Essayez de comprendre pourquoi chaque instruction est là et ce qu'elle fait.
*   **Expérimentez :** Une fois que vous avez une solution (que vous l'ayez écrite vous-même ou avec l'aide de l'IA), modifiez-la. Changez les valeurs, ajoutez des messages, testez les limites. C'est en expérimentant que vous solidifierez vos connaissances.
*   **Débuggez :** Si votre programme ne fonctionne pas comme prévu, essayez de comprendre pourquoi. L'IA peut aussi vous aider à débugger en lui décrivant votre problème et le code que vous avez.

**Exemple de Résultat Attendu (Simulation d'exécution) :**

```
Entrez la première quantité (ex: stock initial) : 150
Entrez la deuxième quantité (ex: mouvement de stock) : 30

--- Résultats des opérations ---
Somme (Nouveau stock total) : 180
Différence (Variation nette) : 120
Produit (Valeur potentielle) : 4500
Division (Lots possibles) : 5
```

Amusez-vous bien avec ce premier programme en C ! N'hésitez pas si vous avez des questions.