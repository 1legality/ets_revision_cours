---
title: LOG645 - Cours 6 - Ordonanceurs
created: '2019-06-08T02:42:52.125Z'
modified: '2019-06-11T16:58:08.207Z'
tags: [LOG645, LOG645-1]
---

# LOG645 - Cours 6 - Ordonanceurs

## Traitement
* Concourant
* Parallèle
* Par lot
  * Un utilisateur donne plusieurs commandes dans une queue d'exécution... Toutes les commandes sont séquentielles

## Composition d'un noyau
- Un noyau monolitique c'est ce qu'on a dans nos ordinateurs présentement
  - Ils ont une protections mémoires
  - Peuvent planter si un pilote plante
- Les micro-noyau vont peut-être être le futur
  - Ils ont une protection mémoire
  - Beaucoup plus petit, moins bloated
  - Si un driver plante, le système ne devrait pas planter au complet

## Ordonanceur
- Ne garanti pas l'ordre sauf si demandé spécifiquement
- Dépend du OS

### Responsabilité
* Équité : l'ordonnaceur doit attrivuer à chaque processus un temps de CPU équitable
* Équilibre : toutes les parties du système sont occupées

## Sémaphore
Système à multiple jetons, penser au "dîné des philosophe"

## Mutex
Prendre possession d'un système et personne peut lui toucher jusqu'à ce que le propriétaire l'ait libéré.

## <span style="color:red">À vérifier le reste du cours, j'ai sûrement oublier de quoi</span>

