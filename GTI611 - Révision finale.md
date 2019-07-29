---
tags: [GTI611, GTI611-2]
title: GTI611 - Révision finale
created: '2019-07-29T19:02:54.541Z'
modified: '2019-07-29T20:56:41.981Z'
---

# GTI611 - Révision finale

## Chapitres à l'examen
```3-4-5-7-8-9-10```

## 3 - Protocole IPv6

* Rappel IPv4
* Protocole IPv6
  * En-tête IPv6
  * Adresses IPv6
  * En-têtes d'extension
* Protocole NDP
* Déploiement de IPv6 avec IPv4

## 4 - Routage IPv6

### Types de routage
#### Routage RIP
Routage "idiot" chaque routeur connait son routeur voisin seulement. À toutes les 30 secondes, un partie ou tout le contenu des tables de routage est transmis au voisins. S'il y a un changement de métrique d'une route, tout le monde doit se mettre à jour. Bon pour les petits réesaux où tout est atteignable en moins de 15 sauts.

### Routage OSPF
Échange seulement l'information lorsqu'il y a une différence dans la topologie, donc beaucoup moins de traffic inutile comme RIP.Coût basé sur la bande passante plutôt que sur le nombre de saut.

### Routage BGP
Protocole pour les gateway extérieurs (WAN). Permet par exemple à un ISP que ses clients restent sur son réseau le plus possible avant d'envoyer le requête à l'externe pour sauver de l'argent.

* Coexistence de IPv4 et IPv6
* Routage Dual-Stack
* Transmission tunnel de IPv6 à travers IPv4
* Interconnexion de IPv6 avec IPv4 (NAT64)

## 5 - Réseau locaux et virtuels

### VLANs (Virtual Local Area Network)
Permet d'avoir plusieurs réseaux sur le même routeur.

### Protocole Spanning Tree (STP)
Permet de supprimer les chemins redondants. En faisant les Noeud racine, Noeud désignés, port racines et port désignés.

### VLAN trunking protocole (VTP)
* Communications Inter-VLANs
* VXLANs (Virtual Extensible LAN)

## 7 Réseaux programmables

* Introduction
* Principes de base
* Architecture SDN et ses composantes

### Protocole Openflow
OpenFlow is a programmable network protocol designed to manage and direct traffic among routers and switches from various vendors. It separates the programming of routers and switches from underlying hardware. It is the result of a six-year research collaboration between Stanford University and the University of California at Berkeley.


* Domaines d’application de SDN

## 8 - Réseau virtuels et infonuagique

### Infonuagique
Permet un accès sur demande à des ressources partageables et configurables offertes par différents réseaux de communications. ces ressources peuvent être fournies et libérées rapidements avec un minimum d'effort de gestion ou d'interaction.

Il existe 2 types de services infonuagiques
1. Avec support de l'élasticité n'importe quand et n'importe où
1. Service mesuré : resources contrôlées et optimisées.

Il y a aussi plusieurs types de services offert
1. SaaS (software as a service)
    - Logiciel avec abonnement principalement.
1. PaaS (Plarforme as a service)
    - Les outils de développement (eg : eclipse, plugin, google AppEngine)
1. IaaS (Infrastructure as a Service)
    - Centre de donées

### Virtualisation

Permet de diviser les ressources physiques en des ressources virtuelles. Par exemple avec des containers.

2 types de scalability
1. Échelonnement vertical en augmentant la capacité d'un ordinateur/serveur (exemple : upgrader ram)
1. Échelonnement horizontal en augmentant le nombre d'ordinateur/serveur.

#### Concept NFV (Network Function Virtualisation)

Pour permettre d'avoir certains élément physique en SaaS. Par exemple avoir un pare-feu distant, un serveur distant ou un serveur de balancement de charge.

## 9 - Les réesaux cellulaires

### Les bases de données cellulaires
* Homes Location Register (HLR)
  * Information sur la localisation des usagers
  * Abonnées du réesau
  * Lorsque le MS se déplace, l'adresse de VLR est mise à jour
* Visitor Location Register (VLR)
  * Visiteurs provenant de réseaux avec lesquels l'opérateur a des accords d'itinérance
  * Lorsque le MS se déplace, les données sont transmises à un autre VLR

### Le 5G
Pleins d'appareils partout en deviennent des antennes émettrices. Utilise la virtualisation pour pas par exemple qu'un client résidentiel ait accès au contenu qui se passe sur son routeur lors qu'i lagit en tant qu'antenne 5G.

## 10 - Les réseaux de capteurs

Les noeuds capteurs ont des sources d'alimentations limitées (par exemple en étant alimenté uniquement par une batterie.) Ils se concentrent donc principalement sur la conservation de l'énergie.

La communication à sauts multiples sera exploitées car elle minise la consommation d'énergie en faisant plusieurs petits sauts plutôt qu'un seul gros qui demande plus de puissance.

On tente de normaliser ces réseaux mais il y a présentement beaucoup de compétition car celui qui réussira à normaliser le tout aura sûrement des milliards en redevances.

On appel ces types de réseaux des **LR WPAN** (Low Rate Wireless Personal Area Network)

Dans le cours on parle de la norme IEEE 802.15.4 ainsi que ZigBee.

La norme dicte les fréquences utilisées (en fonction du pays), la topologies possible des réseaux ainsi que certains éléments de la couche physique et liaison.

### Les types de topologies
1. Point à point
1. Étoile (un serveur au milieux)
1. Arbre de grape (cluster) chaque FFD est lié au moins à un FFD)
1. Maillé

### ZigBee IP
Comme certains compétiteurs commençaient à offrir des systèmes low rate wireless par adresses IP, ZigBee ont commencés à permettre cette utilisation aussi.
