# **Quiz – Compréhension du script Tkinter : Utilisation des Checkbuttons**

## Instructions
- Répondez avec précision.
- Ce quiz couvre la création de Checkbuttons, la gestion d'état via `StringVar`, et l'utilisation des callbacks (`command`).

---

## **Partie 1 – Questions à Choix Multiples (QCM)**

**1.** Quel module propose des widgets modernes adaptés au style du système d’exploitation ?
- a) `tk`
- b) `ttk`
- c) `ctypes`
- d) `windll`

**2.** Quelle est l'utilité de la commande `check_button["state"] = "disabled"` ?
- a) Activer le bouton
- b) Désactiver l'interaction avec la case à cocher
- c) Supprimer la case à cocher
- d) Modifier son apparence graphique

**3.** Quel type de variable est utilisé pour suivre l'état d'un `Checkbutton` dans cet exemple ?
- a) `IntVar`
- b) `DoubleVar`
- c) `BooleanVar`
- d) `StringVar`

**4.** Que signifie le paramètre `onvalue="On"` dans le `Checkbutton` dynamique ?
- a) La valeur par défaut est "On"
- b) Lorsque la case est cochée, la variable associée prend la valeur "On"
- c) Le texte affiché devient "On"
- d) Le bouton passe en mode lecture seule

**5.** Quelle commande permet d'exécuter une fonction automatiquement lorsqu'un utilisateur clique sur un `Checkbutton` ?
- a) `command=print_current_option`
- b) `onclick=print_current_option`
- c) `action=print_current_option`
- d) `trigger=print_current_option`

---

## **Partie 2 – Questions Vrai ou Faux**

**6.** Le script utilise à la fois un `ttk.Checkbutton` et un `tk.Checkbutton`.  
**Répondez :** Vrai / Faux

**7.** La variable associée au `Checkbutton` est modifiée uniquement à la fermeture de la fenêtre.  
**Répondez :** Vrai / Faux

**8.** `offvalue` détermine la valeur stockée lorsque la case est décochée.  
**Répondez :** Vrai / Faux

**9.** Le widget `Checkbutton` peut afficher plusieurs options côte à côte automatiquement.  
**Répondez :** Vrai / Faux

---

## **Partie 3 – Réponses Courtes**

**10.** Expliquez le rôle de la fonction suivante :
```python
def print_current_option():
    print(selected_option.get())
```

**11.** Pourquoi est-il utile d'associer une variable (`StringVar`, `IntVar`) à un `Checkbutton` ?

**12.** Quelle est la différence principale entre un `ttk.Checkbutton` et un `tk.Checkbutton` ?

---

## **Partie 4 – Question de réflexion**

**13.** Imaginez une interface graphique permettant de choisir plusieurs préférences utilisateur (ex : "Recevoir des emails", "Activer les notifications", "Accepter les conditions").  
Comment utiliseriez-vous plusieurs `Checkbutton` pour gérer ces choix et récupérer leur état efficacement ?

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
2. **b) Désactiver l'interaction avec la case à cocher**  
3. **d) StringVar**  
4. **b) Lorsque la case est cochée, la variable associée prend la valeur "On"**  
5. **a) command=print_current_option**

## Partie 2 – Vrai/Faux
6. **Vrai**  
7. **Faux** (la variable est modifiée dès que l'utilisateur interagit)  
8. **Vrai**  
9. **Faux** (chaque `Checkbutton` est indépendant, il faut les placer manuellement)

## Partie 3 – Réponses courtes
10. **Elle affiche dans la console la valeur actuelle de la variable associée au `Checkbutton`.**  
11. **Pour pouvoir récupérer et utiliser l'état (coché/décoché) programmatique du `Checkbutton`.**  
12. **`ttk.Checkbutton` a un style plus moderne et suit l'apparence du système d'exploitation, alors que `tk.Checkbutton` a un style plus basique.**

## Partie 4 – Réflexion
13. **Il faudrait créer un `Checkbutton` pour chaque préférence, chacun lié à une variable (`BooleanVar` ou `StringVar`), puis lire ces variables au moment de la validation pour savoir quelles options ont été sélectionnées.**
