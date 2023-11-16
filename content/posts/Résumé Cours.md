+++
title = 'Résumé du Cours'
date = 2023-11-14T14:52:06+01:00
draft = false
tags = ['Git', 'GitHub', 'Hugo']
author = "Patrik Pucelj"
+++

# 1 Git et GitHub

## 1.1 Introduction

**Git** est un système qui enregistre toutes les modifications de fichiers au fil du temps.
Les *commits* représententent les modifications de fichiers apportées à un moment donné du projet tandis que les *branches* permettent aux développeurs de travailler sur des fonctionnalités en parallèle et les *merges* fusionnent les modifications d'une branche dans une autre.

Liste de commandes Git : 

    - git init
    - git clone [url]
    - git commit m "[message]"
    - git push
    - git pull

**GitHub** est une plateforme qui permet de stocker des répertoires, de collaborer sur des modifications, et de gérer le développement de logiciels.
Les *issues* nous permet de signaler des bugs, demander des fonctionnalités et discuter des aspect du site et les *pull requests* permettent de proposer des suggestions de modifications de fichiers et les faire vérifier par d'autres membres de l'équipe.

## 1.2 Pourquoi utiliser Git et GitHub ?

Git et GitHub sont deux outils extrêmement utiles puisqu'ils permettent aux équipes de gérer efficacement les contributions individuelles et les révisions de code, offrent une vue d'ensemble  des changements effectués sur un projet,
permettant de comprendre l’évolution du code et possèdent des outils intégrés pour la planification, le suivi des problèmes et la gestion des fonctionnalités.

# 2 Hugo

## 2.1 Introduction

**Hugo** est un générateur qui permet de créer des sites web statiques de manière rapide et efficace. Il utilise du *markdown*, un langage de balissage léger utilisé pour l'écriture de contenu formaté et conçu pour être facile à lire et écrire.

Pour créer un site avec Hugo, il suffit de taper la commande *hugo new site monsite* et pour démarrer le serveur local : *hugo server -D*.

On peut choisir un thème pour le projet sur [HugoThemes](https://themes.gohugo.io/). Après avoir choisi le thème, sur la terminal de commande, il faut saisir *git submodule add [url] themes/[nom du thème]* et dans le fichier hugo.toml, il faut rajouter *theme = '[nom du thème]'*.

## 2.2 Hébergement à GitHub Pages

GitHub Pages nous permet d'héberger un projet Hugo.
Pour cela, il faut naviguer dans le dossier public, puis initialiser un dépôt Git (*git init*), ajouter (*git add .*)
et committer (*git commit -m "Initial commit"*) les fichiers.
Après, il faut créer une branche *gh-pages* avec *git branch -M gh-pages*.
Enfin, il faut ajouter le dépôt GitHub comme remote (*git remote add origin [URL du Dépôt GitHub]*) et
pousser le contenu avec *git push -u origin gh-pages*.
Dans les paramètres du dépôt GitHub, dans la section "Pages", il suffit de sélectionner la branche *gh-pages* comme source, et sauvegarder.

Alternativement, on peut automatiser le déploiement en utilisant GitHub Actions.
Dans la section "Pages", il faut sélectionner "GitHub Actions" comme source et ensuite on sélectionne "Hugo" comme Workflow ce qui va créer un fichier *hugo-deploy.yml* dans le dossier *.github/workflows* pour automatiser la construction et le déploiement du site Hugo.
