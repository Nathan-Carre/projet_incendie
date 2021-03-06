# Projet d'informatique en Python du second semestre. 

## Contexte
L'objectif de ce projet est de mettre en place une solution permettant de simuler la propagation d'un incendie sur un terrain de 2500 parcelles. Chacune de ces parcelles à un état initial parmi les suivants :

- Eau
- Forêt
- Prairie

L'état d'une parcelle peut évoluer selon l'état des parcelles qui l'entourent. L'évolution des parcelles suit les règles suivantes : 

- une parcelle d’eau reste une parcelle d’eau durant toute la simulation;
- une parcelle qui devient en feu reste en feu durant 2 étapes de simulation avant de devenir des cendres tièdes pendant 1 étape de simulation et enfin devenir des cendres éteintes durant le reste de la simulation; les valeurs de ces deux constantes sont à définir et laissées à votre appréciation;
- une parcelle de prairie prend feu dès qu’une des 4 cases voisines (gauche, droite, haut, bas) est en feu;
- une parcelle de forêt prend feu avec la probabilité 0.1 × nf où nf est le nombre de ses voisins en feu;

On considère que les bords du terrain ne peuvent pas brûler et qu’ils n’interviennent pas dans la propagation du feu.

## Solution
La solution mise en place est doté d'une interface graphique permettant à l'utilisateur de générer aléatoirement un terrain de 2500 parcelles, de le manipuler, de simuler la propagation d'un incendie et de sauvegarder son état.

![alt texte](https://github.com/Nathan-Carre/projet_incendie/blob/main/ressources/Capture01.PNG)

### 1 - Générer un terrain 

Le bouton "Générer un nouveau terrain" comme son nom l'indique permet de générer un terrain de façon aléatoire. Celui-ci sera composé d'un nombre aléatoire de parcelles d'eau, de forêt et de prairie, représenté respectivement par les couleurs bleu, vert et jaune.

![alt texte](https://github.com/Nathan-Carre/projet_incendie/blob/main/ressources/Capture02.png)


### 2 - Première flamme 

Une fois le terrain généré l'utilisateur peut sélectionner une parcelle parmi les parcelles de forêt et de prairie disponible afin de l'enflammer. Cette sélection se fait par un simple click sur la parcelle en question, qui sera par la suite représentée par la couleur rouge. Une parcelle rouge est nécéssaire au fonctionnement de la simulation de l'incendie.

![alt texte](https://github.com/Nathan-Carre/projet_incendie/blob/main/ressources/Capture03.PNG)

### 3 - Effectuer une étape de simulation

Afin de pouvoir visualiser la propagation de l'incendie, il est possible d'effectuer manuellement une seule étape de la simulation. Pour ce faire l'utilisateur peut utiliser le bouton "Simuler (1 étape)".

![alt texte](https://github.com/Nathan-Carre/projet_incendie/blob/main/ressources/Capture04.PNG)


### 3 - Simulation Automatique

Tout comme la simulation manuelle, il est possible d'activer la simulation automatique. Celle-ci permet d'effectuer automatiquement 10 étape de simulation par seconde. Pour ce faire l'utilisateur peut utiliser le bouton "Simulation automatique".

![alt texte](https://github.com/Nathan-Carre/projet_incendie/blob/main/ressources/Capture05.PNG)

Une fois la simulation automatique lancée, il est possible de l'arrêter à tout moment en appuyant sur le bouton "Stop" qui aura remplacé le bouton "Simulation automatique".

![alt texte](https://github.com/Nathan-Carre/projet_incendie/blob/main/ressources/Capture06.PNG)


### 4 - Sauvegarder / Charger un terrain

La solution permet à l'utilisateur de sauvegarder son terrain à tout moment sous la forme d'un fichier texte. Pour ce faire il suffit de saisir le nom du fichier sans écrire l'extension ".txt" qui s'effectue automatiquement, dans la zone prévue à cet effet.

![alt texte](https://github.com/Nathan-Carre/projet_incendie/blob/main/ressources/Capture07.PNG)

Une fois le nom du fichier saisi, il suffit de cliquer sur le bouton "Sauvegarder le terrain" pour qu'il se sauvegarde dans le dossier où se trouve le fichier projet_inecndie.py.

![alt texte](https://github.com/Nathan-Carre/projet_incendie/blob/main/ressources/Capture08.PNG)

Une fois sauvegarder, un terrain peut être chargé ultérieurement afin de continuer la simulation. Cette manipulation est similaire à la précédente, il suffit donc de saisir le nom du ficher que vous avez choisi de donner lors de la sauvegarde, sans l'extension ".txt", dans la zone prévue à cet effet (la même que pour celle de la sauvegarde). Enfin, il vous suffit de cliquer sur le bouton "Charger un terrain".

![alt texte](https://github.com/Nathan-Carre/projet_incendie/blob/main/ressources/Capture09.PNG)


### 5 - Statistiques 

Afin de faciliter la visualisation et permettre à l'utilisateur de se rendre compte des proportions des différentes parcelles, une section statistique a été ajoutée à l'interface. Cette section est composée, en plus du label affichant le nombre total de parcelles afficher sur le canevas, de 5 labels mis à jour automatiquement. La section permet d'avoir un aperçu sur l'évolution de la quantité de chaque type de parcelles (Parcelles de feu, d'eau, de forêt mais aussi des parcelles de cendres tièdes et cendres chaudes) dans le terrain, en plus de l'évolution de l'incendie visible dans la fenêtre contenant le canevas.

![alt texte](https://github.com/Nathan-Carre/projet_incendie/blob/main/ressources/Capture10.PNG)

![alt texte](https://github.com/Nathan-Carre/projet_incendie/blob/main/ressources/Capture11.PNG)

### 6 - Le code

Le docstring de chaque fonctions, permettant de savoir ce qu'elles réalisent, est disponible avec l'outil : "help(nomDeMaFonction)" qui s'affichera dans le terminal. De plus, nous avons choisi d'utiliser la méthode "toplevel()" qui permet de diviser l'affichage en deux fenêtre distinctes, afin que l'utilisateur est une meilleur visibité et soit libre dans le placement des deux fenêtres Tkinter.

