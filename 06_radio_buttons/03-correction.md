# **Quiz – Compréhension du script Tkinter : Utilisation des Radiobuttons**

## Instructions
- Répondez à chaque question avec précision.
- Ce quiz évalue votre compréhension de l'utilisation des Radiobuttons, des variables associées et de l'affichage du choix utilisateur.

---

## **Partie 1 – Questions à Choix Multiples (QCM)**

**1.** Quel type de variable est utilisée pour stocker la sélection d'un groupe de `Radiobuttons` ?
- a) `IntVar`
- b) `StringVar`
- c) `BooleanVar`
- d) `DoubleVar`

**2.** Pourquoi tous les `Radiobuttons` partagent-ils la même variable (`storage_variable`) ?
- a) Pour permettre plusieurs sélections en même temps
- b) Pour relier les boutons et garantir qu'un seul est sélectionné à la fois
- c) Pour leur donner des couleurs différentes
- d) Pour leur assigner un identifiant numérique unique

**3.** Que se passe-t-il si vous assignez une variable différente à chaque `Radiobutton` ?
- a) Tous les boutons fonctionnent normalement
- b) Aucun bouton ne sera sélectionnable
- c) Plusieurs boutons pourront être sélectionnés en même temps
- d) Cela générera une erreur lors de l’exécution

**4.** Quelle méthode est utilisée pour afficher la sélection après la fermeture de la fenêtre ?
- a) `storage_variable.select()`
- b) `storage_variable.choose()`
- c) `storage_variable.get()`
- d) `storage_variable.show()`

**5.** Quel gestionnaire d'affichage est utilisé pour placer les `Radiobuttons` dans la fenêtre ?
- a) `grid()`
- b) `place()`
- c) `pack()`
- d) `flow()`

---

## **Partie 2 – Questions Vrai ou Faux**

**6.** Chaque `Radiobutton` possède un paramètre `value` qui détermine la valeur stockée lorsqu'il est sélectionné.  
**Répondez :** Vrai / Faux

**7.** Il est possible de sélectionner simultanément plusieurs `Radiobuttons` liés à la même variable.  
**Répondez :** Vrai / Faux

**8.** La méthode `pack()` est utilisée ici pour placer les trois boutons verticalement dans la fenêtre.  
**Répondez :** Vrai / Faux

**9.** `print(storage_variable.get())` s'exécute à chaque fois qu'un Radiobutton est cliqué.  
**Répondez :** Vrai / Faux

---

## **Partie 3 – Réponses Courtes**

**10.** Expliquez ce que fait la commande suivante :
```python
storage_variable = tk.StringVar()
```

**11.** Pourquoi utilise-t-on `print(storage_variable.get())` **après** `root.mainloop()` et non **avant** ?

**12.** Que faudrait-il modifier si l'on voulait afficher **immédiatement** le choix de l'utilisateur dès qu'il sélectionne un `Radiobutton` (sans attendre la fermeture de la fenêtre) ?

---

## **Partie 4 – Question de réflexion**

**13.** Imaginez que vous voulez créer **deux groupes indépendants** de `Radiobuttons` (ex: choix de couleur ET choix de taille).  
Comment structureriez-vous le code pour éviter que les sélections interfèrent entre les deux groupes ?

---

# **Barème proposé**

| Partie | Points |
|:------|------:|
| QCM (5 questions) | 10 points |
| Vrai/Faux (4 questions) | 8 points |
| Réponses courtes (3 questions) | 9 points |
| Question de réflexion (1 question) | 8 points |
| **Total** | **35 points** |

---

#  **Corrigé du Quiz**

## Partie 1 – QCM
1. **b) StringVar**  
2. **b) Pour relier les boutons et garantir qu'un seul est sélectionné à la fois**  
3. **c) Plusieurs boutons pourront être sélectionnés en même temps**  
4. **c) storage_variable.get()**  
5. **c) pack()**

## Partie 2 – Vrai/Faux
6. **Vrai**  
7. **Faux**  
8. **Vrai**  
9. **Faux** (le `print()` n'est exécuté **qu’après** la fermeture de la fenêtre)

## Partie 3 – Réponses courtes
10. **Elle crée une variable `StringVar` qui stockera la valeur correspondant au `Radiobutton` sélectionné.**  
11. **Parce que `root.mainloop()` est une boucle bloquante ; donc le script ne continue qu'après que la fenêtre soit fermée.**  
12. **Il faudrait ajouter un paramètre `command=fonction_a_executer` lors de la création de chaque `Radiobutton`, pour exécuter une fonction à chaque clic.**

## Partie 4 – Réflexion
13. **Il faut créer deux variables différentes (`color_choice = StringVar()` et `size_choice = StringVar()`) et associer chaque groupe de `Radiobuttons` à la variable correspondante pour que leurs sélections soient indépendantes.**

