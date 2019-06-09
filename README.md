## Données d’entrée
Utiliser les différentes cartes VAC sous format PDF. Ces cartes sont disponibles dans le dossier VAC des sources de ce projet.

## Format de sortie du fichier csv
Tous les fichiers pdf d'entrée sont associés à un unique fichier de sortie au format csv. C'est à dire que ce fichier csv contient plusieurs lignes, chaque ligne représentant une carte VAC.

Ce fichier est présent dans le dossier de destination (dossier sélectionné dans la PrimaryPage) sous le nom "metaDonnees.csv".

Le format de chaque ligne est :

>"{code},{type},{échelle verticale},{échelle horizontale},{coordonnées 1},{coordonnées 2}" 

où :

* {code} est remplacé par le code OACI de l'aéroport.
* {type} est remplacé par le type de carte
* {échelle verticale} est remplacée par l'échelle verticale de la carte en degré par 1000 px
* {échelle horizontale} est remplacée par l'échelle horizontale de la carte en degré par 1000 px
* {coordonnées 1} du point en haut à gauche sous le format "longitude latitude" en degré (avec un espace entre les deux !)
* {coordonnées 2} du point en bas à droite sous le format "longitude latitude" en degré (avec un espace entre les deux !)

## Format de sortie de l'image
L'image est enregistrée dans le dossier de destination (dossier sélectionné dans la PrimaryPage) sous le nom "{code}{type}.png" où :

* {code} est remplacé par le code OACI de l'aéroport
* {type} est remplacé par le type de carte

## Dépendances
Besoin des bibliothèques :
* <a href ="https://openjdk.java.net/">OpenJDK11</a>
* <a href ="https://gluonhq.com/products/javafx/">JavaFX11 LTS</a>
* <a href ="https://pdfbox.apache.org/download.cgi">PDFBox 2.0.15</a>
* <a href ="https://sourceforge.net/projects/tess4j/files/tess4j/3.4.8/">Tess4J 3.4.8</a>

## Configuration d'eclipse

> Menu > Run > Run configurations...

Créer une nouvelle launch configuration avec les paramètres :

Main class :
>main.Main

VM arguments 
> --module-path /path/to/javafx-sdk-11.0.2/lib --add-modules javafx.controls,javafx.fxml,javafx.swing

Enlever l'option : 
> Use the -XstartOnFirstThread argument when launching with SWT

## Génération de la Javadoc
Pour générer la Javadoc, utiliser les outils d'eclipse :

> Menu > Project > Generate Javadoc...

## Ajouter les données du model de reconnaissance
Avant d'exécuter le jar, copier le dossier tessdata dans le même répertoire que le jar.
