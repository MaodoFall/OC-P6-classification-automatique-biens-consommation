# 🧠 Classification automatique de produits pour Place de Marché

**Projet 6 – Mastère Spécialisé Data Science – OpenClassrooms**  
**Rôle : Data Scientist**  
**Client : Place de Marché (startup e-commerce)**

---

## 🎯 Objectif du projet

Place de Marché, une marketplace en lancement, souhaite **automatiser l’attribution des catégories produits** à partir de **descriptions textuelles** et d’**images**, aujourd’hui renseignées manuellement par les vendeurs.

Mon rôle est de **conduire une étude de faisabilité d’un moteur de classification** capable de regrouper automatiquement des articles similaires, puis de tester une **approche de classification supervisée** sur les images.

---

## 🗂️ Jeu de données

- 1 fichier `.csv` contenant **1050 produits** avec nom, description, catégorie, image, etc.
- 1 dossier contenant **1050 images**, une par produit

> Catégories équilibrées – bonne base pour classification.

---

## 🧪 Étapes de l’analyse

### 1. 🔍 Analyse exploratoire
- Inspection des textes et images
- Nettoyage des textes (stopwords, lemmatisation, ponctuation)
- Visualisation de quelques exemples d’images

---

### 2. 🧪 Étude de faisabilité d’un moteur de classification automatique

#### 📄 **Approches texte** (features non supervisées) :
- `CountVectorizer`
- `TF-IDF`
- `Word2Vec`
- `BERT`
- `USE` (Universal Sentence Encoder)

#### 🖼️ **Approches image** :
- Extraction de features via :
  - `SIFT` (classique)
  - `CNN` via VGG16 (Transfer Learning)

#### 📊 Réduction de dimension + Visualisation
- Reduction de la dimension des embeddings (texte/image) via **t-SNE** et visualisation en 2D
  - Fonction personnalisée `Tsne_2D(X, y_true, clusters)` :
    - Compare les **catégories réelles** et les **clusters prédits**
    - Affiche deux graphes côte à côte
    - Calcule et affiche le **score ARI** (Adjusted Rand Index)

#### 📈 Évaluation de faisabilité :
- Score de similarité (ARI) entre clusters trouvés et catégories réelles
- Résultat : **CNN VGG16 + t-SNE = meilleure performance et visualisation**

---

### 3. ✅ Classification supervisée d’images

- Prétraitement des images (resize, rescale)
- Modèle basé sur **VGG16 (Transfer Learning)**
- Test avec et sans **data augmentation**
- Résultat : **le modèle sans augmentation est plus stable**

---

### 4. 🌐 Collecte via API – Edamam

- Utilisation de **Food Database API (Edamam)**
- Requête sur le mot-clé `"champagne"`
- Sauvegarde des **10 premiers produits** (utilisables comme données de test)

---

## 🛠️ Compétences mobilisées

- Traitement du langage naturel (NLP)
- Traitement d’images (SIFT, CNN, VGG16)
- Extraction de features et réduction de dimension (t-SNE)
- Clustering non supervisé (KMeans, DBSCAN)
- Classification supervisée (TensorFlow / Keras)
- Appels API & collecte de données

---

## 📁 Livrables

- 📓 Prétraitements, extraction des features et étude de faisabilité
- 📓 Classification supervisée avec et sans augmentation
- 📜 Script de collecte via Edamam API
- 🖥️ Support de présentation

---

## ✅ Conclusion

- **Faisabilité démontrée** : la catégorisation automatique est pertinente via VGG16 + t-SNE
- La classification supervisée peut servir de moteur initial pour le système
- Les nouvelles données collectées via API serviront à **tester la robustesse du modèle en production**

---

## 🙋‍♂️ Réalisé par

**Maodo FALL**  
*Data Scientist*

---
