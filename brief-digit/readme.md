# Meilleur Classifieur pour La reconnaissance des Digits audios

Ce programme à pour but de choisir le meilleur classifier pour la reconnaissance de digits audios afin de mettre en place un système de reconnaissance auditive en temps réel.

## Les données

Les données sont des ensembles de fréquences récupérer dans des fichiers audio. Ces fichiers ont été obtenu en nous enregistrant via la fonction `Tools.collection()`. Ces enregistrements contiennent une lecture des chiffres de 0 à 9.

## Le fonctionnement du programme

### le meilleur classifier
Pour choisir le meilleur classifier nous mettons en place différents modèles de prédictions sur les données que nous avons récolté, des modèle comme le KNN, le Random Forest ou encore XGBooster.
Afin de sélectionner le meilleur d'entre-eux nous les appliquons tour à tour sur des jeux d'entrainement et de test identiques en conservant leurs scores que nous comparons par la suite. 
Une fois le meilleur classifier mis en évidence nous le sauvegardons via la fonction `joblib`.

### Le test en temps réel

Grâce à la fonction `joblib` nous sauvegardons le meilleur modèle et grâce à la fonction `gridsearch` nous savons quels sont les meilleurs hyperparamètres à choisir. Cela nous permets d'appliquer le modèle de prédiction à l'enregistrement obtenu via la fonction `Tools.Rec()` et de faire la meilleure prédiction possible.