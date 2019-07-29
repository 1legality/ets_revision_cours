---
title: GTI611 - Cours 3 - Protocole IPv4/IPv6
created: '2019-06-08T18:28:12.346Z'
modified: '2019-06-09T16:07:01.285Z'
tags: [GTI611, GTI611-1]
---

# GTI611 - Cours 3 - Protocole IPv4/IPv6

## IPv4
C'est le type d'adresse encore la plus utilisées aujourd'hui. La taille des adresses IPv4 limitées à 32 bits. Il existe présentement une pénuerie de ce type d'adresse, donc on prévoit changer avec IPv6 un jour.

### Classes des adreses IPv4
1. A : 001@127.0.0.0/8
1. B : 128@191.x.0.0/12
1. C : 192@223.x.x.0/16
1. D : 224@240.x.x.x/24 (multicast)
1. E : 240@255.x.x.x/32 

Dans un réseau IPv4 première et dernières adresses sont réservées.

## NAT
Permet de créer plusieurs adresses à l'intérieur d'un réseau. Trois sortes d'adresses peuvent être utiliser pour des réseaux privés (NAT).

1. 10.0.0.0 @ 10.255.255.255
1. 172.16.0.0 @ 172.31.255.255
1. 192.168.0.0 @ 192.168.255.255

## DHCP
Permet d'allouer automatique des adresses IP dans un réesau.

## Adressage IPv6
Il existe plusieurs débuts d'adresses IPv6 prévues à certaines utilisations
* :0:0:0:0:0:0:0/128
  * adresse non spécifiée
* 0:0:0:0:0:0:0:1/128
  * adresse de bouclage (loopback)
* FE80::/10
  * adresse univast locale à un lien
* FC00::/7
  * adresse unicast locale unique (VPN)
* FFDD::/8
  * adresse multicast
* autre
  * adresse multicast globale

De tous cela, il existe trois types d'adresses.
1. Unicast
  1. C'est un identificateur pour une seule interface.
  1. Le paquet est transmis à l'interface possédant cette adresse uniquement.
1. Anycast
  1. C'est un identificateur pour un ensemble d'interfaces.
  1. Le paquet est transmis à une seule interface : celle la plus proche. 
1. Multicast
  1. C'est un identificateur pour un ensemble d'interfaces.
  1. Le paquet est transmis à l'ensemble des inferfaces.
  1. Remplace la fonction "Broadcast"

### Affectation d'adresses selon le nombre de site
On considère qu'un organisation ait besoin de plus que 65000 sites...

Préfixe de routage global | Nombre de site
--------------------------| --------------
/48 | 1
/44 | 16
/40 | 256
/36 | 4096
/32 | 65536

## Raisons d'utiliser IPv6 plutôt qu'IPv4
* Augmentation de la taille des adresses
* Simplification de l'en-tête des paquets
* Plus d'options
  * QOS
  * Sécurité
  * Mobilité




