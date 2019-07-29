---
title: GTI611 - Récapitulatif partie 1
created: '2019-06-15T14:01:38.879Z'
modified: '2019-06-16T16:11:53.169Z'
tags: [GTI611, GTI611-1]
---

# GTI611 - Récapitulatif partie 1

# Protocole IPv4
Allocation flexible CIDR a.b.c.d/x avec x nombre de bits.

Trois plages d'adresses IP privées
* 10.0.0.0 à 10.255.255.255 ($2^{24}$ adresses)
* 172.15.0.0 à 172.31.255.255  ($2^{20}$ adresses)
* 192.168.0.0 à 192.168.255.255 ($2^{16}$ adresses)

# Protocole IPv6
Formats d'une adresse IPv6

* Préfixe de routage globale (48 bits)
  * IANA (12 bits)
  * RIR
  * RIR ou FAI (16 à 24 bits)
* ID du sous-groupe (16 bits)
* ID de l'interface (64 bits)

Types d'adresses IPv?
* 0.0.0.0.0.0.0.0/128 | non spécifiée
* 0.0.0.0.0.0.0.1/128 | Adresse loopback
* FE80::/10 | Adresse unicast locale à un lien
* FC00::/7 | Adresses unicast locale unique (VPN)
* FF00::/8 | Adresses multicast
* Autres | Adresses unicast globale

### Planification de l'adressage IPv6
Les types d'affectations sont
* Affectation selon le nombre de site
* Affectation au sein d'un site
* Affectation basée sur les fonctions d'un site
* Affectation basée sur l'emplacement géographique du site

## Protocole NDP (Neighbor Discovery Protocol)
C'est un protocole qui utilise des messages ICMP IPv6 pour découvrir les adresses IPv6 des voisins connectés aux extrémités des interfaces.

Permet de faire la découverte de routeurs et de leurs préfixes et de leur MTU ainsi que du nombre maximal de saut.

## Routage
### RIP
C'est le routage le plus simple : tous les routeurs connaissent leur voisin sans plus. Ils maintiennent une table de routage avec un nombre de saut limité à 15.

Chaque routeur partage l'information au sujet du plus court chemin seulement avec ses voisins à des intervales de 30 secondes.

### OSPF
Maintien la table de routage ainsi que la liste des coûts, chaque coût représentant la bande passante de référence. Les messages OSPF sont encapsulés directement dans un paquet IP.

### BGP
<span style="color:red">à vérifier..</span>

## Cohexistence entre IPv4 et IPv6
### Routage double pile
* tous les appareils ont à la fois une adresse IPv4 et une adresse IPv6

### Transmission tunnel de IPv6 à travers IPv4
Il existe plusieurs mécanismes qui permettent de faire des requêtes IPv6 en passant pas l'IPv4.

* 6to4
  * Nécessite une adresse publique IPv4 par site
  * Un paquet ayant une adresse native IPv6 est transmis à un routeur relai 6to4. L'adresse IPv6 est associé au tunel, le mécanisme 6to4 encapsule le paquet IPv6 dans un paquet IPv4 pour les transferts.
  * Utilise come préixe 2002::/16 
* 6RD
  * Même chose que 6to4 mais avec un préfix lié à un FAI

### NAT64
Permet de traduire une adresse IPv6 en adresse IPv4.

## Réseaux privés (LAN)
### Protocole Spanning Tree (STP)
Permet d'éviter la formation de boucles de commutation dans le réseau en désactivant les chemins redondants.

Suivre les 4 étapes...
1. Déterminer le commutateur racine
1. Déterminer les ports racines
  1. C'est le port ayant le coût le plus faible (selon le débit)
1. Déterminer les ports désignées
  1. C'est souvent le port relié au port racine
1. Bloquer tous les autres ports

### VLAN
La différence entre un VLAN est un LAN c'est qu'il est possible de créer plusieurs VLAN sur le même équipement physique alors qu'il est impossible d'avoir plus LAN sur un seul. On parle de VirtualLAN.

Chaque réseau VLAN regroupe des machines selon des critères (numéro de port, mac address, protocole de communication) les trois représentant des niveaux différents.

* Niveau physique (VLAN niveau 1)
  * Ensemble de machine appartenant au même réseau physique (relié avec des ports)
* Niveau liaison (VLAN niveau 2)
  * Ensemble de marchines regroupé selon leur MAC adress
* Niveau réseau (VLAN niveau 3)
  * Ensemble de machines regroupé selon leur adresses IP

2 types de ports VLAN
1. Les ports Access
  1. Ensemble de ports d'un commutateur auxquels des machines sont conectées
  1. Ces ports doivent être configurés pour être associés à un VLAN
  1. EG : port FA0/1, FA/01 de SW1 et SW2 (SW étants des Switch)
1. Les ports Trunk
  1. Ensemble de ports permettant de connecer les commutateurs entre eux
  1. Ces ports doivent être configurés en mode "trunk" pour offrir l'accès au trafic provenant de plusieurs VLANs
  1. Le port Fa0/3 sur SW1 et SW2

Entre un line trunk on retrouve un VLAN natif. Un VLan natif permet de laisser passer les trames reçu n'ayant pas de VLAN ID sur un lien trunk... Tous les ports d'un commutateur sont associés au VLAN natif.
