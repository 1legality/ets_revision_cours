---
title: LOG645 - Cours 7
created: '2019-06-28T01:46:51.488Z'
modified: '2019-06-27T21:01:26.658Z'
tags: [LOG645, LOG645-2]
---

# LOG645 - Cours 7

## introduction au Multithreading

### Multitâche

Capacité à un système de traiter plusieurs tâches en même temps sur un processeur unique.

### Hyperthreading

C'est une technique multitâche pour mieux utiliser les ressources du processeur. Il ne faut pas confondre l'hyperthreading and un thread.

### Multitraitement

Capacité à un système de traiter plusieurs tâches en même temps sur plusieurs processueurs (système multicores ou multiprocessors)

### Multithread

Un processeur est dit multithread s'il est capable de gérer plusieurs threads simultanément. Capable d'exécuter plusieurs tâches en simultané dans une seule application.

### Thread

C'est une tâche légère correspondant à l'exécution d'un petit programme ou d'une routine d'un programme plus gros, indépendant de celui-ci.

Un thread ne peut pas exister sans processus mais un processus peut avoir plusieurs thread. De plus, les threads peuvent partager certaines informations entres-eux dans le processus.

Les avantages des threads

* Améliorer les temps de réponse
* Parallélisme
* Amélioration du rendement
* Communication
* Amélioration de la performance du programme
* Améliorer la structure du programme (simplicité de code)

#### Modèles de thread

Plusieurs-à-un

Un-à-un
