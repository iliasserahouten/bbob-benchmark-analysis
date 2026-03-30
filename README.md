# Analyse Comparative d'Algorithmes d'Optimisation Boîte Noire sur le Benchmark BBOB

[![DOI]([https://zenodo.org/badge/19339648.svg](https://zenodo.org/badge/doi/10.5281/zenodo.8475.svg))](https://doi.org/10.5281/zenodo.19339648)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)

## Description

Ce dépôt contient le code source, les données et l'article associés à :

> **Analyse Comparative d'Algorithmes d'Optimisation Boîte Noire sur le Benchmark BBOB**  
> Iliass Erahouten et Aya Eddib  
> École d'Ingénieurs du Littoral Côte d'Opale (EILCO)

Nous comparons trois algorithmes d'optimisation boîte noire sur la suite BBOB en dimension 10 :

| Algorithme | Type | Référence |
|-----------|------|-----------|
| **BIPOP-CMA-ES** | Évolutionnaire à redémarrage adaptatif | Hansen, 2009 |
| **PSO-BFGS** | Hybride essaim particulaire + quasi-Newton | Voglis et al., 2012 |
| **RANDOMSEARCH-5** | Recherche aléatoire (ligne de base) | Auger & Ros, 2009 |

## Fonctions BBOB étudiées

| Fonction | Nom | Type |
|----------|-----|------|
| f1 | Sphere | Unimodale, séparable, convexe |
| f8 | Rosenbrock | Unimodale, non séparable, vallée étroite |
| f15 | Rastrigin | Multimodale structurée |
| f20 | Schwefel | Multimodale, structure inadéquate |
| f24 | Lunacek bi-Rastrigin | Multimodale complexe, deux bassins |

## Structure du dépôt

```
.
├── README.md                  # Ce fichier
├── LICENSE                    # Licence MIT
├── requirements.txt           # Dépendances Python
├── .gitignore                 # Fichiers à ignorer
├── notebook/
│   └── analysis.ipynb         # Notebook Jupyter (analyse complète)
└── paper/
    └── paper.tex              # Source LaTeX de l'article
```

## Installation et exécution

### Prérequis

- Python 3.8+
- Jupyter Notebook ou JupyterLab

### Installation

```bash
git clone https://github.com/iliasserahouten/bbob-benchmark-analysis.git
cd bbob-benchmark-analysis
pip install -r requirements.txt
```

### Exécution du notebook

```bash
jupyter notebook notebook/analysis.ipynb
```

> **Note :** Le notebook télécharge automatiquement les données BBOB depuis l'[archive officielle](https://numbbo.github.io/data-archive/) lors de la première exécution.

## Résultats principaux

- **PSO-BFGS** est jusqu'à **15× plus rapide** sur les fonctions unimodales (f1, f8)
- **BIPOP-CMA-ES** est le **seul algorithme fiable** sur les fonctions multimodales (f15, f20, f24)
- **Aucun algorithme ne domine uniformément** : le choix dépend du paysage et du budget
- Toutes les différences sont **statistiquement significatives** (tests de Wilcoxon, p < 0.05)

## Outils d'analyse utilisés

Le notebook implémente six types d'analyses :
1. Courbes de convergence (médiane, échelle log-log)
2. Boxplots des Δf finaux
3. ECDF (Empirical Cumulative Distribution Functions)
4. ERT (Expected Running Time)
5. Heatmap des performances relatives
6. Tests statistiques de Wilcoxon

## Données

Les données proviennent de l'[archive officielle BBOB (numbbo)](https://numbbo.github.io/data-archive/) et sont téléchargées automatiquement par le notebook.

## Citation

Si vous utilisez ce travail, merci de citer :

```bibtex
@misc{erahouten2025bbob,
  author       = {Erahouten, Iliass and Eddib, Aya},
  title        = {Analyse Comparative d'Algorithmes d'Optimisation Boîte Noire sur le Benchmark BBOB},
  year         = {2026},
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.19339648},
  url          = {https://doi.org/10.5281/zenodo.19339648}
}
```

## Licence

Ce projet est distribué sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.

## Auteurs

- **Iliass Erahouten** — [Iliass.Erahoutenb@etu.eilco.univ-littoral.fr](mailto:Iliass.Erahoutenb@etu.eilco.univ-littoral.fr)
- **Aya Eddib** — [Aya.Eddib@etu.eilco.univ-littoral.fr](mailto:Aya.Eddib@etu.eilco.univ-littoral.fr)

Département d'Informatique, École d'Ingénieurs du Littoral Côte d'Opale (EILCO)
