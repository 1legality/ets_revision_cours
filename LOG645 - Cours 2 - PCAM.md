---
title: LOG645 - Cours 2 - PCAM
created: '2019-06-08T18:35:26.923Z'
modified: '2019-06-13T19:24:25.677Z'
tags: [LOG645, LOG645-1]
---

# LOG645 - Cours 2 - PCAM

## Méthodologie de conception
PCAM

* Partitionnement
  * Définition des tâches
  * Faire la granularité des tâches
  * Exemple : $\overbrace{1000}^{x} * \overbrace{1000}^{y} * \overbrace{100}^{z} * \overbrace{1000}^{T}$
* Communication
  * Identifier les exigences
  * Mettre le travail sous forme de vecteur selon le nombre de dépendances 
  * $\begin{bmatrix}-1 & 0 & 0 & -1\end{bmatrix}$
  * $\begin{bmatrix}0 & -1 & 0 & -1\end{bmatrix}$
  * etc
* Agglomération
  * Regroupement des tâches
  * Mettre le travail selon le nombre de cores
  * $\overbrace{\frac{1000}{64}}^{x} * \overbrace{1000}^{y} * \overbrace{100}^{z} * \overbrace{1000}^{T}$
  * 64 cores dans l'exemple ci-dessus
* Mapping (divisioin des tâches)
  * On a accès à combien de machines?
  * $\overbrace{\frac{1000}{8}}^{x} * \overbrace{1000}^{y} * \overbrace{100}^{z} * \overbrace{1000}^{T}$
  * 8 machines dans l'exemple ci-dessus.

## OpenMPI
Quand même beaucoup à apprendre sur OpenMPI, en gros permet d'avoir un réseau d'ordinateurs liés ensemble.
