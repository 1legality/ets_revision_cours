---
title: LOG645 - Cours 3 - Les métriques
created: '2019-06-08T18:36:59.204Z'
modified: '2019-06-11T13:30:04.549Z'
tags: [LOG645, LOG645-1]
---

# LOG645 - Cours 3 - Les métriques

## Temps d'exécution
$T_P \text{ est le temps d'exécution sur P processeur}$
$T_1  \text{ est le temps d'éxécution sur 1 processeur}$

$T = T_\text{comp} + T_\text{comm} + T_\text{idle}$

### Temps de communication
Dépend de
* L'architecture parallère
* Taille des données

### Temps d'attente
Dépend de
* Ordre d'éxécution des opérations
* Complexisté et dimension du problème (N)
* Nombre de tâches dans les processeurs
* Grosseur des tâches
* Type de processeur

## Accélération
$S = \frac{t_1}{t_p}$


Si | Signification
-- | -------------
`S = 1` | Code séquentiel à 100%
`S = p` | Code purement parallèle
`S <= p` | Code avec parallélisme 

## Efficacité

$E = \frac{S}{P} = \frac{t_1}{P * T_p}$

## Loi d'Amdalh

$S = \frac{P}{1+\alpha*(P-1)}$

$\alpha \text{ est le pourcentage parallélisable}$

## Loi de Gustafson
(très similaire à la loi d'Amdalh)

$S = P-\alpha*(P-1)$

$\alpha \text{ est le pourcentage parallélisable}$

## Loi de Karp-Flatt
Prend en considération le temps nécessaire pour faire du paralléliste

$e = \frac{\tfrac{1}{s}-\tfrac{1}{p}}{1-\tfrac{1}{p}}$

e = Proportion séquentielle optimale

## Facteur réduisant S et E
* Surchage des algorithmes
* Trop de code séquentiel impossible à paralléliser
* Surcharge logicielle (augmente alpha)
* Déséquilibre de la charge de travail


