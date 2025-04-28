

# **TP Final – Création d’une Interface Professionnelle de Gestion de Fichiers CSV/JSON avec Tkinter**

---

# **Objectif général :**
Construire une **interface graphique professionnelle et interactive** permettant de :
- Charger un fichier CSV ou JSON
- Afficher son contenu de façon élégante
- Modifier son contenu
- Sauvegarder les modifications
- Utiliser des widgets modernes et organisés
- Créer une expérience utilisateur agréable (**"Wow"**)

---

# **Durée :** 2 semaines  
## **Livrable :**
- Le **fichier Python** final
- Le **rapport PDF/Word** avec captures d’écran
- Les réponses aux questions de réflexion

---

# **Contexte**
Vous êtes engagé par une startup technologique qui souhaite impressionner ses investisseurs.  
On vous demande de réaliser une **interface graphique simple mais professionnelle**, pour manipuler des fichiers clients.

---

# **Présentation du Projet Final**

---

- Une **fenêtre moderne**, bien dimensionnée
- Un **logo** affiché au démarrage
- Un **effet d'animation** sur l'affichage
- Une **combobox** pour choisir CSV/JSON
- Une **zone de texte stylée** avec **scrollbar intégrée**
- **Boutons alignés** et **icônes** sur les boutons
- **Gestion dynamique** de l'affichage et sauvegarde
- **Affichage structuré** des données (pas brut, organisé)

---

# **ÉTAPES DÉTAILLÉES**

---

<br/>

# **PARTIE 1 – Construction de la Fenêtre Principale**

---

### **Tâches :**
- Créer la fenêtre principale
- Désactiver le redimensionnement
- Définir un titre
- Définir une taille fixe (800x600)
- Changer la couleur de fond (ex : `#f0f2f5`)

### **Code à compléter :**

```python
# 1.1 – Importer tkinter, ttk et PIL
_____________________________________________

# 1.2 – Créer la fenêtre principale
_____________________________________________

# 1.3 – Fixer la taille (800x600) et la couleur de fond
_____________________________________________

# 1.4 – Désactiver le redimensionnement
_____________________________________________

# 1.5 – Définir le titre ("Gestionnaire de Fichiers Pro")
_____________________________________________
```

---

# **PARTIE 2 – Affichage du logo avec animation**

---

### **Tâches :**
- Ajouter un logo/image au haut de l'interface
- Appliquer une animation simple : légère apparition retardée

### **Code à compléter :**

```python
# 2.1 – Charger une image avec PIL.Image et ImageTk
_____________________________________________

# 2.2 – Afficher l’image dans un Label
_____________________________________________

# 2.3 – Pack ou Grid avec option "pady" pour espacer
_____________________________________________
```

---

# **PARTIE 3 – Sélection du type de fichier**

---

### **Tâches :**
- Ajouter un `Label` "Type de fichier"
- Ajouter une `Combobox` (`state="readonly"`) avec "CSV" et "JSON"

### **Code à compléter :**

```python
# 3.1 – Créer un label "Type de fichier"
_____________________________________________

# 3.2 – Créer une combobox CSV/JSON
_____________________________________________

# 3.3 – Lier la sélection à une variable
_____________________________________________

# 3.4 – Placer proprement (pack avec padx/pady)
_____________________________________________
```

---

# **PARTIE 4 – Zone de Texte + Scrollbar stylée**

---

### **Tâches :**
- Ajouter une `Text` pour afficher le contenu
- Ajouter une `Scrollbar` verticale synchronisée
- Définir une taille et une police moderne (ex : "Segoe UI", 12)

### **Code à compléter :**

```python
# 4.1 – Créer une Text multiligne
_____________________________________________

# 4.2 – Créer une Scrollbar verticale
_____________________________________________

# 4.3 – Lier la Scrollbar à la Text
_____________________________________________

# 4.4 – Pack ou Grid avec "sticky" pour étirer correctement
_____________________________________________
```

---

# **PARTIE 5 – Boutons élégants avec icônes**

---

### **Tâches :**
- Ajouter deux boutons :
  - **Charger** (icône dossier ouvert)
  - **Sauvegarder sous** (icône disquette)
- Utiliser `PhotoImage` pour les icônes.

### **Code à compléter :**

```python
# 5.1 – Charger les images pour les boutons
_____________________________________________

# 5.2 – Créer le bouton Charger avec image
_____________________________________________

# 5.3 – Créer le bouton Sauvegarder avec image
_____________________________________________

# 5.4 – Pack les deux boutons côte à côte
_____________________________________________
```

---

# **PARTIE 6 – Fonctionnalités : Ouvrir / Afficher / Sauvegarder**

---

### **Tâches :**
- Ouvrir un fichier sélectionné
- Afficher le contenu formaté dans la `Text`
- Sauvegarder le contenu dans un nouveau fichier

### **Code à compléter :**

```python
# 6.1 – Utiliser filedialog.askopenfilename()
_____________________________________________

# 6.2 – Lire CSV avec csv.reader ou JSON avec json.load
_____________________________________________

# 6.3 – Afficher proprement dans la zone Text
_____________________________________________

# 6.4 – Utiliser filedialog.asksaveasfilename() pour sauvegarder
_____________________________________________

# 6.5 – Sauvegarder le contenu sous CSV ou JSON correctement
_____________________________________________
```

---

# **PARTIE 7 – Slider de zoom pour le texte**

---

### **Tâches :**
- Ajouter un `Scale` horizontal pour modifier la taille du texte
- Ajuster dynamiquement la police selon la valeur du `Scale`

### **Code à compléter :**

```python
# 7.1 – Créer un Scale de 8 à 24
_____________________________________________

# 7.2 – Modifier la taille du texte dans le Text quand le Scale bouge
_____________________________________________
```

---

# **PARTIE 8 – Questions de réflexion dans le rapport**

---

**1. Quelle différence existe entre un fichier CSV et JSON au niveau structure ?**  
...............................................................................................................................

**2. Pourquoi utiliser `Scrollbar` et `Text` ensemble dans une interface lisible ?**  
...............................................................................................................................

**3. Quelles sont les différences entre `pack()`, `grid()`, et `place()` dans Tkinter ?**  
...............................................................................................................................

**4. Pourquoi fixer une taille de fenêtre et empêcher le redimensionnement dans une application professionnelle ?**  
...............................................................................................................................

**5. Quelle différence entre `json.load()` et `json.dump()` en Python ?**  
...............................................................................................................................

---

# **CAPTURES D'ÉCRAN EXIGÉES**

1. Fenêtre ouverte avec logo visible
2. Sélection du type de fichier
3. Chargement d'un fichier CSV
4. Chargement d'un fichier JSON
5. Modification de texte
6. Utilisation du Scale pour agrandir/rétrécir le texte
7. Sauvegarde du fichier
8. Rapport final contenant toutes les étapes

---

# **Résumé Visuel attendu**

- Interface **professionnelle, claire et fonctionnelle**
- Tous les widgets correctement alignés
- Navigation fluide (Scrollbar + Zoom)
- Chargement de fichiers sans erreur
- Sauvegarde fonctionnelle

