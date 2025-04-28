
# Cours : Utilisation des Radiobuttons dans Tkinter

---

## 1. Importation des modules nécessaires

```python
import tkinter as tk
from tkinter import ttk
```
- `tkinter` : bibliothèque standard de Python pour créer des interfaces graphiques (GUI).
- `ttk` : sous-module de `tkinter` proposant des widgets modernes, harmonisés avec le style du système d'exploitation.

---

## 2. Configuration spécifique pour Windows

```python
try:
    from ctypes import windll
    windll.shcore.SetProcessDpiAwareness(1)
except:
    pass
```
- Améliore la netteté d'affichage sous Windows sur les écrans haute densité (High DPI).
- Utilisation de la bibliothèque `ctypes` pour accéder à la fonction `SetProcessDpiAwareness`.
- Le bloc `try/except` garantit que l'application fonctionne même si cette fonction n'est pas disponible.

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

## 4. Création d'une variable de stockage

```python
storage_variable = tk.StringVar()
```
- Crée une variable `StringVar`.
- Cette variable est utilisée pour stocker la valeur de l'option sélectionnée parmi plusieurs `Radiobuttons`.
- Tous les boutons radio partagent cette même variable pour fonctionner ensemble.

---

## 5. Création de plusieurs Radiobuttons

### Premier Radiobutton

```python
option_one = ttk.Radiobutton(
    root,
    text="Option 1",
    variable=storage_variable,
    value="First option"
)
```
- Crée un bouton radio affichant le texte "Option 1".
- Ce bouton est lié à `storage_variable`.
- Lorsque l'utilisateur sélectionne ce bouton, `storage_variable` prendra la valeur `"First option"`.

### Deuxième Radiobutton

```python
option_two = ttk.Radiobutton(
    root,
    text="Option 2",
    variable=storage_variable,
    value="Second option"
)
```
- Crée un deuxième bouton radio affichant "Option 2".
- Lié à la même variable `storage_variable`.
- La valeur associée à ce bouton est `"Second option"`.

### Troisième Radiobutton

```python
option_three = ttk.Radiobutton(
    root,
    text="Option 3",
    variable=storage_variable,
    value="Third option"
)
```
- Crée un troisième bouton radio affichant "Option 3".
- Lié également à `storage_variable`.
- La valeur associée est `"Third option"`.

---

## 6. Placement des Radiobuttons dans la fenêtre

```python
option_one.pack()
option_two.pack()
option_three.pack()
```
- Les trois `Radiobuttons` sont affichés verticalement dans la fenêtre grâce au gestionnaire d'affichage `pack()`.

---

## 7. Démarrage de la boucle principale

```python
root.mainloop()
```
- Lance la boucle principale de l'application graphique.
- Attend et gère les interactions de l'utilisateur tant que la fenêtre n'est pas fermée.

---

## 8. Affichage de la sélection après la fermeture

```python
print(storage_variable.get(), "was selected.")
```
- Après la fermeture de la fenêtre, le programme affiche dans la console la valeur sélectionnée par l'utilisateur.
- Utilisation de `storage_variable.get()` pour récupérer la valeur actuelle.

---

# Résumé général

| Étape | Description |
|:---|:---|
| Importation des modules | Chargement de `tkinter` et `ttk` |
| Correction Windows DPI | Amélioration de l'affichage haute résolution |
| Création de la fenêtre principale | Initialisation avec un titre |
| Définition d'une variable partagée | Variable qui mémorise la sélection |
| Création de trois Radiobuttons | Boutons radio associés à des valeurs distinctes |
| Placement des Radiobuttons | Affichage vertical avec `pack()` |
| Démarrage de la boucle | Gestion des événements de l'utilisateur |
| Affichage de la sélection | Impression en console après la fermeture de la fenêtre |

---

# Notes pédagogiques complémentaires

- **Un groupe de `Radiobuttons` partage toujours une même variable** (`StringVar`, `IntVar`, etc.).
- Lorsque l'utilisateur sélectionne un bouton, la variable prend la valeur définie par le paramètre `value` de ce bouton.
- Un seul `Radiobutton` peut être sélectionné à la fois dans un même groupe lié par la même variable.
- Si plusieurs groupes indépendants sont nécessaires, il suffit d'utiliser plusieurs variables différentes.

---

# Observations importantes

- `ttk.Radiobutton` est utilisé ici pour bénéficier d'une apparence visuelle plus intégrée au système d'exploitation.
- Le `print()` après `mainloop()` ne s'exécute qu'une fois que la fenêtre est fermée, car `mainloop()` est une boucle bloquante.
