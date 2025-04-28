# Explication détaillée du script

---

## 1. Importation des modules

```python
import tkinter as tk
from tkinter import ttk
```
- `tkinter` : bibliothèque standard de Python pour créer des interfaces graphiques (GUI).
- `ttk` : module complémentaire de `tkinter` proposant des widgets modernes.

---

## 2. Configuration spécifique à Windows

```python
try:
    from ctypes import windll
    windll.shcore.SetProcessDpiAwareness(1)
except:
    pass
```
- Sous Windows, les applications tkinter peuvent apparaître floues sur les écrans haute résolution (High DPI).
- Cette section utilise la bibliothèque `ctypes` pour appeler une fonction système Windows (`SetProcessDpiAwareness`) qui améliore la netteté de l'affichage.
- Si l'import ou l'appel échoue (par exemple sur un système non-Windows), l'erreur est ignorée grâce au bloc `try/except`.

---

## 3. Création de la fenêtre principale

```python
root = tk.Tk()
```
- Crée la fenêtre principale de l'application.

```python
root.resizable(False, False)
```
- Empêche l'utilisateur de redimensionner la fenêtre, ni horizontalement ni verticalement.

```python
root.title("Widget Examples")
```
- Définit le titre affiché dans la barre de la fenêtre.

---

## 4. Ajout d'un label de texte

```python
label = ttk.Label(root, text="Hello, World!", padding=20)
```
- Crée un widget `Label` affichant le texte "Hello, World!" avec un espacement interne (padding) de 20 pixels.

```python
label.config(font=("Segoe UI", 20))
```
- Modifie la police du texte pour utiliser "Segoe UI" avec une taille de 20 points. Cela pourrait également être défini lors de la création du label.

```python
label.pack()
```
- Utilise la méthode `pack()` pour ajouter le label dans la fenêtre principale et l'afficher.

---

## 5. Ajout d'un label avec une image

```python
from PIL import Image, ImageTk
```
- Importe `PIL` (Pillow), une bibliothèque externe qui permet de manipuler et d'afficher des images avec tkinter.

```python
image = Image.open("test_image.png")
```
- Ouvre l'image "test_image.png" située dans le même dossier que le script.

```python
photo = ImageTk.PhotoImage(image)
```
- Convertit l'image pour qu'elle soit compatible avec les widgets tkinter.

```python
ttk.Label(root, image=photo, padding=5).pack()
```
- Crée et affiche un `Label` contenant l'image, avec un padding de 5 pixels.

---

## 6. Remarque sur la modification dynamique d'une image

```python
# label["image"] = photo
```
- Cette ligne montre comment on pourrait changer dynamiquement l'image affichée dans un label existant en modifiant son attribut `image`.

---

## 7. Création d'un label avec texte dynamique

```python
greeting = tk.StringVar()
```
- Crée une variable `StringVar`, utilisée pour lier dynamiquement du texte à un widget.

```python
label = ttk.Label(root, padding=10)
```
- Crée un nouveau label sans texte initial.

```python
label["textvariable"] = greeting
```
- Associe le texte du label à la variable `greeting`.

```python
greeting.set("Hello, John!")
```
- Définit la valeur de `greeting` à "Hello, John!". Lorsque cette valeur change, le label se met automatiquement à jour.

```python
label.pack()
```
- Affiche ce label dans la fenêtre.

---

## 8. Combinaison d'une image et d'un texte dans un même label

```python
text_image = Image.open("test_image.png")
text_photo = ImageTk.PhotoImage(text_image)
```
- Ouvre de nouveau l'image et la convertit pour une nouvelle utilisation.

```python
ttk.Label(root, text="Image with text.", image=text_photo, padding=5, compound="right").pack()
```
- Crée un label combinant une image et du texte.
- L'option `compound="right"` signifie que l'image sera affichée à droite du texte.

---

## 9. Lancement de la boucle principale

```python
root.mainloop()
```
- Lance la boucle principale de l'interface graphique.
- Cette boucle attend les actions de l'utilisateur (clics, mouvements, saisies) et maintient la fenêtre ouverte tant que l'utilisateur n'a pas fermé l'application.

---

# Résumé général

| Étape | Description |
|:---|:---|
| Importation des modules | Chargement de `tkinter`, `ttk` et `Pillow` |
| Correction d'affichage Windows | Amélioration de la netteté sous Windows |
| Création de la fenêtre principale | Fenêtre de base de l'application |
| Affichage de texte fixe | Label simple avec texte |
| Affichage d'une image | Label affichant une image |
| Texte dynamique | Mise à jour automatique du texte avec `StringVar` |
| Combinaison texte + image | Label avec texte et image sur une même ligne |
| Boucle principale | Lancement et gestion de l'application graphique |

