---
tags: [GTI611, GTI611-2]
title: GTI611- Chapitre 10 - Les réseaux de capteurs
created: '2019-07-17T13:25:30.478Z'
modified: '2019-07-17T14:00:53.448Z'
---

# GTI611- Chapitre 10 - Les réseaux de capteurs

## Ce que tu connais
Sérieux c'est juste connecter pleins de sensors ensemble sur un réseau. Mais expliqué sûrement en version chiante.

## Les piles de protocoles
1. La couche physique
    1. Assure le transport de flux de données
1. La couche liaison de données
1. La couche réseau
1. La couche transport
1. La couche application

## Normalisation
Premier effort de "normalisation" on où on sépare en deux couches.
1. La norme IEEE 802.15.4 pour les douches 1 et 2 (Radio et MAC address)
1. La nome ZigBee pour les couches 3 et plus (adressage, routage, ...)

## Norme IEEE 802.15.4
C'est une norme rien de plus

## ZigBee
c'est un protocole de communication propriétaire comme Bluetooth. Même si l'enseignante fait croire que c'est meilleur que tous les autres compétiteurs.

ZigBee est reconnu pour sa **Simplicité d'implémentation** et sa **faible consommation d'énergie**.

ZigBee est un protocole ayant une porté comprise entre quelque mètres à quelques centraines de mètre a un débit faible (maximum 250 Kbps).

### Types de transmission
1. Unicast
1. Broadcat
1. Multicast

### Algorithme de routage
**AODV** permet d'étable des routes sans boucle à la volée et de les maintenir tant qu'un noeud en a besoin. C'est un protocole pour sauver le plus possible de l'énergie.

Comme ZigBee commençait à perdre du terrain face aux protocoles IP à basse consommation, ZigBee a commencé à intérer la pile TCP/IP dans leur protocole.
