
# **Quiz – Compréhension du script Tkinter : Utilisation du Spinbox**

## Instructions
- Lisez attentivement chaque question.
- Répondez avec précision.
- Ce quiz évalue votre compréhension du widget `Spinbox`, de sa configuration et de son interaction avec l'utilisateur.

---

## **Partie 1 – Questions à Choix Multiples (QCM)**

**1.** Quel type de variable est utilisé pour stocker la valeur du `Spinbox` dans ce script ?
- a) `IntVar`
- b) `StringVar`
- c) `BooleanVar`
- d) `DoubleVar`

**2.** Que permet de faire l'option `wrap=False` dans la configuration du `Spinbox` ?
- a) Forcer la sélection d'une valeur parmi une liste fixe
- b) Empêcher que la sélection dépasse les limites hautes ou basses
- c) Boucler automatiquement de la valeur maximale vers la minimale
- d) Désactiver les flèches de navigation

**3.** Quelle méthode est utilisée pour récupérer la valeur actuelle du `Spinbox` ?
- a) `spin_box.value()`
- b) `spin_box.get()`
- c) `spin_box.select()`
- d) `spin_box.read()`

**4.** Dans la variante commentée, quelle configuration remplace la plage `from_` / `to` ?
- a) L'utilisation de `default` pour les valeurs
- b) L'utilisation d'un tuple dans `values`
- c) La déclaration d'une fonction personnalisée
- d) L'utilisation de `range` directement

**5.** Quand est exécutée l'instruction `print(spin_box.get())` dans ce script ?
- a) Dès que l'utilisateur change la valeur
- b) Après la fermeture de la fenêtre
- c) Avant le lancement de `mainloop()`
- d) Lors de l'initialisation de `mainloop()`

---

## **Partie 2 – Questions Vrai ou Faux**

**6.** Le `Spinbox` permet à l'utilisateur de saisir une valeur manuellement en plus d'utiliser les flèches.  
**Répondez :** Vrai / Faux

**7.** La valeur du `Spinbox` est initialisée ici à 20.  
**Répondez :** Vrai / Faux

**8.** Si `wrap=True`, atteindre la valeur maximale permettrait de revenir automatiquement à la valeur minimale.  
**Répondez :** Vrai / Faux

**9.** Le widget `Spinbox` est créé avec le module `ttk` dans ce script.  
**Répondez :** Vrai / Faux

---

## **Partie 3 – Réponses Courtes**

**10.** Expliquez ce que fait la commande suivante :
```python
initial_value = tk.StringVar(value=20)
```

**11.** Pourquoi est-il déconseillé d'utiliser `print(spin_box.get())` **avant** `mainloop()` dans une vraie application interactive ?

**12.** Comment modifieriez-vous le `Spinbox` pour proposer uniquement les valeurs suivantes : 5, 10, 15, 20, 25, 30 ?

---

## **Partie 4 – Question de réflexion**

**13.** Proposez une situation concrète où l'utilisation d'un `Spinbox` serait préférable à une `Combobox`.  
Expliquez pourquoi et comment vous le configureriez.

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

# ✅ **Corrigé du Quiz**

## Partie 1 – QCM
1. **b) StringVar**  
2. **b) Empêcher que la sélection dépasse les limites hautes ou basses**  
3. **b) spin_box.get()**  
4. **b) L'utilisation d'un tuple dans `values`**  
5. **c) Avant le lancement de `mainloop()`**

## Partie 2 – Vrai/Faux
6. **Vrai**  
7. **Vrai**  
8. **Vrai**  
9. **Faux** (le `Spinbox` vient de `tk`, pas de `ttk`)

## Partie 3 – Réponses courtes
10. **Elle crée une variable `StringVar` initialisée à 20 pour stocker dynamiquement la valeur sélectionnée par l'utilisateur dans le `Spinbox`.**  
11. **Parce qu'avant `mainloop()`, l'utilisateur n'a pas encore interagi ; la valeur affichée est donc simplement l'initialisation par défaut, pas un choix réel.**  
12. **Supprimer `from_` et `to`, et utiliser `values=(5, 10, 15, 20, 25, 30)` dans la création du `Spinbox`.**

## Partie 4 – Réflexion
13. **Exemple : choisir un nombre de participants pour un événement (de 1 à 100). Le `Spinbox` est idéal car il permet une saisie rapide avec les flèches, tout en limitant les erreurs (pas besoin d'ouvrir une longue liste comme avec une `Combobox`). Je configurerais `from_=1`, `to=100`, `wrap=False`, et ajouterais un bouton de validation pour récupérer la valeur avec `get()`.**

