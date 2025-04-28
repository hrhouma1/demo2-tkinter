# Cours : Utilisation de Checkbuttons dans Tkinter

---

## 1. Importation des modules nécessaires

```python
import tkinter as tk
from tkinter import ttk
```
- `tkinter` : bibliothèque standard de Python pour créer des interfaces graphiques (GUI).
- `ttk` : module complémentaire fournissant des widgets plus modernes et esthétiques.

---

## 2. Configuration spécifique à Windows

```python
try:
    from ctypes import windll
    windll.shcore.SetProcessDpiAwareness(1)
except:
    pass
```
- Permet d'améliorer la netteté d'affichage sous Windows sur les écrans haute densité (High DPI).
- Utilisation de `ctypes` pour appeler une fonction native Windows.
- Si la fonction n'est pas disponible, aucune erreur bloquante n'est levée grâce au bloc `try/except`.

---

## 3. Création de la fenêtre principale

```python
root = tk.Tk()
```
- Initialise la fenêtre principale de l'application.

```python
root.title("Widget Examples")
```
- Définit le titre affiché dans la barre de la fenêtre principale.

---

## 4. Création d'un premier Checkbutton

```python
check_button = ttk.Checkbutton(root, text="Check me!")
check_button.pack()
```
- Crée un widget `Checkbutton`, qui est une case à cocher (checkbox).
- `text="Check me!"` définit le texte affiché à côté de la case à cocher.
- `pack()` affiche ce widget dans la fenêtre principale.

```python
check_button["state"] = "disabled"
```
- Change l'état du bouton pour le rendre désactivé (`disabled`), ce qui empêche l'utilisateur de cocher ou décocher la case.
- L'état par défaut est `"normal"`, permettant l'interaction.

---

## 5. Introduction à la gestion d'état avec `variable`

Pour exploiter pleinement un `Checkbutton`, il est courant d'associer une variable (`StringVar`, `IntVar`, `BooleanVar`, etc.) qui garde en mémoire l'état de la case (cochée ou décochée).

---

## 6. Déclaration d'une variable associée

```python
selected_option = tk.StringVar()
```
- Crée une variable de type `StringVar`.
- Cette variable stockera la valeur actuelle de la case (par exemple `"On"` ou `"Off"`).

---

## 7. Définition d'une fonction de rappel (callback)

```python
def print_current_option():
    print(selected_option.get())
```
- Déclare une fonction appelée lors d'un changement d'état du bouton.
- Cette fonction récupère et affiche la valeur de la variable associée.

---

## 8. Création d'un Checkbutton dynamique

```python
check = tk.Checkbutton(
    root,
    text="Check Example",
    variable=selected_option,
    command=print_current_option,
    onvalue="On",
    offvalue="Off"
)
```
- Crée un `Checkbutton` classique (non `ttk` cette fois).
- `text="Check Example"` : définit le texte affiché à côté de la case.
- `variable=selected_option` : associe la variable `selected_option` à la case à cocher.
- `command=print_current_option` : précise la fonction à appeler chaque fois que l'utilisateur change l'état de la case.
- `onvalue="On"` : valeur que la variable prendra lorsque la case est cochée.
- `offvalue="Off"` : valeur que la variable prendra lorsque la case est décochée.

```python
check.pack()
```
- Affiche le `Checkbutton` dans la fenêtre.

---

## 9. Lancement de la boucle principale

```python
root.mainloop()
```
- Lance la boucle principale de l'application graphique.
- La fenêtre reste active jusqu'à ce que l'utilisateur la ferme.

---

# Résumé général

| Étape | Description |
|:---|:---|
| Importation | Chargement de `tkinter` et `ttk` |
| Configuration Windows | Correction de l'affichage sur écrans haute résolution |
| Création de la fenêtre | Initialisation de la fenêtre principale |
| Création d'un Checkbutton simple | Affichage d'une case à cocher désactivée |
| Création d'un Checkbutton dynamique | Case à cocher associée à une variable et déclenchant une fonction |
| Boucle principale | Maintien de la fenêtre ouverte et gestion des événements |

---

# Notes pédagogiques complémentaires

- `Checkbutton` permet de sélectionner ou désélectionner une option, contrairement à un bouton simple (`Button`).
- L'utilisation d'une variable (`StringVar`, `IntVar`, etc.) est indispensable pour capturer et utiliser l'état du `Checkbutton`.
- Le paramètre `command` permet de réagir immédiatement à une action utilisateur sans nécessiter d'autre événement.
- `onvalue` et `offvalue` permettent de définir les valeurs enregistrées selon que l'option est activée ou non.

---

# Remarques sur l'usage des `ttk.Checkbutton` et `tk.Checkbutton`

- `ttk.Checkbutton` : a une apparence plus moderne et suit le style graphique du système d'exploitation.
- `tk.Checkbutton` : style plus brut, moins intégré à l'apparence du système.
- Les deux peuvent être utilisés selon les besoins, mais il est recommandé d'utiliser `ttk` pour des applications professionnelles.

