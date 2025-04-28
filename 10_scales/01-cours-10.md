

# Cours : Utilisation d'un Scale (curseur) dans Tkinter

---

## 1. Importation des modules nécessaires

```python
import tkinter as tk
from tkinter import ttk
```
- `tkinter` : bibliothèque standard de Python pour créer des interfaces graphiques.
- `ttk` : module complémentaire fournissant des widgets modernes et plus adaptés au style natif du système d'exploitation.

---

## 2. Configuration spécifique pour Windows

```python
try:
    from ctypes import windll
    windll.shcore.SetProcessDpiAwareness(1)
except:
    pass
```
- Corrige les problèmes d'affichage flou sous Windows sur les écrans haute densité (High DPI).
- Utilise la bibliothèque `ctypes` pour accéder à une fonction système (`SetProcessDpiAwareness`).
- Si cette fonction n'est pas disponible, le bloc `try/except` empêche l'arrêt du programme.

---

## 3. Création de la fenêtre principale

```python
root = tk.Tk()
```
- Initialise la fenêtre principale de l'application.

```python
root.title("Widget Examples")
```
- Définit le titre affiché dans la barre de la fenêtre.

---

## 4. Définition d'une fonction de gestion du changement de valeur

```python
def handle_scale_change(event):
    print(scale.get())
```
- Fonction appelée chaque fois que l'utilisateur déplace le curseur du `Scale`.
- `scale.get()` récupère la valeur actuelle du curseur et l'affiche dans la console.
- À noter : il est également possible d'utiliser `scale.set(valeur)` pour modifier la valeur du curseur de manière programmatique.

---

## 5. Création et configuration du Scale

```python
scale = ttk.Scale(root, orient="horizontal", from_=0, to=10, command=handle_scale_change)
```
- Crée un widget `Scale` utilisant `ttk` pour une apparence moderne.
- Paramètres :
  - `root` : rattache le `Scale` à la fenêtre principale.
  - `orient="horizontal"` : définit une orientation horizontale.
  - `from_=0` : valeur minimale possible.
  - `to=10` : valeur maximale possible.
  - `command=handle_scale_change` : lie les mouvements du curseur à la fonction définie précédemment.

---

## 6. Placement du Scale dans la fenêtre

```python
scale.pack(fill="x")
```
- Utilise `pack()` pour afficher le `Scale` dans la fenêtre.
- `fill="x"` permet d'étirer le curseur horizontalement sur toute la largeur disponible.

---

## 7. Remarque sur l'état du Scale

```python
# scale["state"] = "disabled"
```
- Cette ligne commentée montre comment désactiver le `Scale`.
- `state="disabled"` rend le curseur inactif et empêche toute interaction.
- L'état normal par défaut est `state="normal"`.

---

## 8. Lancement de la boucle principale

```python
root.mainloop()
```
- Démarre la boucle principale de l'application graphique.
- Permet de capturer les actions de l'utilisateur et de maintenir la fenêtre ouverte tant que nécessaire.

---

# Résumé général

| Étape | Description |
|:---|:---|
| Importation des modules | Chargement de `tkinter` et `ttk` |
| Correction d'affichage Windows | Amélioration pour les écrans haute densité |
| Création de la fenêtre principale | Initialisation de l'application |
| Définition de la fonction de gestion | Réaction au déplacement du curseur |
| Création du Scale | Curseur horizontal de 0 à 10 |
| Placement du Scale | Affichage avec extension horizontale |
| Gestion de l'état du Scale | Option de désactivation possible |
| Boucle principale | Gestion des événements utilisateur |

---

# Notes pédagogiques complémentaires

- Le widget `Scale` est utilisé pour sélectionner une valeur numérique de manière visuelle en déplaçant un curseur.
- `get()` permet de récupérer la valeur actuelle sélectionnée.
- `set(valeur)` permet de changer la valeur du curseur par programmation.
- L'événement `command` est déclenché en temps réel pendant que l'utilisateur déplace le curseur.
- Utiliser `state="disabled"` est utile lorsqu'une interaction utilisateur doit être temporairement interdite.

