

# Cours : Utilisation d'une Listbox dans Tkinter

---

## 1. Importation des modules nécessaires

```python
import tkinter as tk
from tkinter import ttk
```
- `tkinter` : bibliothèque standard de Python pour la création d'interfaces graphiques (GUI).
- `ttk` : module complémentaire fournissant des widgets modernes avec une apparence native du système d'exploitation.

---

## 2. Configuration spécifique pour Windows

```python
try:
    from ctypes import windll
    windll.shcore.SetProcessDpiAwareness(1)
except:
    pass
```
- Améliore la netteté de l'affichage sous Windows pour les écrans haute densité (High DPI).
- Utilise la bibliothèque `ctypes` pour ajuster l'affichage en appelant la fonction système `SetProcessDpiAwareness`.
- Si cette fonction n'est pas disponible, le bloc `try/except` permet au programme de continuer sans erreur.

---

## 3. Création de la fenêtre principale

```python
root = tk.Tk()
```
- Initialise la fenêtre principale de l'application.

```python
root.title("Widget Examples")
```
- Définit le titre de la fenêtre.

---

## 4. Définition de la liste des éléments

```python
programming_languages = ("C", "Go", "JavaScript", "Perl", "Python", "Rust")
```
- Déclare un tuple contenant plusieurs langages de programmation qui seront affichés dans la `Listbox`.

---

## 5. Création d'une variable pour la Listbox

```python
pl = tk.StringVar(value=programming_languages)
```
- Crée une variable `StringVar` contenant les éléments à afficher dans la `Listbox`.
- `value=programming_languages` initialise cette variable avec la liste de langages.

---

## 6. Création et configuration de la Listbox

```python
pl_select = tk.Listbox(root, listvariable=pl, height=6)
```
- Crée une `Listbox`, qui est un widget d'affichage d'une liste de choix multiples.
- `listvariable=pl` relie la liste à la variable contenant les langages de programmation.
- `height=6` définit que 6 lignes seront visibles sans nécessiter de défilement.

```python
pl_select.pack(padx=10, pady=10)
```
- Affiche la `Listbox` dans la fenêtre principale avec des marges intérieures (`padx` et `pady` de 10 pixels).

---

## 7. Définition du mode de sélection

```python
pl_select["selectmode"] = "extended"
```
- Définit le mode de sélection à `extended`, permettant :
  - Sélection d'un ou plusieurs éléments consécutifs ou non en utilisant `Ctrl` ou `Shift`.
- Le mode alternatif est `browse`, qui limite l'utilisateur à une seule sélection à la fois.

---

## 8. Définition de la fonction de gestion de sélection

```python
def handle_selection_change(event):
    selected_indices = pl_select.curselection()
    for i in selected_indices:
        print(pl_select.get(i))
```
- Fonction appelée à chaque modification de la sélection.
- `curselection()` retourne les indices des éléments sélectionnés.
- Pour chaque indice, `get(i)` permet de récupérer l'élément correspondant et l'affiche dans la console.

---

## 9. Liaison de l'événement de sélection

```python
pl_select.bind("<<ListboxSelect>>", handle_selection_change)
```
- Lie l'événement `<<ListboxSelect>>` à la fonction `handle_selection_change`.
- Chaque fois que l'utilisateur change la sélection, cette fonction est automatiquement appelée.

---

## 10. Lancement de la boucle principale

```python
root.mainloop()
```
- Lance la boucle principale qui maintient la fenêtre ouverte et traite les événements utilisateur.

---

# Résumé général

| Étape | Description |
|:---|:---|
| Importation des modules | Chargement de `tkinter` et `ttk` |
| Correction affichage Windows | Amélioration de la qualité d'affichage sur écrans haute résolution |
| Création de la fenêtre principale | Fenêtre initiale avec titre défini |
| Définition de la liste d'éléments | Liste de langages de programmation |
| Création de la variable associée | Stockage des éléments pour la `Listbox` |
| Création de la Listbox | Liste déroulante affichant plusieurs éléments |
| Configuration du mode de sélection | Mode permettant des sélections multiples |
| Gestion des sélections | Fonction qui récupère et affiche les sélections |
| Liaison de l'événement | Réaction aux changements de sélection |
| Boucle principale | Maintien de la fenêtre et gestion des événements |

---

# Notes pédagogiques complémentaires

- `Listbox` permet d'afficher une liste de choix que l'utilisateur peut parcourir et sélectionner.
- `selectmode="extended"` est utile pour des sélections multiples avec `Ctrl` ou `Shift`.
- `listvariable` est la meilleure pratique pour lier un ensemble d'éléments à une `Listbox`, car il permet aussi de modifier dynamiquement la liste si nécessaire.
- L'événement `<<ListboxSelect>>` est déclenché aussi bien lors d'une sélection que d'une désélection.
