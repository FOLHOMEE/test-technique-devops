# Test technique Devops Folhomee

## Contexte

Les buts de ce test technique sont les suivants :

- Nous permettre de voir votre niveau technique
- Essayer de déterminer vos capacités concernant la résolution de problèmes
- Voir si vous pourriez vous intégrer au sein de notre équipe technique

L'objectif de ce test technique est de créer une configuration pour le développement puis pour le déploiement en prod pour une application nodejs

Il est important de respecter les consignes suivantes :

- Ne sautez pas un exercice, il faut respecter l'ordre
- Vous n'avez pas besoin d'utiliser un service externe pour les exercices, sauf quand c'est explicitement demandé
- Il est très facile de trouver des résolutions/solutions de ce test en ligne, aussi vous serez jugé sur votre capacité de structurer votre code

## Livrables

Les livrables minimum sont les suivants :

- Un **nouveau repo github privé** auquel vous aurez donné accès au CTO de Folhomee (username github : [milanito](https://github.com/milanito)), qui est créé en clonant celui ci
- Un ensemble de dossiers/fichiers selon une nomenclature claires
- Pour chacun des exercices, le temps que vous avez mis à le réaliser au travers d'un README que vous essayerez de détailler (le markdown est recommandé), de préférences individuellement pour chaque partie

Dans le README, vous devrez essayer de répondre aux question suivantes :

- Quels sont les principes que vous avez appliqué
- Pouvez-vous expliquer les décisions que vous avez prise et pourquoi c'est la meilleure approche
- Quelles sont vos recommandations pour un travail futur

Nous vous demanderons en plus de respecter la contrainte technique suivante :

- Le code devra être écrit en javascript et tourner sur node LTS (v12 au moment de l'écriture de ce test)

Pour le reste, vous êtes libre de vos choix technique quand il n'est pas explicitement dit dans l'exercice le choix à faire

## Exercices

L'API qui est utilisée pour cet exercice se trouve dans le dossier `server`, elle est fonctionnelle

### Configuration de développement

Nos développeur sont un peu fainéant, et ils ne veulent pas avoir à installer le nécessaire pour faire tourner le server en local, pour cet exercice, vous devez :

- Créer un docker file et un fichier docker compose pour permettre aux développeur de lancer rapidement la stack sans avoir rien d'autre d'installé sur leur machine que docker

#### Bonus

- On aime bien ne pas perdre de temps à builder
- On aime bien regarder des logs propres (pas besoin d'améliorer ceux du serveur, il a été généré automatiquement)

### Dockerfile de production

Maintenant que les développeurs peuvent travailler tranquillement en local, ils veulent pouvoir déployer rapidement leur API, pour cet exercice, vous devez :

- Créer un dockerfile de production, en faisant attention à proposer une image qui ne soit pas trop lourde

#### Bonus

- On aime vraiment ne pas perdre de temps à builder
- Faites nous rêver

### Déploiement continu

Décidement, nos développeurs ne veulent rien faire de manuel ! Il veulent pouvoir builder une image docker sans effort. Pour cet exercice vous devez :

- Créer une configuration github action qui va builder et push l'image, construite à partir du dockerfile de production, sur le registery docker (utilisez un compte gratuit) à chaque push sur la branche master

#### Bonus

- Il existe de nombreuses choses qui peuvent être faites (notification, message slack, etc ...), à vous de nous dire ce qui vous semble le plus pertinent

### Déploiment sur AWS

Maintenant que tout semble plutot ok, les développeurs veulent être capable de déployer sur AWS. Pour cet exercice vous devez :

- Créer une configuration terraform (contenant d'éventuels script) pour pouvoir déployer notre API sur AWS en utilisant Elastic Container Service.
- Les développeurs veulent un environnement sécurisé et isolé en ayant la possibilité de run plusieurs container sur une instance

#### Bonus

- On aime bien quand on push sur master que ca déploie sur AWS
- On aime bien être prévenu
- Faites nous rêver
