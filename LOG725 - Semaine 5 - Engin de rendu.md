---
title: LOG725 - Semaine 5 - Engin de rendu
created: '2019-06-11T16:40:30.416Z'
modified: '2019-06-18T15:43:20.493Z'
tags: [LOG725]
---

# LOG725 - Semaine 5 - Engin de rendu

## Introduction
C'est la composante principale d'un engin de jeu. Le but de l'engin de rendu est de dessiner les objets 3D sur l'écran. Dans le cours, on va voir...
* Pipeline graphique moderne
* Modélisation 3D
* Éclairage et effets
* Techniques avancées de rendu

On aime ça rendre les jeux toujours le plus réalisme possible.

## Rendu d'une scène 3D
* Caméra
* Une ou plusieures lumières
* Surfaces matéhmatiques 3D (points, polygones)
* Les propriétés visuelles des surfaces (ex : Couleurs, texture, transparence, matériel)

*frustun* : la zone 3D dans le champs de vision de la caméra. En forme de pyramide mais sans le bout piquant parce que le bout de la caméra est carré.

## Pipeline graphique moderne
On peut modifier les **Vertex Shaders** et les **Fragment Shader** le reste fait parti du engine ou des drivers seulement.

## Modélisation 3D
Les engins de rendu pour les jeux vidéos utilisent des maillages des polygones pour représenter une surface. On appel cela des **maillages triangulaires**.

Pourquoi des triangles plutôt que des cercle ou que des carrés?
* Les triangle est le plus simple des polygones.
* Ils sont toujours planaires
* Ils restent toujours des triangles malgré les transformations affines et projections.
* Tous les GPU sont optimisés pour la rastérisation triangulare aujourd'hui.

### Construction d'un maillage triangulaire
On a trois vertex : $P_1$, $P_2$, $P_3$.

#### Les arrêtes (lignes) sont donc.
$e_{12} = P_2 - P_1$
$e_{13} = P_3 - P_1$
$e_{23} = P_3 - P_2$

#### La normale
*Il faut utiliser la loi normale pour déterminer l'ordre*

$$n=\frac{e_{12} * e_{13}}{|e_{12} * e_{13}|}$$

## Sources de lumière
3 composantes d'intensité : Rouge, Vert, Bleu

### Ponctuelle 
* Va dans toutes les directions de manière uniforme
* Dépend de la position de la source (p)
* L'intensidé est inversement proportionnelle au carré de la distance (d) entre la lumière et le point sur la surface ~ $\frac{1}{d^2}$ (nommé falloff)

### Lumière spot
* Mêmes propriétés que la lumière ponctuelle avec 3 autres paramètres
  1. Direction $I_s$
  1. Angles de coupure: $\theta_{min}$, $\theta_{max}$
* Intensidé maximale si l'angle entre la lumière et la surface est moins de $\theta_{min}$, réduction progressive vers $\theta_{max}$, zéro en dehors.

### Lumière directionelle
* Ce sont des rayons parallèles qui possède une orientation mais que la position de la lumière est ignorée.
* Par exemple : le soleil.

## Éclairage
### Modèle de Phong
Concaténation de l'objet de base, de l'intensité de la lumière et des réflexions.

Les essentiels du modèle de Phong
$p =$ point sur la surface
$n =$ normale à la surface au point
$I =$ vecteur de la lumière
$r =$ vecteur de la lumière régléchie par lanormale
$v =$ vecteur à l'observateur (caméra)
$I_L =$ Intensité lumineuse

### Réflexion diffus
L'intensité de la lumiere diminue en fonction de l'angle ($\theta$). Si l'angle est à 90° on aura aucune reflexion par exemple. On a la lumière (I) et la normale (n)

$$I=I_L=\alpha * I_L | \alpha = \cos(\theta)$$
$$\cos(\theta)=n * l -> \frac{n * l}{||n|| * ||l||}$$

Il existe certaines variantes pour faire les réflexions de lumières, on peut aussi mélanger des variantes ensemble par exemple Blinn-Phong.

### Lightmap
Les calculs d'éclairage sont precalculées (ou baked) pour réduire le coût des calculs d'éclairage lors du runtime.

## Caméras

### Frame buffer
L'imagine finale est générée en dessinant la coordonnéee x et y de l'espace clip homogène et en ignorant z (sur l'écran.)

Les engins de rendu ont typiquement au moins deux frame buffers.
* Un qui est parcouru par la carte graphique pour l'affichage
* L'autre qui est mis à jour par l'engin de rendu (pour l'afficher à l'écran)

Ça peut créer du screen tearing. le VSYNC corrige un peu la situation (la carte graphique doit attendre après le moniteur pour que ça fonctionne)

On peut aussi utiliser trois frame buffer... Ça créer un petit délais d'image.

## Rastérisation
C'est lorsqu'on fait le rendering pour l'écran directement.

Z-Buffer : on dessine les éléments selon leur prodondeur, les plus distant en premier puis on place les plus proche par la suite comme un peintre ferait en faisant une peinture. Le nombre de Z-buffer dépend de la carte graphique... entre 20 et 40 bits environ, 32 bits étant bon.

Z-Fighting : c'est lorsqu'on a deux surface très proche et qu'il n'est pas vraiment possible de savoir quel élément est au dessus de l'autre. On se ramasse avec un mélange des deux surfaces ensembles..

### Culling
C'est lorsqu'on évite de dessiner les faces (ou maillages) à l'extérieur du volume de vue pour sauver de la performance.
