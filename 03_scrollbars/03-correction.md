# **Quiz – Compréhension du script Tkinter : Widget Text avec Scrollbar**

## Instructions
- Lisez chaque question avec attention.
- Répondez de manière précise et complète.
- Ce quiz couvre la grille (`grid`), le widget `Text`, et la `Scrollbar`.

---

## **Partie 1 – Questions à Choix Multiples (QCM)**

**1.** Quel module est utilisé pour obtenir des widgets au style moderne ?
- a) `tkinter`
- b) `PIL`
- c) `ttk`
- d) `ctypes`

**2.** Quelle est l'utilité de `windll.shcore.SetProcessDpiAwareness(1)` dans ce script ?
- a) Améliorer la fluidité de la barre de défilement
- b) Corriger l'affichage flou sur les écrans haute résolution Windows
- c) Ajouter un nouveau widget `Scrollbar`
- d) Modifier la taille de la fenêtre principale

**3.** À quoi sert la méthode `grid_columnconfigure(0, weight=1)` sur `root` ?
- a) Fixer la hauteur de la fenêtre
- b) Permettre à la colonne 0 de s’étendre horizontalement
- c) Ajouter un widget dans la colonne 0
- d) Lier une scrollbar à la colonne 0

**4.** Que signifie l'option `sticky="ew"` lors de l'utilisation de `grid` avec le widget `Text` ?
- a) Le widget est fixé à gauche uniquement
- b) Le widget s'étend verticalement
- c) Le widget s'étend horizontalement
- d) Le widget reste centré sans étirement

**5.** Quel est le rôle de la commande suivante ?
```python
text['yscrollcommand'] = text_scroll.set
```
- a) Permettre au texte d'appeler la scrollbar
- b) Synchroniser le défilement du `Text` et de la `Scrollbar`
- c) Créer un raccourci clavier
- d) Redimensionner automatiquement la zone de texte

---

## **Partie 2 – Questions Vrai ou Faux**

**6.** La grille (`grid`) permet d'organiser les widgets uniquement en lignes, pas en colonnes.  
**Répondez :** Vrai / Faux

**7.** La `Scrollbar` est connectée au widget `Text` via l'argument `command=text.yview`.  
**Répondez :** Vrai / Faux

**8.** Sans l'attribution `text['yscrollcommand'] = text_scroll.set`, la barre de défilement ne bougerait pas même si le texte est long.  
**Répondez :** Vrai / Faux

**9.** `sticky="ns"` signifie que le widget s'étire horizontalement dans sa cellule.  
**Répondez :** Vrai / Faux

---

## **Partie 3 – Réponses Courtes**

**10.** Expliquez ce que fait la commande suivante :
```python
text.grid(row=0, column=0, sticky="ew")
```

**11.** Pourquoi a-t-on besoin d'un `Scrollbar` dans ce script ?

**12.** Que permet l'instruction suivante ?
```python
root.mainloop()
```

---

## **Partie 4 – Question de réflexion**

**13.** Imaginez que vous devez adapter cette interface pour un champ de texte beaucoup plus grand (plus de 50 lignes).  
Que faudrait-il modifier pour rendre l'interface encore plus pratique pour l'utilisateur ?

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
1. **c) ttk**  
2. **b) Corriger l'affichage flou sur Windows haute résolution**  
3. **b) Permettre à la colonne 0 de s’étendre horizontalement**  
4. **c) Le widget s'étend horizontalement**  
5. **b) Synchroniser le défilement du `Text` et de la `Scrollbar`**

## Partie 2 – Vrai/Faux
6. **Faux** (la grille organise en lignes **et** colonnes)  
7. **Vrai**  
8. **Vrai**  
9. **Faux** (sticky="ns" signifie extension **verticale**, pas horizontale)

## Partie 3 – Réponses courtes
10. **Elle place le widget `Text` dans la cellule (ligne 0, colonne 0) de la grille et l'étire horizontalement.**  
11. **Parce que si le texte dépasse la taille visible du widget `Text`, l'utilisateur doit pouvoir défiler pour lire tout le contenu.**  
12. **Elle lance la boucle principale de Tkinter pour afficher l'interface et traiter les actions utilisateur.**

## Partie 4 – Réflexion
13. **Il faudrait augmenter la hauteur du widget `Text` (par exemple `height=20` ou `height=30`), peut-être ajouter également une barre de défilement horizontale (`orient="horizontal"`) si nécessaire, et configurer `sticky="nsew"` pour un étirement dans toutes les directions.**

