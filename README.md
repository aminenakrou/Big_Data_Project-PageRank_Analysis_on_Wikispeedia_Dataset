# 📊 Analyse du PageRank sur Wikispeedia

> Projet Big Data consacré à l’implémentation et à l’analyse de l’algorithme **PageRank** sur le dataset **Wikispeedia**, avec comparaison entre une version **standard** et une version **personnalisée**.

## ✨ Aperçu

Ce projet a pour objectif d’étudier le comportement de l’algorithme **PageRank** sur un graphe réel construit à partir des parcours de navigation du jeu **Wikispeedia**.

L’approche combine :

- modélisation des transitions entre pages ;
- implémentation Python du PageRank ;
- analyse de convergence ;
- personnalisation du vecteur de téléportation ;
- interprétation des résultats obtenus.

## 🎯 Objectifs

Le projet vise à :

- implémenter le **PageRank standard** ;
- implémenter un **PageRank personnalisé** ;
- construire une matrice de transition à partir du dataset ;
- analyser l’influence du facteur d’amortissement `beta` ;
- comparer le nombre d’itérations et le temps d’exécution ;
- étudier des scénarios de personnalisation thématique.

## 📚 Dataset utilisé

Le projet s’appuie sur le dataset **Wikispeedia** de l’université de Stanford.  
Ce jeu de données contient des parcours de navigation réalisés par des utilisateurs sur une version simplifiée de Wikipédia. [file:134]

Les données exploitées proviennent principalement du fichier `paths_finished.tsv`, en particulier la colonne contenant les chemins empruntés entre les pages. [file:134]

## 🧠 Concepts abordés

- **PageRank standard**
- **PageRank personnalisé**
- **Matrice d’adjacence**
- **Matrice de transition**
- **Méthode de la puissance itérée**
- **Convergence numérique**
- **Téléportation**
- **Dangling nodes**
- **Analyse de performance**

## 🛠️ Technologies utilisées

- **Python**
- **NumPy**
- **Matplotlib**
- **time**
- **os**
- **urllib.parse**

## 📂 Structure du projet

```bash
.
├── pagerank_standard.py
├── pagerank_personnalise.py
├── paths_finished.tsv
├── figures/
│   ├── top20_beta_085.png
│   ├── impact_beta.png
│   ├── performance_iterations.png
│   └── performance_temps.png
├── rapport/
│   └── NAKROU_YAHI__RAPPORT_BIGDATA.pdf
└── README.md
