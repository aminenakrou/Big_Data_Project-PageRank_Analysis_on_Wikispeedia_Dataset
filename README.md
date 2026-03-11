<div align="center">

# 📊 PageRank Analysis on Wikispeedia Dataset

**Implémentation et analyse comparative de l'algorithme PageRank (standard & personnalisé) sur le graphe de navigation Wikispeedia de Stanford.**

[![GitHub Pages](https://img.shields.io/badge/🌐_Live_Demo-GitHub_Pages-6366f1?style=for-the-badge)](https://aminenakrou.github.io/Big_Data_Project-PageRank_Analysis_on_Wikispeedia_Dataset/)
[![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

<br>

[🌐 **Voir le site du projet**](https://aminenakrou.github.io/Big_Data_Project-PageRank_Analysis_on_Wikispeedia_Dataset/) · [📄 **Lire le rapport**](rapport/NAKROU_YAHI__RAPPORT_BIGDATA.pdf) · [🐛 **Signaler un bug**](https://github.com/AmiNeNakrou/Big_Data_Project-PageRank_Analysis_on_Wikispeedia_Dataset/issues)

</div>

---

## 📋 Table des matières

- [Aperçu](#-aperçu)
- [Résultats clés](#-résultats-clés)
- [Dataset](#-dataset)
- [Méthodologie](#-méthodologie)
- [Installation & Exécution](#-installation--exécution)
- [Structure du projet](#-structure-du-projet)
- [Technologies](#-technologies)
- [Auteurs](#-auteurs)

---

## ✨ Aperçu

Ce projet de **Big Data** (IS4) implémente et analyse l'algorithme **PageRank** — dans sa version standard et sa version personnalisée — sur le jeu de données **Wikispeedia** de l'Université de Stanford. L'objectif est d'étudier le comportement de cet algorithme sur un graphe réel de navigation construit à partir des parcours de joueurs sur une version condensée de Wikipédia.

L'approche combine :

- Construction d'une **matrice de transition** à partir des chemins de navigation
- Calcul du PageRank via la **méthode de la puissance itérée**
- Analyse de l'impact du **facteur d'amortissement β**
- **Personnalisation** du vecteur de téléportation pour orienter les résultats

> 🌐 **Le site interactif du projet est disponible ici :**
> **[aminenakrou.github.io/Big_Data_Project-PageRank_Analysis_on_Wikispeedia_Dataset](https://aminenakrou.github.io/Big_Data_Project-PageRank_Analysis_on_Wikispeedia_Dataset/)**

---

## 🏆 Résultats clés

| Métrique | Valeur |
|:---|:---|
| Pages analysées | **4 169** |
| Chemins de navigation | **51 318** |
| Itérations (β = 0.85) | **26** |
| Temps d'exécution | **2.55 s** |
| Page la mieux classée | **United_States** (score : 0.0305) |

### Top 5 — PageRank Standard (β = 0.85)

| Rang | Page | Score |
|:---:|:---|:---:|
| 🥇 | United_States | 0.030514 |
| 🥈 | Europe | 0.014162 |
| 🥉 | United_Kingdom | 0.013187 |
| 4 | England | 0.011728 |
| 5 | Africa | 0.009416 |

> 💡 **United_States** obtient un score plus de **2× supérieur** à celui de la 2ᵉ page, révélant un rôle de « super-hub » dans le réseau de navigation Wikispeedia.

### PageRank Personnalisé

| Scénario | Itérations | Temps (s) | Top 1 |
|:---|:---:|:---:|:---|
| Standard (β = 0.85) | 26 | 2.55 | United_States |
| Personnalisé « Computer » | 36 | 3.17 | Computer |
| Personnalisé « Savane » | 38 | 3.37 | Lion |

---

## 📚 Dataset

Le projet utilise le dataset [**Wikispeedia**](https://snap.stanford.edu/data/wikispeedia.html) de l'Université de Stanford.

- **4 604 articles** Wikipédia (version condensée)
- **51 318 chemins** de navigation terminés avec succès
- Fichier principal : `paths_finished.tsv` (colonne 4 = séquence de pages visitées)
- Gestion des **retours arrière** via le symbole `<`

---

## 🧠 Méthodologie

```
📥 Chargement TSV  →  🏷️ Indexation (4169 nœuds)  →  📐 Matrice d'adjacence (n×n)
        →  🔄 Normalisation (matrice de transition)  →  ⚡ PageRank (puissance itérée)
```

### Formules

**PageRank Standard :**

```
PR = (1 − β) / n  +  β × M × PR
```

**PageRank Personnalisé :**

```
PR = (1 − β) × V  +  β × M × PR
```

Où `V` est le vecteur de personnalisation favorisant un sous-ensemble de pages, et `M` la matrice de transition normalisée.

### Concepts mis en œuvre

`PageRank standard` · `PageRank personnalisé` · `Matrice d'adjacence` · `Matrice de transition` · `Puissance itérée` · `Convergence numérique` · `Téléportation` · `Dangling nodes` · `Norme L1`

---

## 🚀 Installation & Exécution

### Prérequis

- Python 3.x
- NumPy
- Matplotlib

### Installation

```bash
# Cloner le dépôt
git clone https://github.com/AmiNeNakrou/Big_Data_Project-PageRank_Analysis_on_Wikispeedia_Dataset.git
cd Big_Data_Project-PageRank_Analysis_on_Wikispeedia_Dataset

# Installer les dépendances
pip install numpy matplotlib
```

### Exécution

```bash
# PageRank Standard
python pagerank_standard.py

# PageRank Personnalisé
python pagerank_personnalise.py
```

> ⚠️ **Note :** Assurez-vous que le fichier `paths_finished.tsv` se trouve dans le même répertoire que les scripts, ou modifiez la variable `file_path` dans chaque fichier.

---

## 📂 Structure du projet

```
.
├── index.html                              # Site web du projet (GitHub Pages)
├── pagerank_standard.py                    # Implémentation du PageRank standard
├── pagerank_personnalise.py                # Implémentation du PageRank personnalisé
├── paths_finished.tsv                      # Dataset Wikispeedia (chemins)
├── figures/
│   ├── top20_beta_085.png                  # Top 20 des pages (β = 0.85)
│   ├── impact_beta.png                     # Évolution du Top 5 selon β
│   ├── performance_iterations.png          # Itérations en fonction de β
│   └── performance_temps.png               # Temps d'exécution en fonction de β
├── rapport/
│   └── NAKROU_YAHI__RAPPORT_BIGDATA.pdf    # Rapport complet du projet
└── README.md
```

---

## 🛠️ Technologies

| Outil | Usage |
|:---|:---|
| **Python 3** | Langage principal |
| **NumPy** | Calcul matriciel et algèbre linéaire |
| **Matplotlib** | Visualisation des résultats |
| **urllib.parse** | Nettoyage des noms de pages (URL decoding) |
| **GitHub Pages** | Hébergement du site web interactif |

---

## 👥 Auteurs

| | Nom | Rôle |
|:---:|:---|:---|
| 🟣 | **Amine Nakrou** | Développeur — IS4 Big Data |
| 🟢 | **Réda Yahi** | Développeur — IS4 Big Data |

**Encadrant :** Serge Petiton — Année universitaire 2025–2026

---

<div align="center">

**[🌐 Voir le site interactif](https://aminenakrou.github.io/Big_Data_Project-PageRank_Analysis_on_Wikispeedia_Dataset/)** · **[📄 Lire le rapport](rapport/NAKROU_YAHI__RAPPORT_BIGDATA.pdf)**

<sub>Projet Big Data — IS4 · Université de Lille</sub>

</div>
