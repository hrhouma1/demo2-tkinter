# **Correction détaillée du Quiz**

---

# Partie 1 – QCM

---

## **Question 1**

**Quel module est utilisé pour créer des widgets modernes avec un style système natif ?**

→ **Réponse correcte : b) ttk**

**Explication :**  
- `ttk` est une extension moderne de `tkinter` qui permet de créer des widgets (boutons, labels, etc.) qui ressemblent davantage aux éléments graphiques de Windows, MacOS, Linux.
- `tk` (réponse a) est le module de base, mais sans styles modernes.
- `ctypes` (réponse c) est un module pour manipuler des fonctions système, pas pour créer des widgets.
- `PIL` (réponse d) est utilisé pour les images, pas pour des boutons ou labels.

**Pourquoi b) est la bonne réponse ?**  
Parce que `ttk` apporte des widgets améliorés visuellement, contrairement à `tk` seul.

**Par élimination :**
- a) `tk` : crée des widgets classiques, pas modernes.
- c) `ctypes` : sert à appeler des fonctions du système Windows, pas pour faire des interfaces.
- d) `PIL` : travaille avec des images, rien à voir avec des boutons ou labels.

---

## **Question 2**

**Quelle est la fonction de `windll.shcore.SetProcessDpiAwareness(1)` ?**

→ **Réponse correcte : c) Améliorer la netteté sous Windows haute résolution**

**Explication :**
- Quand on utilise Tkinter sous Windows sur un écran haute densité (comme 4K), les fenêtres et textes peuvent apparaître flous.
- `SetProcessDpiAwareness(1)` demande à Windows de corriger cela automatiquement.

**Par élimination :**
- a) Créer une nouvelle fenêtre : non, la création de fenêtre est faite avec `tk.Tk()`.
- b) Gérer les événements clavier : non, ce n'est pas lié au clavier.
- d) Modifier la taille du texte : non, cela améliore l'affichage général, pas uniquement le texte.

---

## **Question 3**

**Quelle commande interdit à l'utilisateur de redimensionner la fenêtre ?**

→ **Réponse correcte : c) root.resizable(False, False)**

**Explication :**
- `root.resizable(False, False)` interdit l'agrandissement de la fenêtre, aussi bien horizontalement qu'en hauteur.
- Le premier `False` est pour la largeur, le second pour la hauteur.

**Par élimination :**
- a) `root.resize(False, False)` : cette méthode n'existe pas en Tkinter.
- b) `root.block(False, False)` : `block()` n'existe pas non plus.
- d) `root.locksize(False, False)` : il n'y a pas de `locksize()` en Tkinter.

---

## **Question 4**

**Pour afficher une image dans un `Label`, laquelle des bibliothèques est utilisée ?**

→ **Réponse correcte : b) Pillow**

**Explication :**
- Tkinter tout seul ne sait pas lire les formats modernes d'images (ex: PNG, JPEG).  
- La bibliothèque `Pillow` est donc utilisée pour charger et afficher des images dans un widget Tkinter.

**Par élimination :**
- a) OpenCV : sert au traitement d'image avancé, pas à l'affichage simple dans Tkinter.
- c) Matplotlib : sert pour tracer des graphiques, pas pour afficher des images directement.
- d) NumPy : sert aux calculs numériques sur des matrices, pas aux images.

---

## **Question 5**

**Quel paramètre permet d'afficher du texte et une image dans un même `Label` ?**

→ **Réponse correcte : c) compound**

**Explication :**
- `compound` permet de positionner l'image par rapport au texte dans un même widget Label (ex: image à droite, texte à gauche).

**Par élimination :**
- a) align : n'existe pas dans Tkinter pour ce contexte.
- b) side : existe dans `pack()`, mais pas pour Label.
- d) attach : n'existe pas dans Tkinter.

---

# Partie 2 – Vrai/Faux

---

## **Question 6**

**Le script utilise `try/except` pour empêcher une erreur sur des systèmes non-Windows.**

→ **Réponse : Vrai**

**Explication :**  
Le bloc `try/except` sert à éviter que l'application plante si la fonction Windows (`SetProcessDpiAwareness`) n'existe pas sur d'autres systèmes comme Linux ou Mac.

---

## **Question 7**

**`StringVar()` est utilisée pour modifier dynamiquement le style graphique d'un label.**

→ **Réponse : Faux**

**Explication :**
- `StringVar` permet de changer le **contenu** (texte) d'un label, pas son style (ex: couleur, taille).
- Le style se modifie autrement (`font`, `foreground`, etc.), pas avec `StringVar`.

---

## **Question 8**

**Sans `root.mainloop()`, la fenêtre se fermerait immédiatement après sa création.**

→ **Réponse : Vrai**

**Explication :**
- `mainloop()` est une boucle infinie qui garde la fenêtre ouverte et attend les événements de l'utilisateur.
- Sans elle, le programme finirait immédiatement après avoir créé la fenêtre.

---

# Partie 3 – Réponses Courtes

---

## **Question 9**

**Expliquez l'objectif de `label.pack()`.**

→ **Réponse :**
- `label.pack()` place le `Label` dans la fenêtre principale et demande à Tkinter de l'afficher.
- Sans `pack()`, le label serait créé en mémoire mais ne serait jamais visible dans l'interface graphique.

---

## **Question 10**

**Quelle est la différence entre `text="Hello"` et `textvariable=greeting` dans un Label ?**

→ **Réponse :**
- `text="Hello"` : fixe le texte au moment de la création. Il est **statique** (ne change pas automatiquement).
- `textvariable=greeting` : lie dynamiquement le texte du label à une variable `StringVar`.  
  Quand la valeur de la variable change, le texte affiché dans le label change aussi **automatiquement** sans devoir refaire `config()`.

---

# Partie 4 – Réflexion

---

## **Question 11**

**Que se passe-t-il si l'image `"test_image.png"` n'existe pas ? Que proposeriez-vous ?**

→ **Réponse :**
- Si l'image n'existe pas, Python lèverait une erreur **FileNotFoundError**.
- Cela ferait planter le programme si on ne gère pas l'erreur.
- **Solution** :  
  Ajouter un `try/except` autour du `Image.open()` pour attraper cette erreur, et :
  - Soit afficher un message d'erreur dans la console,
  - Soit afficher une image par défaut ("image introuvable"),
  - Soit continuer sans ajouter d'image.

**Exemple de correction simple :**
```python
try:
    image = Image.open("test_image.png")
except FileNotFoundError:
    print("Erreur : L'image 'test_image.png' est introuvable.")
    image = Image.new("RGB", (100, 100), color="gray")  # Image vide de secours
```

---

# Résumé

| Partie | Détail |
|:---|:---|
| Partie 1 – QCM | Explication précise + élimination pédagogique |
| Partie 2 – Vrai/Faux | Justifications complètes |
| Partie 3 – Réponses courtes | Réponses claires, adaptées aux débutants |
| Partie 4 – Réflexion | Propositions concrètes, réalistes |
