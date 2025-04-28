# **Quiz – Compréhension du script Tkinter : Utilisation d'une Listbox**

## Instructions
- Répondez sérieusement et précisément à chaque question.
- Ce quiz porte sur la création, l’utilisation et la gestion des événements d’une `Listbox`.

---

## **Partie 1 – Questions à Choix Multiples (QCM)**

**1.** Quelle variable est utilisée pour lier les éléments affichés dans la `Listbox` ?
- a) `BooleanVar`
- b) `IntVar`
- c) `StringVar`
- d) `ListVar`

**2.** Quel est le rôle de `listvariable=pl` lors de la création de la `Listbox` ?
- a) Lier dynamiquement la liste des éléments affichés
- b) Modifier la taille de la Listbox
- c) Fixer le nombre maximum de sélections possibles
- d) Limiter l'utilisateur à une seule sélection

**3.** Quelle méthode est utilisée pour obtenir les indices des éléments sélectionnés dans la `Listbox` ?
- a) `get_selection()`
- b) `curselection()`
- c) `selected_items()`
- d) `selected_indices()`

**4.** Quel est l'effet du mode `selectmode="extended"` dans la `Listbox` ?
- a) Permet uniquement la sélection d'un élément à la fois
- b) Permet la sélection multiple avec `Ctrl` ou `Shift`
- c) Interdit la sélection d'éléments
- d) Force la sélection de tous les éléments

**5.** Quel événement est déclenché lorsqu'une sélection change dans la `Listbox` ?
- a) `<<SelectionChanged>>`
- b) `<ListboxClick>`
- c) `<<ListboxSelect>>`
- d) `<SelectItem>`

---

## **Partie 2 – Questions Vrai ou Faux**

**6.** Dans ce script, la `Listbox` permet de sélectionner uniquement un élément à la fois.  
**Répondez :** Vrai / Faux

**7.** L’événement `<<ListboxSelect>>` est lié à la fonction `handle_selection_change`.  
**Répondez :** Vrai / Faux

**8.** `pl_select.get(i)` retourne le texte de l'élément correspondant à l'indice `i`.  
**Répondez :** Vrai / Faux

**9.** Lorsque la sélection change, l'application ferme automatiquement la fenêtre.  
**Répondez :** Vrai / Faux

---

## **Partie 3 – Réponses Courtes**

**10.** Expliquez le rôle de la fonction suivante :
```python
def handle_selection_change(event):
    selected_indices = pl_select.curselection()
    for i in selected_indices:
        print(pl_select.get(i))
```

**11.** Que permet l'utilisation de `padx=10, pady=10` lors du `pack()` de la `Listbox` ?

**12.** Que faudrait-il modifier pour restreindre la `Listbox` à une seule sélection possible à la fois ?

---

## **Partie 4 – Question de réflexion**

**13.** Imaginez que vous voulez créer une interface permettant à l'utilisateur de choisir ses **3 langages préférés** parmi une liste de 10 langages.  
Comment structureriez-vous votre `Listbox` et votre fonction de validation pour respecter cette contrainte (au niveau de l'affichage et du traitement) ?

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
1. **c) StringVar**  
2. **a) Lier dynamiquement la liste des éléments affichés**  
3. **b) curselection()**  
4. **b) Permet la sélection multiple avec `Ctrl` ou `Shift`**  
5. **c) <<ListboxSelect>>**

## Partie 2 – Vrai/Faux
6. **Faux** (elle est en mode `extended`)  
7. **Vrai**  
8. **Vrai**  
9. **Faux**

## Partie 3 – Réponses courtes
10. **Cette fonction récupère les indices des éléments sélectionnés et affiche pour chacun l'élément correspondant dans la console.**  
11. **`padx` et `pady` ajoutent un espace vide de 10 pixels autour de la `Listbox`, améliorant la présentation visuelle.**  
12. **Il faudrait changer `pl_select["selectmode"] = "extended"` en `pl_select["selectmode"] = "browse"`.**

## Partie 4 – Réflexion
13. **Configurer la `Listbox` en mode `extended`, limiter le nombre d'éléments sélectionnés dans la fonction de validation (en vérifiant que `len(curselection()) == 3`), sinon afficher un message d'erreur.**

