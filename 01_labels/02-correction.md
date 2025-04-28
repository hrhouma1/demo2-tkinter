# **Quiz – Compréhension du script Tkinter**

## Instructions
- Répondez sérieusement à chaque question.
- Vous pouvez consulter vos notes, mais essayez d'abord sans aide.

---

## **Partie 1 – Questions à Choix Multiples (QCM)**

**1.** Quel module est utilisé pour créer des widgets modernes dans ce script ?
- a) `tkinter`
- b) `ttk`
- c) `ctypes`
- d) `PIL`

**2.** Quelle est la fonction de `windll.shcore.SetProcessDpiAwareness(1)` dans ce programme ?
- a) Créer une nouvelle fenêtre.
- b) Gérer les événements clavier.
- c) Améliorer la netteté de l'interface sous Windows haute résolution.
- d) Modifier la taille du texte.

**3.** Quelle méthode empêche la fenêtre de changer de taille ?
- a) `root.resize(False, False)`
- b) `root.block(False, False)`
- c) `root.resizable(False, False)`
- d) `root.locksize(False, False)`

**4.** Pour afficher une image dans un `Label`, laquelle des bibliothèques est utilisée ?
- a) OpenCV
- b) Pillow
- c) Matplotlib
- d) NumPy

**5.** Quel paramètre permet d'afficher du texte **et** une image dans un même label ?
- a) `align`
- b) `side`
- c) `compound`
- d) `attach`

---

## **Partie 2 – Questions Vrai ou Faux**

**6.** Le script utilise `try/except` pour empêcher une erreur sur des systèmes non-Windows.  
**Répondez :** Vrai / Faux

**7.** `StringVar()` est utilisée pour modifier dynamiquement le style graphique d'un label.  
**Répondez :** Vrai / Faux

**8.** Sans `root.mainloop()`, la fenêtre se fermerait immédiatement après sa création.  
**Répondez :** Vrai / Faux

---

## **Partie 3 – Réponses Courtes**

**9.** Expliquez en une phrase l'objectif de `label.pack()`.

**10.** Quelle est la différence entre `text="Hello"` et `textvariable=greeting` dans un Label ?

---

## **Partie 4 – Question de Réflexion**

**11.** Supposons que l’image `"test_image.png"` n’existe pas dans le dossier.  
Que se passe-t-il ? Que proposeriez-vous pour éviter que le programme plante ?

---

# **Barème proposé**

| Partie | Points |
|:------|------:|
| QCM (5 questions) | 10 points |
| Vrai/Faux (3 questions) | 6 points |
| Réponses courtes (2 questions) | 8 points |
| Question de réflexion (1 question) | 6 points |
| **Total** | **30 points** |

---

# **Corrigé du Quiz**

## Partie 1 – QCM
1. **b) ttk**  
2. **c) Améliorer la netteté sous Windows haute résolution**  
3. **c) root.resizable(False, False)**  
4. **b) Pillow**  
5. **c) compound**

## Partie 2 – Vrai/Faux
6. **Vrai**  
7. **Faux** (`StringVar` modifie **le contenu texte**, pas le style graphique)  
8. **Vrai**

## Partie 3 – Réponses courtes
9. **`label.pack()` sert à ajouter le widget `Label` dans la fenêtre et à demander son affichage.**  
10. **`text="Hello"` fixe un texte statique lors de la création du label, alors que `textvariable=greeting` lie dynamiquement le texte à une variable qui peut être modifiée après.**

## Partie 4 – Réflexion
11. **Le script lèverait une erreur `FileNotFoundError` car l'image n'existe pas. Pour éviter cela, il faudrait ajouter un `try/except` autour du `Image.open()`, et afficher un message d'erreur ou un contenu alternatif.**

---

#  **Mini-TP complémentaire**

**Objectif** : Ajoutez un bouton qui ferme l'application !

- Ajoutez ce code avant `root.mainloop()` :

```python
def close_window():
    root.destroy()

exit_button = ttk.Button(root, text="Quitter", command=close_window)
exit_button.pack(pady=10)
```

**Consignes** :
- Le bouton doit avoir pour texte `Quitter`.
- Lorsqu'on clique dessus, la fenêtre se ferme proprement.

