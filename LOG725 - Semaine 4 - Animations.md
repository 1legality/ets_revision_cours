---
title: LOG725 - Semaine 4 - Animations
created: '2019-06-11T16:45:25.905Z'
modified: '2019-06-11T14:10:16.111Z'
tags: [LOG725]
---

# LOG725 - Semaine 4 - Animations

## Squelette
C'est une collection de pièces rigies qui donne les contraintes à un objet.

Permet de faire des animations plus naturelles.

## Jointure
Partie du squelette qui peut bouger avec par exemple des Quaternions.

### Pose globale
* Il est parfois utile d'exprimer la pose d'un joint en espace modèle ou espace monde.
* Pour y arriver, il faut parcourir la hiérarchie des joints vers la racine (jointure la plus centrée) en **multipliant** les poses locales rencontrées.

## Animations
Dans un jeu vidéo on utilise souvent plusieurs petites animations qu'on nomme des **clips d'animation** pour en faire des plus grosses.

Chaque clip a sa tâche définie, par exemple
* Lancer
* Sauter
* Courir
* Tomber

### Interpolation

#### Linéaire
$$P_{LERP}=(1 - \beta) * T_A + \beta * T_B$$ 

#### Linéaire sphérique
$$q_{SLERP}=\frac{\sin(\theta * (1 - \beta)) * q_A + \sin(\theta * \beta) * q_B }{\sin(\theta)}$$

où

$$\theta = \cos^{-1}(q_A * q_B)$$


### Skinning
Wtf?


### Animation Procédurale
On veut parfois faire des animations selon l'envionnement du jeu.

Par exemple une animation serait différente entre 2 personnages dans deux géométries différentes. Un personnage en habit d'été à la plage ne devrait pas marcher de la même manière qu'un personnage en habit d'hiver dans une montagne.

### Motion graphs
On peut créer toutes les animations avec des loops consécutifs. Les transitions entre les animations sont notés sur un graphe. Impossible de sortir du graphe de dépendance.

