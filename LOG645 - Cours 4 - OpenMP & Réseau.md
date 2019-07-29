---
title: LOG645 - Cours 4 - OpenMP & Réseau
created: '2019-06-08T18:37:49.961Z'
modified: '2019-06-13T02:23:35.232Z'
tags: [LOG645, LOG645-1]
---

# LOG645 - Cours 4 - OpenMP & Réseau

## OpenMP
Quand même beaucoup à apprendre, vraie différence c'est que c'est à mémoire partagée.

## Réseau
Il existe deux types d'ordinateurs pour les besoins actuels
1. Multiprocesseurs
  1. mémoire partagées UMA
  1. Mutex et sémaphores principalement
1. multi-ordinateurs
  1. Fonctionne avec mémoires en réseau (NUMA)
  1. C'est là où on commence à mettre de la cache en mémoire et que l'inconhérence prend forme.
  1. Fonctionne beaucoup avec des passages de messages (par exemple OpenMPI)

Il existe deux types de parc informatique
1. Symmétrique
  1. Tous les ordinateurs sont le plus homogène possible.
1. Asymmétrique
  1. Pas besoin d'homogénéité

## Définitions
### CPU Scavenging
Permet d'utiliser à fond les CPU non utilisés.

Par exemple : incredibuild.

### Déterminisme
Pour le même input, le output devrait toujours être le même.

<span style="color:red">**À revoir!**</span>
