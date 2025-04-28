# Explication détaillée du script

---

## 1. Importation des modules

```python
import tkinter as tk
from tkinter import ttk
```
- `tkinter` : bibliothèque standard de Python pour développer des interfaces graphiques.
- `ttk` : extension de `tkinter` qui propose des widgets avec un style plus moderne.

---

## 2. Configuration spécifique pour Windows

```python
try:
    from ctypes import windll
    windll.shcore.SetProcessDpiAwareness(1)
except:
    pass
```
- Cette section corrige l’affichage flou sur les écrans haute résolution sous Windows.
- `windll.shcore.SetProcessDpiAwareness(1)` demande au système de prendre en compte la densité de pixels (DPI) pour un affichage plus net.
- Le bloc `try/except` permet d’éviter les erreurs si cette configuration n'est pas disponible.

---

## 3. Création de la fenêtre principale

```python
root = tk.Tk()
```
- Initialise la fenêtre principale de l’application.

---

## 4. Configuration du système de grille

```python
root.grid_columnconfigure(0, weight=1)
root.grid_rowconfigure(0, weight=1)
```
- Prépare la fenêtre pour utiliser un **système de grille** (layout en lignes et colonnes).
- `grid_columnconfigure(0, weight=1)` : permet à la colonne 0 de prendre tout l’espace horizontal disponible.
- `grid_rowconfigure(0, weight=1)` : permet à la ligne 0 de s’étendre verticalement si nécessaire.

---

## 5. Ajout d'un widget `Text`

```python
text = tk.Text(root, height=8)
```
- Crée un widget `Text`, qui est une zone multiligne pour afficher ou saisir du texte.
- Le paramètre `height=8` définit la hauteur du widget en nombre de lignes visibles.

```python
text.grid(row=0, column=0, sticky="ew")
```
- Place le widget `Text` dans la cellule (ligne 0, colonne 0) de la grille.
- `sticky="ew"` signifie que le widget s'étirera horizontalement (East-West) pour occuper tout l'espace disponible de sa cellule.

```python
text.insert("1.0", "Please enter a comment...")
```
- Insère le texte initial "Please enter a comment..." à la position "1.0" (première ligne, premier caractère).

---

## 6. Ajout d'une barre de défilement verticale

```python
text_scroll = ttk.Scrollbar(root, orient="vertical", command=text.yview)
```
- Crée un widget `Scrollbar` orienté verticalement.
- Le paramètre `command=text.yview` signifie que la barre de défilement est liée au défilement vertical du widget `Text`.

```python
text_scroll.grid(row=0, column=1, sticky="ns")
```
- Place la barre de défilement dans la cellule (ligne 0, colonne 1) de la grille.
- `sticky="ns"` signifie que la barre de défilement s'étend verticalement (North-South) pour occuper toute la hauteur de sa cellule.

```python
text['yscrollcommand'] = text_scroll.set
```
- Permet au widget `Text` de mettre à jour automatiquement la position de la barre de défilement lorsque le contenu est parcouru.

---

## 7. Lancement de la boucle principale

```python
root.mainloop()
```
- Démarre la boucle principale de l’application.
- Cette boucle attend les actions de l’utilisateur (clics, défilements, saisies) et maintient l’interface active.

---

# Résumé général

| Étape | Description |
|:---|:---|
| Importation des modules | Chargement de `tkinter`, `ttk`, et configuration Windows |
| Création de la fenêtre principale | Initialisation de la fenêtre avec `Tk()` |
| Mise en place de la grille | Configuration de la fenêtre pour utiliser un layout en grille |
| Ajout du widget `Text` | Zone de texte multiligne placée avec `grid` |
| Ajout d'une barre de défilement | Scrollbar verticale liée au widget `Text` |
| Lancement de l'application | Démarrage de la boucle principale avec `mainloop()` |
