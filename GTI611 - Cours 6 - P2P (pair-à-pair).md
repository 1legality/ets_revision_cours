---
title: GTI611 - Cours 6 - P2P (pair-à-pair)
created: '2019-06-08T18:33:17.985Z'
modified: '2019-06-12T03:38:31.964Z'
tags: [GTI611, GTI611-1]
---

# GTI611 - Cours 6 - P2P (pair-à-pair)

## Réseau Client/Serveur vs P2P

Client | Serveur | P2P
-------|---------|----
initie la requête | fournit le service | fait les deux
Pas toujours performant | Peu manquer de ressources | voir plus bas

* Avantages
  * Aucune entité centrale et pas de service dédié
  * Meilleure flexibilité pour les paires en termes d'accès et de consommation de ressources
  * Moins vulnérable par le nombre d'appareil utilisés comme serveur
  * Facile à utiliser
  * Applications P2P souvent gratuites
  * Contribution souvent altruistes et pas limitées à une location géographique
* Problèmes P2P
  * Maintenir la connectivité entre les noeuds
  * La confiance entre les pairs
  * Recherche des pairs/ressources (résolution du nom, localisation du pair, routage)
    * Les pais peuvent entrer et sortir du système n'importe quand
    * Où Stocker? Qui garde quoi?
  * Renforcement des droits d'auteurs pour empêcher le partage de certains contenus
  * Trafic P2P bloqué par les FAI de certains pays

## Architecture P2P

* P2P pur
  * Architecture totalement distribuées
  * Très rare
* P2p Hybride
  * Certain niveau de centralisation (par exemple pour authentifier un utilisateur)

## Modèles
* Communication
  * Symétrique (tous les pairs peuvent faire le même rôle)
  * Asymétrique (chaque pairs ont un rôle différent)
* Interaction
  * Anonyme
  * Non-Anonyme (utilisateur connecté à un serveur centrale)
  * Pseudo-Anonyme (nom d'utilisateur facultatif)

## Exemples populaires de logiciels P2P
* Napster
* BitTorrent
* Skype (pas depuis 2016 mais même si le cours a été fait en 2017, ça été prit en compte)

## Challenge distribution de contenu
1. Trouver l'ensemble des pairs pour télécharger un contenu
1. Réplication du contenu, prioriser les fragments "rares" pour qu'ils le soient moins
1. Utilisateurs peu altruistes qui préfèrent recevoir que de donner

## Réseau de recouvrement P2P

Deux type
* Non-structuré
* Structuré

## Non-structuré
données placées à des endroits aléatoires. Surcoût et plus de latence lors de la recherche d'une portion de contenu comparativement aux réseau de recouvrement structurés.

* Naspter
* Freenet
* KazaA
* BitTorrent

## Structuré
Données placées à des endroits spécifiques. Permet de rechercher des données de manière très efficase.

* Content Addressable Network (CAN)
* Chord
* Tapestry
* Pastry
* Kademlia
* Viceroy

## Plateforme JXTA
Permet de placer des éléments l'un à côté de l'autre. Le but de JXTA est de standardiser la façon que les pairs découvrent les autres pairs, leur manière de communiquer entre eux et de mieux comprendre les ressources de chacun.

3 types de pairs
1. Micro-pair
  * Peut envoyer et recevoir mais ne peut pas annoncer les autres pairs.
1. Pair simple
  * Meme chose que Micro-pair mais peut annoncer les autres pair. Elle ne transmet pas la requête de découvete à un autre pair par contre.
1. Super-Pair
  * Pair Rendez-vous
      * Pair simple mais qui peut aider les autres pais à découvrir les resources.
      * Devrit être en mesure de garder en cache un grand nombre d'annonces.
  * Pair relay
      * Permet d'acheminer les messages vers les autres pairs dans un réseau physique.
  * Pair proxy
      *  Utilisé par les micro-pairs. Il stocke les annonces et traite les messages provenant des micro-pairs.

