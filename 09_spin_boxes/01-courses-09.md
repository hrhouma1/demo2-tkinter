
# Cours : Utilisation d'un Spinbox dans Tkinter

---

## 1. Importation des modules nécessaires

```python
import tkinter as tk
from tkinter import ttk
```
- `tkinter` : bibliothèque standard de Python pour créer des interfaces graphiques.
- `ttk` : sous-module de `tkinter` offrant des widgets modernes, mais ici `Spinbox` est utilisé directement via `tk`.

---

## 2. Configuration spécifique pour Windows

```python
try:
    from ctypes import windll
    windll.shcore.SetProcessDpiAwareness(1)
except:
    pass
```
- Correction de l'affichage flou sous Windows sur les écrans haute densité (High DPI).
- Utilise la bibliothèque `ctypes` pour appeler une fonction native Windows qui ajuste la gestion des pixels.

---

## 3. Création de la fenêtre principale

```python
root = tk.Tk()
```
- Initialise la fenêtre principale de l'application graphique.

```python
root.title("Widget Examples")
```
- Définit le titre affiché dans la barre de la fenêtre.

---

## 4. Définition d'une variable associée

```python
initial_value = tk.StringVar(value=20)
```
- Crée une variable `StringVar` contenant une valeur initiale fixée à `20`.
- Cette variable est associée au `Spinbox` pour stocker et suivre la valeur affichée.

---

## 5. Création et configuration du Spinbox

```python
spin_box = tk.Spinbox(
    root,
    from_=0,
    to=30,
    textvariable=initial_value,
    wrap=False)
```
- Crée un widget `Spinbox`, qui permet à l'utilisateur de choisir une valeur numérique à l'aide de petites flèches haut/bas.
- Paramètres utilisés :
  - `root` : attache le `Spinbox` à la fenêtre principale.
  - `from_=0` : valeur minimale disponible.
  - `to=30` : valeur maximale disponible.
  - `textvariable=initial_value` : relie la valeur affichée à la variable `initial_value`.
  - `wrap=False` : interdit le "retour" lorsque la valeur maximale ou minimale est atteinte (pas de boucle).

### Variante mentionnée en commentaire

```python
# spin_box = tk.Spinbox(root, values=(5, 10, 15, 20, 25, 30), textvariable=initial_value, wrap=False)
```
- En alternative, il est possible de spécifier une **liste de valeurs fixes** plutôt qu'une plage numérique avec `from_` et `to`.
- `values=(5, 10, 15, 20, 25, 30)` propose uniquement ces valeurs spécifiques.

---

## 6. Placement du Spinbox dans la fenêtre

```python
spin_box.pack()
```
- Utilise le gestionnaire d'affichage `pack()` pour insérer le `Spinbox` dans la fenêtre principale.

---

## 7. Affichage immédiat de la valeur sélectionnée

```python
print(spin_box.get())
```
- Affiche dans la console la valeur actuellement affichée par le `Spinbox`.
- Attention : cet appel est effectué **avant** le lancement de la boucle principale (`mainloop`).
- Après que la boucle commence, il faudra récupérer la valeur autrement (par exemple via un bouton).

---

## 8. Lancement de la boucle principale

```python
root.mainloop()
```
- Lance la boucle principale de l'application graphique.
- Permet de capturer les interactions de l'utilisateur et de maintenir la fenêtre ouverte jusqu'à sa fermeture.

---

# Résumé général

| Étape | Description |
|:---|:---|
| Importation des modules | Chargement de `tkinter` et `ttk` |
| Correction d'affichage Windows | Amélioration de la netteté pour les écrans haute densité |
| Création de la fenêtre principale | Initialisation et définition du titre |
| Définition de la variable associée | Stockage de la valeur sélectionnée dans un `StringVar` |
| Création du Spinbox | Sélecteur numérique avec flèches haut/bas |
| Placement dans la fenêtre | Affichage du Spinbox avec `pack()` |
| Affichage immédiat | Impression de la valeur avant `mainloop` |
| Lancement de la boucle principale | Traitement des événements utilisateur |

---

# Notes pédagogiques complémentaires

- Le widget `Spinbox` est particulièrement utile lorsque l'utilisateur doit choisir une valeur numérique dans un intervalle restreint.
- Il est possible de configurer le `Spinbox` :
  - Avec une plage (`from_` et `to`) pour des suites continues.
  - Avec une liste spécifique (`values`) pour limiter les choix.
- `wrap=True` permettrait de revenir automatiquement au début ou à la fin de la plage une fois la limite atteinte.
- `get()` récupère la valeur actuelle du `Spinbox`. Dans un contexte normal, il est préférable d'appeler `get()` **après** que l'utilisateur ait interagi avec le widget, généralement en cliquant sur un bouton de validation.

