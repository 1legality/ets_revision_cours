---
title: GTI611 - Cours 4 - Routage
created: '2019-06-08T18:29:37.371Z'
modified: '2019-06-09T15:55:47.094Z'
tags: [GTI611, GTI611-1]
---

# GTI611 - Cours 4 - Routage

## Routage Interne
2 types de routages à l'interne : *rip* et *OSPF*.

Le but de faire du routage à l'interne est de trouver le meilleur chemin à travers lequel les paquets seront acheminés.

## RIP
Chaque routeur connait sont voisin seulement. Il existe seulement deux types de requêtes en RIP.
1. Demander la table de routage au routeur voisin
1. Envoyer la table de routage au voisin lorsqu'il la demande.

Une demande de mise à jour est demandé environ aux 30 secondes par chaques routeurs.

### Désavantages de RIP
1. Les changements peuvent être lent à propager partout sur le réseau
1. Il y a une limite de 15 sauts pour éviter des bonds infinis

## OSPF
Les routeurs communiquent leurs tables de routage entre-eux avec un algorithme basé sur l'algorithme de Dijkstra.
1. Chaque routeur connait la distance de son voisin

<span style="color:red">Il manque certainement des éléments de ce cours la à vérifier</span>
