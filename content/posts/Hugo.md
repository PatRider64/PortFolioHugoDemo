+++
title = 'Hugo'
date = 2023-11-14T14:51:38+01:00
draft = false
tags = ['Hugo']
author = "Patrik Pucelj"
+++

# Introduction
**Hugo** est un générateur qui permet de créer des sites web statiques de manière rapide et efficace. Il utilise du *markdown*, un langage de balissage léger utilisé pour l'écriture de contenu formaté et conçu pour être facile à lire et écrire.

Pour créer un site avec Hugo, il suffit de taper la commande *hugo new site monsite* et pour démarrer le serveur local : *hugo server -D*.

On peut choisir un thème pour le projet sur [HugoThemes](https://themes.gohugo.io/). Après avoir choisi le thème, sur la terminal de commande, il faut saisir *git submodule add [url] themes/[nom du thème]* et dans le fichier hugo.toml, il faut rajouter *theme = 'ananke'*.

# Hébergement à GitHub Pages

GitLab Pages nous permet d'héberger un projet Hugo.
Pour cela, il faut naviguer dans le dossier public, puis initialiser un dépôt Git (git init), ajoutez (git add .)
et committer (git commit -m "Initial commit") les fichiers.
Après, il faut créer une branche gh-pages avec git branch -M gh-pages.
Enfin, il faut ajouter le dépôt GitHub comme remote (git remote add origin [URL du Dépôt GitHub]) et
pousser le contenu avec git push -u origin gh-pages.
Dans les paramètres du dépôt GitHub, dans la section "Pages", il suffit de sélectionner la branche gh-pages comme source, et sauvegarder.

Alternativement, on peut automatiser le déploiement en utilisant GitHub Actions.
Dans la section "Pages", il faut sélectionner "GitHub Actions" comme source et ensuite on sélectionne "Hugo" comme Workflow ce qui va créer un fichier *hugo-deploy.yml* dans le dossier *.github/workflows* pour automatiser la construction et le déploiement du site Hugo.

dgdg