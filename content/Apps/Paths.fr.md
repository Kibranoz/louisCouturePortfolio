+++
title = "Paths"
description = "L'application Paths"
date = "2025-11-14"
aliases = ["paths"]
author = "Louis Couture"
+++
Cette application vous permet d'ajouter des chemins à votre variable PATH dans une interface graphique. Vous pouvez également définir des alias et l'emplacement de ces scripts.

![Path setup app screenshot](/images/paths/path.png)
![Path setup app alias screenshot](/images/paths/alias.png)

## FAQ 
### Comment fonctionne l'application ?
Cette application utilise le dossier .bashrc.d de Fedora, elle ne modifie donc pas votre fichier .bashrc. Si vous utilisez une autre distribution Linux, elle créera un dossier .bashrc.d et ajoutera le code suivant à votre fichier .bashrc
```
if [ -d ~/.bashrc.d ]; then
    for rc in ~/.bashrc.d/*; do
        if [ -f "$rc" ]; then
            . "$rc"
        fi
    done
fi
unset rc
```
Ce script parcours le dossier .bashrc.d et va inclure le code des fichiers dans .bashrc, ce qui fera en sorte que les chemins et les aliases seront disponible dans une session bash.
### Pourquoi cette application ?
Bien qu'il soit possible de gérer vos chemins depuis un fichier, certains utilisateurs sont moins familiers avec la syntaxe de type code pour la gestion des chemins et des alias. Certains peuvent également trouver plus rapide d'ouvrir une interface graphique pour ajouter leurs chemins plutôt que de les ajouter via .bashrc
Cela a été créé dans le but de rendre la famille de systèmes d'exploitation utilisant des outils tels que le noyau Linux et la bibliothèque GNU (communément appelés Linux ou LiGNUx) plus conviviaux
### J'ai ouvert l'application et mes chemins n'ont pas été ajoutés 
Ce n'est pas une fonctionnalité prise en charge. L'application gère uniquement les chemins et alias qui ont été configurés dans l'application.
