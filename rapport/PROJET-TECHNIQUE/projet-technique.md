## Projet technique (Prototype)

Avant de commencer le développement du projet principal, j'ai réalisé un projet technique sous forme de prototype : une application web de **gestion et de consultation d'un catalogue de films**, permettant d'organiser les films, de gérer leurs réalisateurs et de les classer selon leurs genres cinématographiques.

La plateforme permet à l'administrateur d'ajouter des films, des réalisateurs et des genres. Les visiteurs peuvent consulter le catalogue depuis la page d'accueil et accéder aux principales informations de chaque film, notamment son titre, sa description, sa date de sortie, sa durée, son réalisateur et son genre.

## Fonctionnalités clés

- **Movie Management :** Gestion du catalogue de films et ajout de nouveaux films.
- **Director Management :** Gestion des réalisateurs et de leurs informations.
- **Film Genre Management :** Gestion des genres cinématographiques et classification des films.
- **Movie Catalog :** Affichage et consultation des films disponibles depuis la page d'accueil.
- **Movie Information :** Consultation des informations détaillées de chaque film, notamment son réalisateur et son genre.

## Classes principales du modèle

Le modèle de données repose sur trois entités principales :

- **Movie :** Représente un film avec son identifiant, son titre, sa description, sa date de sortie, sa durée, son réalisateur et son genre.
- **Director :** Représente un réalisateur avec son identifiant, son prénom, son nom et sa nationalité.
- **FilmGenre :** Représente un genre cinématographique avec son identifiant, son nom et sa description.

## Relations principales

- **Director ↔ Movie :** Relation One-to-Many (un réalisateur peut être associé à plusieurs films, tandis qu'un film est associé à un seul réalisateur).
- **FilmGenre ↔ Movie :** Relation One-to-Many (un genre peut regrouper plusieurs films, tandis qu'un film est associé à un seul genre).