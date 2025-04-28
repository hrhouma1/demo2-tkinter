# **Quiz – Compréhension du script Tkinter : Widget Text**

## Instructions
- Répondez à chaque question avec précision.
- Lisez attentivement avant de répondre.
- Ce quiz évalue votre compréhension du widget `Text` et du fonctionnement général de Tkinter.

---

## **Partie 1 – Questions à Choix Multiples (QCM)**

**1.** Quel module fournit des widgets au style plus moderne en complément de Tkinter ?
- a) `ctypes`
- b) `windll`
- c) `ttk`
- d) `PIL`

**2.** Quelle est la fonction de `windll.shcore.SetProcessDpiAwareness(1)` ?
- a) Fermer l'application proprement
- b) Améliorer la netteté de l'affichage sur Windows
- c) Ouvrir une image dans Tkinter
- d) Modifier la taille d'un widget Text

**3.** Quelle commande interdit à l'utilisateur de redimensionner la fenêtre ?
- a) `root.fixed()`
- b) `root.resizable(False, False)`
- c) `root.resize(0, 0)`
- d) `root.locked(True)`

**4.** À quoi sert la méthode `insert()` du widget `Text` ?
- a) Récupérer le texte contenu dans le widget
- b) Modifier la police du texte
- c) Insérer du texte à une position spécifique
- d) Désactiver la zone de texte

**5.** Que signifie la position `"1.0"` dans un widget `Text` ?
- a) Ligne 1, caractère 1
- b) Ligne 0, caractère 1
- c) Ligne 1, caractère 0
- d) Ligne 0, caractère 0

---

## **Partie 2 – Questions Vrai ou Faux**

**6.** Le widget `Text` permet de saisir du texte sur une seule ligne uniquement.  
**Répondez :** Vrai / Faux

**7.** La syntaxe des positions dans un widget `Text` est sous la forme "ligne.caractère".  
**Répondez :** Vrai / Faux

**8.** Lorsque le widget `Text` est en mode `disabled`, il est toujours possible d'ajouter du texte depuis l'interface graphique.  
**Répondez :** Vrai / Faux

**9.** La méthode `get("1.0", "end")` permet de lire tout le contenu de la zone de texte.  
**Répondez :** Vrai / Faux

---

## **Partie 3 – Réponses Courtes**

**10.** Expliquez ce que fait la commande suivante :
```python
text["state"] = "disabled"
```

**11.** Que se passe-t-il si on insère du texte dans un widget `Text` sans préciser de position (par exemple en oubliant `"1.0"`) ?

**12.** Quelle est l'utilité de la commande suivante dans le script ?
```python
root.mainloop()
```

---

## **Partie 4 – Question de réflexion**

**13.** Proposez un scénario concret (petite application) où l'utilisation d'un widget `Text` serait utile, et expliquez pourquoi il serait nécessaire de désactiver (`disabled`) cette zone de texte après insertion.

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
2. **b) Améliorer la netteté de l'affichage sur Windows**  
3. **b) root.resizable(False, False)**  
4. **c) Insérer du texte à une position spécifique**  
5. **c) Ligne 1, caractère 0**

## Partie 2 – Vrai/Faux
6. **Faux** (le widget `Text` permet plusieurs lignes)  
7. **Vrai**  
8. **Faux** (en mode `disabled`, aucune saisie n'est possible par l'utilisateur)  
9. **Vrai**

## Partie 3 – Réponses courtes
10. **La commande `text["state"] = "disabled"` rend la zone de texte non éditable par l'utilisateur.**  
11. **L'insertion échoue car Tkinter nécessite toujours une position pour insérer dans un widget `Text`.**  
12. **La commande `root.mainloop()` lance la boucle principale qui maintient la fenêtre ouverte et traite les événements utilisateur.**

## Partie 4 – Réflexion
13. **Exemple : Dans un formulaire de feedback client, on pourrait afficher un message de confirmation ("Merci pour votre commentaire !") dans une zone `Text` désactivée pour éviter toute modification par l'utilisateur après soumission.**

