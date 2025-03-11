
# Projet Business Intelligence : Recrutement de joueurs de football

## Contexte

Le football est un domaine vaste et complexe qui englobe divers aspects, dont l'analyse de matchs, la gestion d'équipe et le recrutement des joueurs. Passionnés de football et curieux de combiner notre expertise en Business Intelligence avec notre passion, nous avons choisi de concentrer notre projet sur un aspect clé du football : le recrutement des joueurs. 

Le challenge consistait à développer un outil d'aide à la décision pour faciliter le recrutement de joueurs en utilisant des données extraites du jeu vidéo FIFA. 
Après une recherche approfondie, nous avons opté pour l'utilisation des données disponibles sur Kaggle, qui offrent une description détaillée des performances des joueurs.

## Objectif

L'objectif de ce projet est de créer un outil d'aide à la décision pour le recrutement de joueurs de football en analysant les performances des joueurs basées sur les données extraites du jeu vidéo FIFA. Ce projet vise à fournir une visualisation dynamique et interactive des joueurs de Ligue 1, permettant aux recruteurs de mieux évaluer les joueurs et de prendre des décisions éclairées pour renforcer les équipes.

## Les étapes


1. **Préparation des données (Data preprocessing)**
   Cette étape consiste à nettoyer et transformer les données de ventes fournies par le client. Elle inclut la gestion des valeurs manquantes, la normalisation des formats de données, l'identification et l'élimination des valeurs aberrantes (par exemple, les ventes anormalement élevées), ainsi que la création de nouvelles variables pour analyser la saisonnalité et la performance des magasins.
  
     ```python
     import pandas as pd

# Charger le fichier Excel
file_path = "DATA v2 (1).xlsx"
xls = pd.ExcelFile(file_path)

# Liste des feuilles à charger
sheet_names = xls.sheet_names

# Dictionnaire pour stocker les DataFrames nettoyées
df_cleaned = {}

# Charger et nettoyer les données de chaque feuille
for sheet in sheet_names:
    df = xls.parse(sheet)
    
    # Suppression des colonnes inutiles (exemple de la feuille 'sales')
    if 'Unnamed: 0' in df.columns:
        df = df.drop(columns=['Unnamed: 0'], errors='ignore')

    # Exemple pour détecter et supprimer des valeurs aberrantes pour la colonne 'Ventes bruts'
    if 'Ventes bruts' in df.columns:
        df = df[df['Ventes bruts'] <= 255]

    # Ajouter le DataFrame nettoyé au dictionnaire
    df_cleaned[sheet] = df
# Sauvegarder les DataFrames nettoyées dans un nouveau fichier Excel
output_file_path = "dataframe_clean.xlsx"
with pd.ExcelWriter(output_file_path) as writer:
    for sheet, df in df_cleaned.items():
        df.to_excel(writer, sheet_name=sheet, index=False)

print("Structure du DataFrame nettoyé :")
for sheet, df in df_cleaned.items():
    print(f"\nAnalyse de la feuille : {sheet}")
    print("Aperçu des premières lignes :")
    print(df.head())  # Affiche les 5 premières lignes du DataFrame
    print("\nInformation générale sur la structure :")
    print(df.info())  # Affiche les types de données, nombre de valeurs non-nulles, etc.
    print("\nValeurs manquantes par colonne :")
    print(df.isnull().sum())  # Affiche le nombre de valeurs manquantes par colonne
    print("-" * 50)
  


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
