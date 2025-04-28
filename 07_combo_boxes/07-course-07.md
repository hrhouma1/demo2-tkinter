
# Cours : Utilisation des Combobox dans Tkinter

---

## 1. Importation des modules nécessaires

```python
import tkinter as tk
from tkinter import ttk
```
- `tkinter` : bibliothèque standard de Python pour la création d'interfaces graphiques (GUI).
- `ttk` : extension moderne de `tkinter` fournissant des widgets avec un style plus esthétique et natif.

---

## 2. Configuration spécifique pour Windows

```python
try:
    from ctypes import windll
    windll.shcore.SetProcessDpiAwareness(1)
except:
    pass
```
- Améliore l'affichage sous Windows sur les écrans haute densité (High DPI).
- Utilise `ctypes` pour appeler une fonction native (`SetProcessDpiAwareness`) qui ajuste l'affichage.
- En cas d'indisponibilité, l'erreur est ignorée sans interrompre le programme.

---

## 3. Création de la fenêtre principale

```python
root = tk.Tk()
```
- Initialise la fenêtre principale de l'application graphique.

```python
root.title("Widget Examples")
```
- Définit le titre de la fenêtre.

---

## 4. Création d'une variable associée à la Combobox

```python
selected_weekday = tk.StringVar()
```
- Crée une variable `StringVar` qui servira à stocker la valeur actuellement sélectionnée dans la `Combobox`.

---

## 5. Création et configuration de la Combobox

```python
weekday = ttk.Combobox(root, textvariable=selected_weekday)
```
- Crée une `Combobox`, un menu déroulant permettant à l'utilisateur de choisir une valeur parmi plusieurs options.
- La sélection est liée à `selected_weekday`, ce qui permet de récupérer ou de modifier le choix de l'utilisateur.

```python
weekday["values"] = ("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
```
- Définit les options disponibles dans la liste déroulante.

```python
weekday["state"] = "readonly"
```
- Rend la `Combobox` en mode lecture seule (`readonly`).
- L'utilisateur doit obligatoirement choisir parmi les valeurs proposées et ne peut pas saisir un texte libre.
- Le mode alternatif serait `"normal"`, qui permettrait la saisie libre.

```python
weekday.pack()
```
- Affiche la `Combobox` dans la fenêtre principale à l'aide du gestionnaire d'affichage `pack()`.

---

## 6. Définition de la fonction de gestion d'événements

```python
def handle_selection(event):
    print("Today is", weekday.get())
    print("But we're gonna change it to Friday.")
    weekday.set("Friday")
    print(weekday.current())
```
- Fonction appelée lorsqu'une sélection est faite dans la `Combobox`.
- Étapes réalisées par cette fonction :
  1. Affiche dans la console la valeur actuellement sélectionnée.
  2. Change la sélection pour "Friday" en utilisant `weekday.set("Friday")`.
  3. Affiche dans la console l'index de la valeur actuelle avec `weekday.current()`.
     - Si la valeur n'est pas dans la liste prédéfinie, `current()` peut retourner `-1`.

---

## 7. Association d'un événement à la Combobox

```python
weekday.bind("<<ComboboxSelected>>", handle_selection)
```
- Lie l'événement `<<ComboboxSelected>>` à la fonction `handle_selection`.
- Chaque fois que l'utilisateur sélectionne un jour, la fonction est automatiquement appelée.

---

## 8. Lancement de la boucle principale

```python
root.mainloop()
```
- Lance la boucle principale de l'application graphique.
- Attend et traite les actions de l'utilisateur jusqu'à la fermeture de la fenêtre.

---

## 9. Affichage du résultat après la fermeture de la fenêtre

```python
print(selected_weekday.get(), "was selected.")
```
- Après la fermeture de la fenêtre, le script affiche dans la console la valeur stockée dans `selected_weekday`.
- Cela correspond à la dernière sélection effectuée.

---

# Résumé général

| Étape | Description |
|:---|:---|
| Importation des modules | Chargement de `tkinter` et `ttk` |
| Configuration DPI Windows | Optimisation de l'affichage haute résolution |
| Création de la fenêtre principale | Initialisation avec un titre |
| Création de la variable associée | Variable pour stocker la sélection de la `Combobox` |
| Création de la Combobox | Liste déroulante avec des jours de la semaine |
| Définition de la fonction d'événement | Fonction qui réagit aux sélections et modifie la valeur |
| Association de l'événement | Liaison de la sélection de la `Combobox` à la fonction |
| Boucle principale | Maintien de la fenêtre ouverte et gestion des événements |
| Affichage final | Impression de la sélection après la fermeture de la fenêtre |

---

# Notes pédagogiques complémentaires

- `Combobox` est un widget essentiel pour limiter l'entrée utilisateur à un ensemble prédéfini de choix.
- Utiliser `state="readonly"` est une bonne pratique pour éviter les erreurs de saisie par l'utilisateur.
- La méthode `set()` permet de modifier dynamiquement la valeur de la `Combobox`.
- L'événement `<<ComboboxSelected>>` se déclenche uniquement lorsque l'utilisateur sélectionne une option dans la liste.
- `current()` retourne l'index de la sélection, ce qui est utile pour manipuler les options sous forme d'indices.


