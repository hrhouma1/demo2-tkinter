# Explication détaillée du script

---

## 1. Importation des modules

```python
import tkinter as tk
from tkinter import ttk
```
- `tkinter` : bibliothèque standard de Python pour construire des interfaces graphiques (GUI).
- `ttk` : module complémentaire proposant des widgets avec un style plus moderne.

---

## 2. Configuration spécifique pour Windows

```python
try:
    from ctypes import windll
    windll.shcore.SetProcessDpiAwareness(1)
except:
    pass
```
- Sous Windows, certains affichages tkinter peuvent être flous sur les écrans haute résolution.
- Cette section utilise la bibliothèque `ctypes` pour accéder à une fonction native (`SetProcessDpiAwareness`) qui améliore la gestion des pixels.
- Si cette fonction n'est pas disponible ou si une erreur survient, elle est ignorée silencieusement grâce à `try/except`.

---

## 3. Création de la fenêtre principale

```python
root = tk.Tk()
```
- Initialise la fenêtre principale de l'application.

```python
root.resizable(False, False)
```
- Désactive la possibilité de redimensionner la fenêtre.

```python
root.title("Widget Examples")
```
- Définit le titre affiché dans la barre de la fenêtre.

---

## 4. Création d'un widget `Text`

```python
text = tk.Text(root, height=8)
```
- Crée un widget `Text`, qui est une zone de saisie multiligne.
- Le paramètre `height=8` définit la hauteur du widget en nombre de lignes visibles.

```python
text.pack()
```
- Ajoute et affiche le widget `Text` dans la fenêtre.

---

## 5. Insertion de contenu initial dans la zone de texte

```python
text.insert("1.0", "Please enter a comment...")
```
- Insère le texte "Please enter a comment..." dans la zone de texte.
- `"1.0"` précise la position où insérer :
  - Le premier chiffre `1` représente la première ligne (numérotation commence à 1).
  - Le second chiffre `0` représente le premier caractère sur cette ligne (numérotation commence à 0).

---

## 6. Rappels sur la syntaxe des positions dans un widget `Text`

- Les positions sont données sous la forme `"ligne.caractère"`.
- Exemple : `"2.5"` correspond à la deuxième ligne, au sixième caractère.

---

## 7. Désactivation du widget `Text`

```python
text["state"] = "disabled"
```
- Modifie l'état du widget en "disabled", ce qui le rend non éditable par l'utilisateur.
- L'état par défaut est `"normal"`, permettant la modification.

---

## 8. Récupération du contenu de la zone de texte

```python
text_content = text.get("1.0", "end")
```
- Utilise la méthode `get()` pour récupérer le texte contenu dans la zone de texte.
- `"1.0"` est la position de départ (premier caractère de la première ligne).
- `"end"` signifie jusqu'à la fin du contenu.

```python
print(text_content)
```
- Affiche dans la console le contenu récupéré.

---

## 9. Lancement de la boucle principale

```python
root.mainloop()
```
- Démarre la boucle principale de l'application graphique.
- Cette boucle attend et traite les actions de l'utilisateur jusqu'à la fermeture de la fenêtre.

---

# Résumé général

| Étape | Description |
|:---|:---|
| Importation des modules | Chargement de `tkinter`, `ttk` et configuration Windows |
| Création de la fenêtre principale | Initialisation de la fenêtre et configuration du titre |
| Ajout d'un widget `Text` | Zone de texte multiligne pour la saisie de texte |
| Insertion de texte initial | Ajout d'un texte par défaut dans la zone |
| Désactivation du widget | Interdiction de modifier le contenu après insertion |
| Lecture du contenu | Récupération et affichage du texte saisi |
| Boucle principale | Maintien de l'interface graphique active |

