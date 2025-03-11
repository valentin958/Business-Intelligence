
# Projet Business Intelligence : Rapide étude de cas d'une base de données d'un magasin "Tout-@-Vendre"

## Contexte

Le client souhaite exploiter ses données de ventes pour identifier les points forts et faibles de ses magasins, en prenant en compte la saisonnalité et la diversité des tailles des magasins.


## Objectif

L'objectif de ce projet est d'analyser les ventes brutes, la marge et les caractéristiques des magasins pour identifier les points forts et faibles, en tenant compte des effets de saisonnalité, afin d'ajuster la stratégie commerciale et optimiser les performances des différents magasins.

## Les étapes


1. **Modélisation des données**
   - Identification des dimensions clés : expérience, région et poste du joueur.
   - Construction d'un modèle en flocon avec une granularité fine pour une analyse approfondie.
  
     ![modélisation flocon](images/modelisation_flocon.png)
  
   - Création du cube OLAP et analyse multidimensionelle
  
     ![modélisation OLAP](images/cube_olap.png)

3. **Traitement des données**
   - Traitement des données manquantes et ajout de données externes (budget des clubs de Ligue 1).
   - Enrichissement du dataset avec des informations supplémentaires pour mieux comprendre les contextes des joueurs.
  
     ![data](images/data.png)

3. **Visualisation des données**
   - Création d'un dashboard interactif avec des filtres permettant d'explorer les performances des joueurs en fonction de critères comme le prix, la vitesse, la défense, etc.
   - Intégration d'une carte interactive pour visualiser la répartition géographique des clubs.

   ![tableau1](images/bi1.PNG)
   ![tableau2](images/bi2.PNG)

## Résultat

L'outil facilite le processus de recrutement en offrant des fonctionnalités de filtrage et de tri sur des variables telles que le prix, la note générale, la vitesse, la défense, et bien d'autres. Il inclut également une carte interactive des clubs de Ligue 1, permettant une analyse géographique des données. 
Ce tableau de bord permet aux recruteurs d'identifier plus facilement les talents émergents et de prendre des décisions éclairées pour renforcer les équipes de football.
