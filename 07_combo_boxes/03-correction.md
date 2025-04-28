

# **Quiz – Compréhension du script Tkinter : Utilisation de la Combobox**

## Instructions
- Répondez de manière précise et complète.
- Ce quiz évalue votre compréhension de l’utilisation d’une `Combobox`, de la gestion d’événements, et de la manipulation de sélection utilisateur.

---

## **Partie 1 – Questions à Choix Multiples (QCM)**

**1.** Quel type de variable est utilisée pour stocker la sélection d'une `Combobox` ?
- a) `IntVar`
- b) `BooleanVar`
- c) `StringVar`
- d) `DoubleVar`

**2.** À quoi sert le paramètre `state="readonly"` dans la `Combobox` ?
- a) Empêcher toute interaction avec la Combobox
- b) Permettre à l'utilisateur de saisir n'importe quel texte
- c) Forcer l'utilisateur à choisir parmi les options proposées
- d) Supprimer les options existantes

**3.** Quel événement est associé à une sélection dans une `Combobox` ?
- a) `<ButtonClick>`
- b) `<SelectChanged>`
- c) `<<ComboboxSelected>>`
- d) `<ValueChanged>`

**4.** Quelle méthode est utilisée pour récupérer la valeur actuellement sélectionnée dans une `Combobox` ?
- a) `weekday.get()`
- b) `weekday.select()`
- c) `weekday.choice()`
- d) `weekday.pick()`

**5.** Que fait la méthode `weekday.set("Friday")` dans le script ?
- a) Ajoute "Friday" aux options disponibles
- b) Sélectionne "Friday" comme nouvelle valeur dans la `Combobox`
- c) Supprime "Friday" des choix
- d) Réinitialise la Combobox

---

## **Partie 2 – Questions Vrai ou Faux**

**6.** La `Combobox` créée dans ce script autorise l'utilisateur à écrire manuellement un jour de la semaine.  
**Répondez :** Vrai / Faux

**7.** L'événement `<<ComboboxSelected>>` est déclenché même si la sélection est modifiée par `set()`.  
**Répondez :** Vrai / Faux

**8.** La fonction `handle_selection` est appelée automatiquement lorsqu'un jour est sélectionné par l'utilisateur.  
**Répondez :** Vrai / Faux

**9.** La méthode `current()` retourne l'index de l'élément actuellement sélectionné dans la liste de la `Combobox`.  
**Répondez :** Vrai / Faux

---

## **Partie 3 – Réponses Courtes**

**10.** Expliquez ce que fait cette ligne :
```python
weekday["values"] = ("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
```

**11.** Pourquoi utilise-t-on `selected_weekday.get()` après `root.mainloop()` ?

**12.** Que faudrait-il modifier dans le script pour permettre à l'utilisateur d'entrer **manuellement** un jour au lieu de choisir uniquement parmi la liste déroulante ?

---

## **Partie 4 – Question de réflexion**

**13.** Imaginez une application de réservation d'activités où l'utilisateur doit choisir une **plage horaire** dans une `Combobox`.  
Comment structureriez-vous la gestion de cet élément pour à la fois limiter les choix possibles et afficher la sélection finale dans la console ?

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
1. **c) StringVar**  
2. **c) Forcer l'utilisateur à choisir parmi les options proposées**  
3. **c) <<ComboboxSelected>>**  
4. **a) weekday.get()**  
5. **b) Sélectionne "Friday" comme nouvelle valeur dans la `Combobox`**

## Partie 2 – Vrai/Faux
6. **Faux** (la Combobox est en `readonly`)  
7. **Faux** (changer avec `set()` ne déclenche pas `<<ComboboxSelected>>`)  
8. **Vrai**  
9. **Vrai**

## Partie 3 – Réponses courtes
10. **Elle définit les valeurs proposées dans la `Combobox` : les jours de la semaine.**  
11. **Parce que `root.mainloop()` est bloquant ; donc l'affichage de la sélection se fait seulement après la fermeture de la fenêtre.**  
12. **Il faudrait changer l'attribut `state="readonly"` en `state="normal"`.**

## Partie 4 – Réflexion
13. **Je définirais la `Combobox` avec les différentes plages horaires ("08:00-10:00", "10:00-12:00", etc.), je la mettrais en `readonly` pour limiter les choix, puis, à la sélection, j’utiliserais un événement `<<ComboboxSelected>>` pour afficher le choix dans la console.**

