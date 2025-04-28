# **Quiz – Compréhension du script Tkinter : Utilisation d'un Scale**

## Instructions
- Répondez de manière précise et complète.
- Ce quiz vérifie votre maîtrise du widget `Scale`, de ses propriétés, et de l'interaction utilisateur.

---

## **Partie 1 – Questions à Choix Multiples (QCM)**

**1.** Quel module est utilisé dans ce script pour créer un `Scale` avec une apparence moderne ?
- a) `tk`
- b) `ttk`
- c) `ctypes`
- d) `tkmod`

**2.** Que signifie l'option `orient="horizontal"` dans la création du `Scale` ?
- a) Le curseur est affiché verticalement
- b) Le curseur est affiché horizontalement
- c) Le curseur est désactivé
- d) Le curseur utilise une couleur différente

**3.** Quel paramètre est utilisé pour spécifier la valeur maximale atteignable dans le `Scale` ?
- a) `max=10`
- b) `limit=10`
- c) `to=10`
- d) `high=10`

**4.** Quelle méthode permet de récupérer la valeur actuelle du `Scale` ?
- a) `scale.read()`
- b) `scale.get()`
- c) `scale.value()`
- d) `scale.show()`

**5.** Que se passe-t-il si l'on active `scale["state"] = "disabled"` ?
- a) Le curseur est inversé
- b) Le curseur devient invisible
- c) Le curseur ne peut plus être déplacé
- d) Le curseur redémarre à zéro

---

## **Partie 2 – Questions Vrai ou Faux**

**6.** Le curseur du `Scale` peut être déplacé uniquement si son état est `normal`.  
**Répondez :** Vrai / Faux

**7.** `set(valeur)` permet de changer la position du curseur par programmation.  
**Répondez :** Vrai / Faux

**8.** `command=handle_scale_change` permet d'exécuter la fonction `handle_scale_change` uniquement **après** avoir relâché le curseur.  
**Répondez :** Vrai / Faux

**9.** Le paramètre `fill="x"` dans `pack()` étend le `Scale` horizontalement.  
**Répondez :** Vrai / Faux

---

## **Partie 3 – Réponses Courtes**

**10.** Expliquez en une phrase le rôle de la fonction suivante :
```python
def handle_scale_change(event):
    print(scale.get())
```

**11.** Que signifie exactement `scale["state"] = "disabled"` ?

**12.** Comment modifieriez-vous le `Scale` pour qu’il s'affiche verticalement au lieu d'horizontalement ?

---

## **Partie 4 – Question de réflexion**

**13.** Imaginez que vous voulez créer un formulaire où l'utilisateur doit **noter sa satisfaction de 0 à 100** à l'aide d'un `Scale`.  
Quelles configurations précises utiliseriez-vous pour rendre cette expérience utilisateur fluide et claire ?

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
1. **b) ttk**  
2. **b) Le curseur est affiché horizontalement**  
3. **c) to=10**  
4. **b) scale.get()**  
5. **c) Le curseur ne peut plus être déplacé**

## Partie 2 – Vrai/Faux
6. **Vrai**  
7. **Vrai**  
8. **Faux** (la fonction est appelée **en temps réel** pendant le déplacement)  
9. **Vrai**

## Partie 3 – Réponses courtes
10. **Elle récupère la valeur actuelle du curseur et l'affiche dans la console chaque fois que le curseur est déplacé.**  
11. **Le curseur devient inactif : l'utilisateur ne peut plus le déplacer ni modifier sa valeur.**  
12. **Changer le paramètre `orient="horizontal"` en `orient="vertical"` dans la création du `Scale`.**

## Partie 4 – Réflexion
13. **Je créerais un `Scale` avec `from_=0`, `to=100`, `orient="horizontal"`, `length=400` pour un déplacement fluide, j'ajouterais un label affichant la valeur en temps réel avec `command=fonction_affichage`. Je configurerais aussi un espacement (`padx` et `pady`) pour plus de clarté.**

