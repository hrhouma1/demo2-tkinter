# **Quiz – Compréhension du script Tkinter : Labels et Separators**

## Instructions
- Répondez avec attention et précision.
- Ce quiz teste votre compréhension de la gestion d’éléments visuels (`Label`, `Separator`) et du placement avec `pack()`.

---

## **Partie 1 – Questions à Choix Multiples (QCM)**

**1.** Quel module permet d'utiliser des widgets modernes avec un style système natif ?
- a) `tk`
- b) `ttk`
- c) `tktools`
- d) `windll`

**2.** Quel est le rôle de `windll.shcore.SetProcessDpiAwareness(1)` dans ce script ?
- a) Ajouter un label supplémentaire
- b) Lancer la boucle principale
- c) Améliorer l'affichage sur écrans haute résolution sous Windows
- d) Ajouter un effet de flou volontaire aux widgets

**3.** Que permet de faire l'option `fill="x"` avec `pack()` appliqué à un `Separator` ?
- a) Remplir l'espace verticalement
- b) Remplir l'espace horizontalement
- c) Centrer le séparateur dans la fenêtre
- d) Agrandir le texte

**4.** Que se passe-t-il si l'on retire l'option `fill="x"` du séparateur ?
- a) Il disparaît complètement
- b) Il occupe uniquement une petite longueur horizontale
- c) Il devient vertical
- d) Il se transforme en `Label`

**5.** Quel est le gestionnaire utilisé pour placer les widgets dans ce script ?
- a) `grid()`
- b) `place()`
- c) `pack()`
- d) `flow()`

---

## **Partie 2 – Questions Vrai ou Faux**

**6.** Le premier label et le deuxième label sont différents dans leur texte affiché.  
**Répondez :** Vrai / Faux

**7.** Le séparateur est placé entre les deux labels.  
**Répondez :** Vrai / Faux

**8.** `root.mainloop()` est nécessaire pour que l'application graphique reste visible et interactive.  
**Répondez :** Vrai / Faux

**9.** Le widget `Separator` est destiné à afficher du texte entre deux widgets.  
**Répondez :** Vrai / Faux

---

## **Partie 3 – Réponses Courtes**

**10.** À quoi sert la commande suivante ?
```python
main_sep = ttk.Separator(root, orient="horizontal")
```

**11.** Pourquoi utiliser `pack(fill="x")` pour un `Separator` ?

**12.** Quelle est la différence fondamentale entre un `Label` et un `Separator` ?

---

## **Partie 4 – Question de réflexion**

**13.** Supposons que vous souhaitez séparer trois sections distinctes dans une interface graphique complexe.  
Comment utiliseriez-vous `Separator` pour rendre l'interface plus claire visuellement ? (Décrivez brièvement.)

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
1. **b) ttk**  
2. **c) Améliorer l'affichage sur écrans haute résolution sous Windows**  
3. **b) Remplir l'espace horizontalement**  
4. **b) Il occupe uniquement une petite longueur horizontale**  
5. **c) pack()**

## Partie 2 – Vrai/Faux
6. **Faux** (le texte est le même : `"Hello, World!"`)  
7. **Vrai**  
8. **Vrai**  
9. **Faux** (le `Separator` ne sert pas à afficher du texte)

## Partie 3 – Réponses courtes
10. **Créer un séparateur horizontal pour organiser visuellement l'interface.**  
11. **Pour que le séparateur s'étende sur toute la largeur disponible et marque visuellement une séparation claire.**  
12. **Un `Label` est utilisé pour afficher du texte, tandis qu'un `Separator` est un élément purement visuel sans texte, servant à séparer les zones de l'interface.**

## Partie 4 – Réflexion
13. **On pourrait insérer un `Separator` après chaque section principale (par exemple, après chaque groupe de widgets), avec `pack(fill="x")` pour qu'ils s'étendent entièrement, afin de rendre les différentes sections distinctes et plus lisibles pour l'utilisateur.**

