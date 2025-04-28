

# **TP 1 – Création d’une Interface de Lecture/Écriture CSV et JSON avec Tkinter**

---

# **Objectif général :**
Apprendre à construire une **interface graphique Tkinter** permettant de :
- Charger un fichier CSV ou JSON existant
- Afficher son contenu dans une zone de texte
- Modifier ce contenu
- Sauvegarder les modifications dans un nouveau fichier
- Utiliser des widgets de base (`Label`, `Button`, `Text`, `Combobox`, `Scrollbar`, etc.)

---

# **Durée :** 1 heure  
## **Livrable :**
- Un **rapport PDF ou Word** comprenant :
  - Les captures d’écran des étapes clés.
  - Le code source commenté.
  - Les réponses aux questions de réflexion.

- Le fichier Python `.py` complet de votre interface.

---

# **Contexte**
Vous travaillez pour une petite compagnie qui souhaite un outil simple pour :
- Lire rapidement des fichiers clients (CSV ou JSON)
- Faire quelques corrections rapides
- Sauvegarder les fichiers corrigés

Vous devez concevoir cet outil sous forme **d’une interface Tkinter**, facile à utiliser par des employés non informaticiens.

---

# **Étapes du TP**

---

<br/>

# **PARTIE 1 – Préparation de la fenêtre principale**

---

### **Tâche :**
- Créer une fenêtre Tkinter (`root`).
- Désactiver le redimensionnement (`resizable(False, False)`).
- Ajouter un titre ("Gestionnaire de Fichiers").

### **Commandes/code à compléter :**

```python
# 1.1 – Importer les modules nécessaires
___________________________________________

# 1.2 – Créer la fenêtre principale
___________________________________________

# 1.3 – Désactiver le redimensionnement
___________________________________________

# 1.4 – Définir un titre clair
___________________________________________
```

### **Résultat attendu :**
- Une fenêtre Tkinter de taille fixe avec le titre défini.

---

# **PARTIE 2 – Ajouter un Label et une Combobox pour choisir le type de fichier**

---

### **Tâche :**
- Ajouter un `Label` indiquant "Type de fichier".
- Ajouter une `Combobox` proposant les choix "CSV" et "JSON".

### **Commandes/code à compléter :**

```python
# 2.1 – Créer un label pour le type de fichier
___________________________________________

# 2.2 – Créer une combobox readonly avec "CSV" et "JSON"
___________________________________________

# 2.3 – Placer le label et la combobox dans la fenêtre
___________________________________________
```

### **Résultat attendu :**
- Un label et une liste déroulante permettant de choisir entre CSV et JSON.

---

# **PARTIE 3 – Ajouter la zone de texte et la barre de défilement**

---

### **Tâche :**
- Ajouter un `Text` pour afficher le contenu du fichier.
- Ajouter une `Scrollbar` verticale synchronisée avec le `Text`.

### **Commandes/code à compléter :**

```python
# 3.1 – Créer la zone de texte
___________________________________________

# 3.2 – Créer une barre de défilement verticale
___________________________________________

# 3.3 – Configurer la scrollbar pour contrôler le Text
___________________________________________

# 3.4 – Placer la Text et la Scrollbar dans la fenêtre
___________________________________________
```

### **Résultat attendu :**
- Une zone de texte avec une barre de défilement fonctionnelle.

---

# **PARTIE 4 – Ajouter les boutons de chargement et sauvegarde**

---

### **Tâche :**
- Ajouter deux boutons :
  - "Charger un fichier" → charge un CSV ou JSON.
  - "Sauvegarder sous" → enregistre les modifications.

### **Commandes/code à compléter :**

```python
# 4.1 – Créer un bouton "Charger un fichier"
___________________________________________

# 4.2 – Créer un bouton "Sauvegarder sous"
___________________________________________

# 4.3 – Définir les fonctions associées aux deux boutons
___________________________________________

# 4.4 – Placer les boutons dans la fenêtre
___________________________________________
```

---

# **PARTIE 5 – Lecture d’un fichier CSV ou JSON**

---

### **Tâche :**
- Lire le fichier sélectionné et afficher son contenu dans le `Text`.

### **Commandes/code à compléter :**

```python
# 5.1 – Utiliser filedialog pour choisir un fichier
___________________________________________

# 5.2 – Ouvrir et lire le fichier selon l’extension
___________________________________________

# 5.3 – Afficher le contenu formaté dans la zone de texte
___________________________________________
```

---

# **PARTIE 6 – Sauvegarde des modifications**

---

### **Tâche :**
- Permettre à l’utilisateur de sauvegarder son texte dans un nouveau fichier CSV ou JSON.

### **Commandes/code à compléter :**

```python
# 6.1 – Utiliser filedialog pour choisir l’emplacement du nouveau fichier
___________________________________________

# 6.2 – Enregistrer le contenu de la zone Text
___________________________________________
```

---

# **PARTIE 7 – Questions de réflexion**

---

## **Questions à répondre dans votre rapport :**

<br/>

**1. Quelle différence fondamentale existe-t-il entre un fichier CSV et un fichier JSON ?**  
Réponse :  
...............................................................................................................................

<br/>

**2. Pourquoi est-il important de vérifier l’extension du fichier avant de l’ouvrir ?**  
Réponse :  
...............................................................................................................................

<br/>

**3. Quelle méthode Tkinter est utilisée pour récupérer le contenu actuel d'un widget Text ?**  
Réponse :  
...............................................................................................................................

<br/>

**4. Expliquez pourquoi il est nécessaire de lier une `Scrollbar` à la `Text`. Que se passerait-il sinon ?**  
Réponse :  
...............................................................................................................................

<br/>

**5. Quelle différence constatez-vous entre `pack()`, `grid()` et `place()` pour positionner les widgets ?**  
Réponse :  
...............................................................................................................................

---

# **Captures d’écran exigées**

1. Fenêtre principale affichée correctement
2. Sélection d'un type de fichier
3. Contenu d'un fichier CSV chargé
4. Contenu d'un fichier JSON chargé
5. Zone de texte après modification
6. Dialogue de sauvegarde du nouveau fichier

---

# **Résumé**

| Étape                      | Objectif                          | Widget principal utilisé |
|:----------------------------|:----------------------------------|:-------------------------|
| Fenêtre principale          | Créer l’interface de base         | Tk()                     |
| Type de fichier             | Sélectionner CSV ou JSON          | Combobox                 |
| Zone de texte               | Afficher et éditer le contenu     | Text, Scrollbar          |
| Boutons actions             | Charger et Sauvegarder            | Button                   |
| Lecture de fichier          | Ouvrir un fichier CSV ou JSON     | open(), csv, json         |
| Sauvegarde de fichier       | Écrire le fichier                 | open(), write()          |

