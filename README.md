# Projet: Classification de paires de visages avec Random Forest

## 📋 Description du projet
Ce projet implémente un classifieur Random Forest pour déterminer si deux visages appartiennent à la même personne en utilisant le jeu de données **Labeled Faces in the Wild (LFW) pairs**. 

**Objectifs principaux:**
- Mettre en œuvre l'algorithme Random Forest
- Préparer et analyser les données LFW pairs
- Évaluer les performances avec des métriques pertinentes
- Comparer avec un modèle baseline simple
- Documenter les choix techniques et discuter des limites

## 🏗️ Structure du projet
random_forest_lfw_project/
│
├── random_forest_lfw.ipynb # Notebook principal avec l'implémentation complète
├── README.md # Ce fichier - Instructions d'exécution
├── requirements.txt # Dépendances Python
│
└── images/ # Figures générées automatiquement
├── lfw_examples.png # Exemples d'images du dataset
├── class_distribution.png # Distribution des classes
├── confusion_matrices.png # Matrices de confusion
├── roc_curve.png # Courbe ROC
├── feature_importance.png # Importance des features
└── misclassified_examples.png # Exemples d'erreurs


## 📊 Jeu de données utilisé

### Labeled Faces in the Wild (LFW) pairs
- **Source:** University of Massachusetts Amherst
- **Lien:** http://vis-www.cs.umass.edu/lfw/
- **Version utilisée:** LFW pairs avec resize=0.5
- **Taille:** ~2,200 paires de visages
- **Format:** Images en niveaux de gris 62x47 pixels
- **Classes:** 
  - 0: Personnes différentes (56% des échantillons)
  - 1: Même personne (44% des échantillons)

### Caractéristiques du dataset
- Chaque échantillon contient 2 images aplaties (2 × 62 × 47 = 5,828 features)
- Problème de classification binaire
- Dataset équilibré (légèrement déséquilibré en faveur de la classe 0)

## ⚙️ Prérequis techniques

### Configuration minimale requise
- **Python:** 3.8 ou version ultérieure
- **RAM:** 4 Go minimum (8 Go recommandé)
- **Espace disque:** 500 Mo libre
- **Système d'exploitation:** Windows, macOS ou Linux

### Dépendances Python
Les dépendances sont listées dans `requirements.txt`:
scikit-learn>=1.0.0
numpy>=1.20.0
pandas>=1.3.0
matplotlib>=3.5.0
seaborn>=0.11.0
jupyter>=1.0.0
notebook>=6.4.0

## 🚀 Installation et exécution

### Option 1: Exécution sur Google Colab (Recommandé)
1. **Télécharger** le fichier `random_forest_lfw.ipynb`
2. Se rendre sur [Google Colab](https://colab.research.google.com/)
3. Cliquer sur **"Upload"** et sélectionner le notebook
4. **Exécuter toutes les cellules** (Runtime → Run all)

**Avantages Colab:**
- Aucune installation nécessaire
- Accès gratuit à GPU/TPU
- Environnement préconfiguré
- Partage facile

### Option 2: Exécution locale avec Jupyter
```bash
# 1. Cloner le repository
git clone https://github.com/votre-username/random_forest_lfw.git
cd random_forest_lfw

# 2. Créer un environnement virtuel (recommandé)
python -m venv venv

# 3. Activer l'environnement
# Sur Windows:
venv\Scripts\activate
# Sur macOS/Linux:
source venv/bin/activate

# 4. Installer les dépendances
pip install -r requirements.txt

# 5. Lancer Jupyter Notebook
jupyter notebook

# 6. Ouvrir random_forest_lfw.ipynb et exécuter toutes les cellules
# Convertir le notebook en script Python
jupyter nbconvert --to python random_forest_lfw.ipynb

# Exécuter le script
python random_forest_lfw.py
