---
title: LOG645 - Cours 1 - Introduction
created: '2019-06-08T18:34:47.317Z'
modified: '2019-06-13T19:44:45.744Z'
tags: [LOG645, LOG645-1]
---

 # LOG645 - Cours 1 - Introduction

## Différents types de parallélisme
1. De données
  * Présent lorsque des tâches indépendantes appliquent la même opération sur différent éléments d'un ensemble de données
1. De tâches (fonctions)
  * Présent lorsque des tâches indépendantes appliquent des opérations différentes sur des données différentes
1. En pipeline
  * Divier un algorithme séquentiel en phase
  * Chaque phase peut être parallélisée
  * L'output d'une phase représente l'inpus de la prochaine phase

## Taxonomie de Flynn
* Flux de données
* Flux d'instructions

## Variation de la taxonomie de Flynn
* SISD
  * Supporte le parallélisme apparent
  * Qui n'ont pas de dépendance de data
* SIMD
  * Adapté aux problèmes à forte régularité
  * CUDA
  * OpenCL
* MISD (existe pas)
* MIMD 
  * La plus utilisée
  * chaque processeur indépendants
  * 2 variantes
    - Mémoire partagé (UMA)
    - Mémoire distribuée (NUMA)

## Concourence
La concourance est la "possiblité" d'être parallèle. Cela veut dire qu'on peut avoir un code qui est possiblement parallèle sans l'être par exemple sur un ordinateur single thread.

## Parallélisme
Le parallélisme c'est vraiment exécuter deux ou plus de tâches en même temps dans un processus.

## Deux types de métrique
Débit et Latence
