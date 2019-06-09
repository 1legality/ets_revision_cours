---
title: GTI611 - Cours 5 - Réseaux locaux virtuels
created: '2019-06-08T18:31:47.119Z'
modified: '2019-06-08T18:34:11.597Z'
tags: [GTI611, GTI611-1]
---

# GTI611 - Cours 5 - Réseaux locaux virtuels

## VLANs
C'est comme un LAN mais géré au niveau logiciel seulement. Permet donc d'avoir plusieurs routeur tous connectés sur le même "VLAN". Par exemple : un routeur 2 réseaux vlans.

Permet par exemple d'avoir de la sécurité en mettant les serveur sur un VLAN et les ordinateurs privés sur un autre.

## STP et MSTP
### Protocole Snanning Tree (STP)
Permet de désactiver les boucles de commutation, notamment en effacant les chemins redondants.

Chaque commutateur possède un identifiant SID qui est la concaténation de la priorité et de l'adresse MAC d'un commutateur. Le commutateur avec l'identifiant le plus petit (souvent priorité plus petite) est désigné comme le noeuf racide.

[Priorité][Mac]

#### Étapes de connexion STP
1. Identifier le commutateur racine
1. Identifier les ports racines sur les autres commutateurs. Ces ports doivent avoir le coût le plus faible vers le commutateur racine.
1. Identifier les ports désignés sur chaque segment SETP. Doivent avoir le coût le plus faible vers commutateur racine.
1. Bloquer tous les autres ports sur chaque segment STP pour éviter les boucles de commutation.

#### Avantages
- Algorithme stable
- Élimine les boucles dans un réesau en bloquant des ports
- Empêche la duplication des trames et les Broadcast Storm
#### Inconvénients
- Les performance ne sont pas optimale
- Utilisation inefficace des liens du réseau due au blocage des liens alternatifs

## VLAN trunking protocol (VTP)
VTP facilite la configuration des VLANs en diffusant leurs configurations à travers un réseau. 

Permet de répliquer les VLANs mais ne permet pas de configurer les ports Access et Trunk : ils doivent être configurer à part.


Fonction|Serveur|Client|Transparent
--------|-------|------|-----------
Diffuse message VTP | O | N | N
Traite message de diffusion reçu | O | O | N
Restransmet les messages de diffusion reçus | O | O | O
Créer, modifie o usupprime des VLANS | O | N | O

## Limitation des VLANs
* STP impose des restrictions au niveau de la résilience du réseau. Elle entraîne une utilisation inefficace des liens du réseau due au blocage des liens alternatifs.
* STP et MST demeurent limités pour les réseau de grande taille. Le délais de convergence augmente avec l'augmentation de la taille du réseau.
* Solution : VXLan

## VXLans (Virtual Extensible LAN) - Cisco seulement
Faire un tunnel entre deux routeurs pour en faire un gros VLAN unique.
