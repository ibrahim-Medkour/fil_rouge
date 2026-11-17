---
layout: default
title: Rapport du projet de covoiturage
---

# Rapport de projet

## Conception d'une plateforme web de covoiturage

## Table des matières

-   [Remerciements](#remerciements)
-   [Introduction](#introduction)
-   [Contexte du projet](#contexte-du-projet)
-   [Cahier des charges](#cahier-des-charges)
-   [Méthodologie de travail](#méthodologie-de-travail)
    -   [Méthodologie Scrum](#méthodologie-scrum)
    -   [Processus 2TUP](#processus-2tup)
    -   [Design Thinking](#design-thinking)
-   [Planification](#planification)
-   [Branche fonctionnelle](#branche-fonctionnelle)
    -   [Carte d'empathie](#carte-dempathie)
    -   [Définition du problème](#définition-du-problème)
    -   [Idéation](#idéation)
    -   [Diagramme de cas d'utilisation](#diagramme-de-cas-dutilisation)
-   [Branche technique](#branche-technique)
    -   [Stack technologique](#stack-technologique)
    -   [Architecture logicielle](#architecture-logicielle)
    -   [Prototype : fonctionnalités et
        classes](#prototype--fonctionnalités-et-classes)
-   [Conception](#conception)
    -   [Diagramme de classes](#diagramme-de-classes)
    -   [Maquettes](#maquettes)
-   [Réalisation](#réalisation)
    -   [Interfaces](#interfaces)
-   [Conclusion](#conclusion)

------------------------------------------------------------------------

## Remerciements

Nous tenons à remercier toutes les personnes qui ont contribué,
directement ou indirectement, à la réflexion et à la préparation de ce
projet. Nous remercions également nos formateurs et les personnes qui
nous ont accompagnés durant notre parcours de formation, pour leurs
conseils, leurs orientations et leurs remarques.

Enfin, nous remercions toutes les personnes susceptibles de participer à
l'évaluation de cette plateforme et de partager leurs suggestions afin
d'améliorer sa conception.

## Introduction

Le covoiturage est une solution de mobilité qui consiste à partager un
véhicule et un trajet entre plusieurs personnes se déplaçant dans une
direction identique ou proche. Il permet de mettre en relation des
conducteurs disposant de places libres avec des passagers qui
recherchent un moyen de transport pour effectuer un déplacement.

Dans ce contexte, notre projet consiste à concevoir une **plateforme web
de covoiturage** destinée à faciliter la mise en relation entre
conducteurs et passagers. La plateforme doit permettre aux conducteurs
de proposer leurs trajets et aux passagers de rechercher les trajets qui
correspondent à leurs besoins, puis d'effectuer une demande de
réservation.

Ce rapport présente l'analyse du besoin, les fonctionnalités envisagées,
les acteurs du système, les choix de conception et l'organisation
technique prévue. Il suit une démarche structurée qui permet de passer
de la compréhension du problème à la conception d'une solution
informatique.

**Périmètre actuel :** le présent document décrit principalement la
phase d'analyse et de conception. Les technologies définitives, les
règles métier détaillées et les résultats de réalisation devront être
renseignés lorsque ces décisions et travaux auront été effectivement
réalisés.

## Contexte du projet

Les déplacements quotidiens ou occasionnels peuvent représenter une
difficulté pour les personnes qui ne disposent pas toujours d'un moyen
de transport adapté. Un passager peut rencontrer des difficultés pour
trouver un conducteur effectuant le même trajet. De son côté, un
conducteur peut effectuer un déplacement avec des places libres sans
disposer d'un moyen simple pour trouver des personnes souhaitant
partager ce trajet.

La mise en relation entre ces deux profils peut donc être compliquée
lorsqu'elle repose uniquement sur des échanges informels ou des
recherches dispersées.

Notre projet propose une plateforme web centralisée qui facilite cette
mise en relation. Le conducteur peut publier les informations de son
trajet, tandis que le passager peut consulter les propositions
disponibles et rechercher un trajet selon ses critères.

La plateforme prévoit trois acteurs principaux :

-   **Conducteur :** personne qui propose un trajet et met à disposition
    des places dans son véhicule.
-   **Passager :** personne qui recherche un trajet et souhaite réserver
    une ou plusieurs places.
-   **Administrateur :** responsable de la gestion et du suivi des
    utilisateurs, des trajets et des réservations.

Un même utilisateur peut éventuellement utiliser la plateforme comme
conducteur pour certains déplacements et comme passager pour d'autres.
Les modalités exactes de gestion de ces profils devront être précisées
lors de la conception détaillée.

## Cahier des charges

### Présentation du besoin

Le besoin principal est de développer une plateforme web qui centralise
les offres de covoiturage et facilite les échanges entre les personnes
qui proposent un trajet et celles qui en recherchent un.

La solution doit proposer une interface permettant de publier,
consulter, rechercher et réserver des trajets. Elle doit également
fournir à l'administrateur les moyens nécessaires pour superviser les
principales données de la plateforme.

### Objectifs du projet

Les objectifs principaux sont les suivants :

-   Faciliter la rencontre entre conducteurs et passagers.
-   Permettre aux conducteurs de publier leurs propositions de trajets.
-   Permettre aux passagers de rechercher des trajets selon leurs
    besoins.
-   Simplifier la consultation des détails d'un trajet.
-   Permettre aux passagers d'effectuer des demandes de réservation.
-   Donner aux conducteurs un moyen de consulter les réservations liées
    à leurs trajets.
-   Donner à l'administrateur une vision globale des utilisateurs, des
    trajets et des réservations.
-   Centraliser les informations relatives aux trajets et aux
    réservations.

### Besoins fonctionnels

  -----------------------------------------------------------------------
  Acteur                              Besoins fonctionnels
  ----------------------------------- -----------------------------------
  Conducteur                          Publier un trajet, consulter ses
                                      trajets, modifier ou supprimer un
                                      trajet, consulter les demandes de
                                      réservation reçues.

  Passager                            Rechercher un trajet, consulter les
                                      détails, effectuer une réservation
                                      et consulter ses réservations.

  Administrateur                      Consulter et gérer les
                                      utilisateurs, les trajets et les
                                      réservations.
  -----------------------------------------------------------------------

Les opérations de confirmation ou de refus d'une réservation par le
conducteur constituent une règle de fonctionnement à valider avant leur
intégration définitive.

### Besoins non fonctionnels

La plateforme devra prendre en considération les qualités suivantes :

-   **Ergonomie :** proposer une interface claire et facile à utiliser.
-   **Accessibilité :** permettre aux utilisateurs d'accéder aux
    principales fonctionnalités depuis une interface web.
-   **Sécurité :** protéger les comptes et limiter l'accès aux
    opérations selon le rôle de l'utilisateur.
-   **Fiabilité :** assurer la cohérence des informations relatives aux
    trajets et aux réservations.
-   **Maintenabilité :** organiser le code de manière claire afin de
    faciliter les corrections et les évolutions.
-   **Performance :** permettre la consultation et la recherche des
    trajets dans des délais raisonnables.

### Contraintes et limites

Les choix définitifs concernant les technologies, le système de
stockage, l'hébergement, les moyens de paiement et les éventuels
services externes ne sont pas encore établis dans les informations
disponibles. Ils ne sont donc pas présentés comme des décisions déjà
prises.

## Méthodologie de travail

### Méthodologie Scrum

#### Présentation de Scrum

Scrum est un cadre de travail agile qui permet d'organiser le
développement d'un projet en plusieurs cycles courts appelés
**sprints**. Chaque sprint vise à produire un résultat concret et à
faire progresser le projet de manière régulière.

Dans le cadre de notre plateforme de covoiturage, Scrum peut être
utilisé pour organiser les tâches, suivre l'avancement et adapter les
priorités en fonction des besoins identifiés.

#### Principes de Scrum

-   **Transparence :** les tâches, les objectifs et l'état d'avancement
    doivent être visibles.
-   **Inspection :** le travail réalisé est examiné régulièrement afin
    d'identifier les problèmes.
-   **Adaptation :** les priorités et l'organisation peuvent être
    ajustées selon les résultats et les retours.

#### Organisation prévisionnelle en sprints

La répartition suivante constitue une proposition de planification. Elle
devra être adaptée à la durée réelle du projet.

**Sprint 1 --- Analyse et conception**

-   Identifier les acteurs de la plateforme.
-   Définir les besoins fonctionnels et non fonctionnels.
-   Décrire les principaux cas d'utilisation.
-   Élaborer le diagramme de classes prévisionnel.
-   Préparer les premières maquettes.

**Sprint 2 --- Gestion des utilisateurs**

-   Concevoir les écrans d'inscription et de connexion.
-   Définir la gestion des profils conducteur et passager.
-   Prévoir les contrôles d'accès selon les rôles.

**Sprint 3 --- Gestion des trajets**

-   Prévoir la publication d'un trajet.
-   Prévoir la consultation, la modification et la suppression des
    trajets.
-   Prévoir la recherche et le filtrage des trajets.

**Sprint 4 --- Gestion des réservations et administration**

-   Prévoir la demande de réservation.
-   Définir le suivi des réservations.
-   Prévoir les fonctions d'administration.
-   Préparer les tests fonctionnels et les corrections.

Les sprints ci-dessus représentent une organisation proposée et non des
travaux déjà réalisés.

### Processus 2TUP

#### Définition

La méthode **2TUP (Two Tracks Unified Process)** est une démarche de
développement logiciel qui sépare l'analyse en deux branches
complémentaires :

-   **La branche fonctionnelle :** elle permet de comprendre les
    utilisateurs, leurs besoins et les fonctionnalités attendues.
-   **La branche technique :** elle permet d'étudier les contraintes
    techniques, les choix technologiques et l'architecture du système.

Ces deux branches avancent en parallèle et se rejoignent lors de la
phase de conception et de réalisation.

#### Application au projet de covoiturage

Dans notre projet, la branche fonctionnelle porte notamment sur :

-   La gestion des utilisateurs et de leurs profils.
-   La publication et la gestion des trajets.
-   La recherche et la consultation des trajets.
-   La réservation des places.
-   La gestion administrative de la plateforme.

La branche technique devra déterminer les technologies adaptées,
l'organisation du frontend et du backend, le système de stockage et les
mécanismes de sécurité.

La convergence des deux branches permettra de construire une solution
cohérente avec les besoins des conducteurs, des passagers et de
l'administrateur.

#### Conclusion

La méthode 2TUP permet de séparer clairement la compréhension du métier
de l'étude technique. Cette séparation facilite l'analyse du projet et
aide à vérifier que l'architecture envisagée répond aux besoins réels de
la plateforme de covoiturage.

### Design Thinking

#### Présentation

Le Design Thinking est une approche de résolution de problèmes centrée
sur l'utilisateur. Elle consiste à comprendre les difficultés
rencontrées par les utilisateurs, à définir précisément le problème, à
proposer plusieurs idées, puis à concevoir et tester des solutions.

Cette approche est pertinente pour notre plateforme, car les conducteurs
et les passagers n'ont pas exactement les mêmes attentes.

#### Les étapes du Design Thinking

1.  **Empathie :** comprendre les difficultés et les attentes des
    conducteurs et des passagers.
2.  **Définition :** formuler clairement le problème auquel la
    plateforme doit répondre.
3.  **Idéation :** proposer plusieurs fonctionnalités et solutions
    possibles.
4.  **Prototype :** préparer des maquettes simplifiées des principales
    interfaces.
5.  **Test :** faire évaluer les maquettes par des utilisateurs et
    améliorer l'expérience selon leurs retours.

Ces étapes permettent de garder les besoins des utilisateurs au centre
des décisions de conception.

## Planification

La planification prévisionnelle peut être organisée selon les phases
suivantes :

  -----------------------------------------------------------------------
  Phase                   Activités principales   Résultat attendu
  ----------------------- ----------------------- -----------------------
  1\. Analyse             Étude du contexte,      Cahier des charges
                          identification des      
                          acteurs et des besoins  

  2\. Analyse             Carte d'empathie,       Modélisation
  fonctionnelle           définition du problème, fonctionnelle
                          cas d'utilisation       

  3\. Conception          Diagramme de classes,   Dossier de conception
                          architecture et         
                          maquettes               

  4\. Préparation         Choix du stack et       Environnement technique
  technique               organisation du projet  défini

  5\. Développement       Implémentation          Application développée
                          progressive des         
                          fonctionnalités         

  6\. Tests               Vérification des        Version testée
                          fonctionnalités et      
                          correction des          
                          anomalies               

  7\. Finalisation        Préparation de la       Livrable final
                          documentation et        
                          présentation            
  -----------------------------------------------------------------------

**Remarque :** les dates, les durées et les responsables de chaque phase
restent à compléter selon le calendrier réel du projet.

## Branche fonctionnelle

La branche fonctionnelle consiste à analyser le fonctionnement attendu
de la plateforme du point de vue des utilisateurs. Elle permet
d'identifier les acteurs, leurs objectifs, leurs interactions et les
règles métier nécessaires.

### Carte d'empathie

La carte d'empathie permet de mieux comprendre les attentes et les
difficultés des utilisateurs.

#### Profil 1 : Conducteur

-   **Ce qu'il pense et ressent :** il souhaite organiser ses
    déplacements et trouver des passagers intéressés par son trajet.
-   **Ce qu'il voit :** des personnes qui effectuent parfois le même
    trajet, mais qu'il ne connaît pas nécessairement.
-   **Ce qu'il entend :** des demandes de transport et des discussions
    autour du coût et de l'organisation des déplacements.
-   **Ce qu'il dit et fait :** il cherche un moyen de publier son trajet
    et de présenter les informations nécessaires.
-   **Ses difficultés :** trouver des passagers, communiquer les détails
    du trajet et suivre les demandes de réservation.
-   **Ses besoins :** publier un trajet facilement, consulter les
    demandes et gérer ses propositions.

#### Profil 2 : Passager

-   **Ce qu'il pense et ressent :** il souhaite trouver un trajet
    correspondant à sa destination et à son horaire.
-   **Ce qu'il voit :** différentes possibilités de déplacement, sans
    toujours savoir où trouver une offre de covoiturage adaptée.
-   **Ce qu'il entend :** des propositions de trajets et des
    recommandations de personnes de son entourage.
-   **Ce qu'il dit et fait :** il recherche un trajet et compare les
    informations disponibles.
-   **Ses difficultés :** trouver un conducteur effectuant un trajet
    compatible et connaître les places disponibles.
-   **Ses besoins :** rechercher des trajets, consulter leurs détails et
    effectuer une réservation.

#### Profil 3 : Administrateur

-   **Ce qu'il pense et ressent :** il doit assurer le suivi général de
    la plateforme.
-   **Ce qu'il voit :** les utilisateurs, les trajets publiés et les
    réservations enregistrées.
-   **Ce qu'il entend :** les éventuels retours et signalements transmis
    par les utilisateurs.
-   **Ce qu'il dit et fait :** il consulte et gère les informations
    nécessaires à l'administration.
-   **Ses difficultés :** suivre les données et maintenir une
    organisation cohérente.
-   **Ses besoins :** disposer d'un espace d'administration pour gérer
    les utilisateurs, les trajets et les réservations.

Cette carte est une première analyse des profils cibles. Elle pourra
être enrichie par des entretiens ou des questionnaires auprès de
véritables utilisateurs.

### Définition du problème

L'analyse du contexte fait apparaître une difficulté principale : les
conducteurs qui disposent de places libres et les passagers qui
recherchent un transport partagé ne disposent pas toujours d'un espace
centralisé pour se retrouver et organiser leurs déplacements.

Cette situation peut rendre la recherche d'un trajet, la publication
d'une offre et le suivi des réservations moins simples.

**Problématique :**

Comment concevoir une plateforme web simple et accessible permettant de
mettre en relation les conducteurs et les passagers, de faciliter la
publication et la recherche de trajets, et d'organiser les demandes de
réservation au sein d'un même système ?

### Idéation

À partir de la problématique identifiée, plusieurs idées de
fonctionnalités peuvent être proposées.

**Pour le conducteur :**

-   Créer et gérer son profil.
-   Publier un trajet avec une ville de départ, une destination, une
    date, une heure et le nombre de places proposées.
-   Indiquer les informations complémentaires du trajet, comme le prix
    proposé, si cette fonctionnalité est retenue.
-   Consulter la liste de ses trajets.
-   Consulter les demandes de réservation associées à ses trajets.

**Pour le passager :**

-   Créer et gérer son profil.
-   Rechercher un trajet selon la ville de départ et la destination.
-   Filtrer les résultats selon la date et d'autres critères retenus.
-   Consulter les détails d'un trajet.
-   Effectuer une demande de réservation.
-   Consulter ses réservations.

**Pour l'administrateur :**

-   Consulter les utilisateurs.
-   Gérer les comptes utilisateurs.
-   Consulter et gérer les trajets.
-   Consulter et gérer les réservations.

**Idées à valider avant développement :** paiement en ligne, système
d'avis et de notation, messagerie, notifications, vérification
d'identité et géolocalisation. Ces fonctionnalités ne sont pas
considérées comme incluses dans le périmètre confirmé à ce stade.

### Diagramme de cas d'utilisation

Le diagramme de cas d'utilisation présente les interactions entre les
acteurs et les fonctionnalités principales de la plateforme.

#### Acteurs

-   **Conducteur :** publie et gère ses trajets, puis consulte les
    demandes associées.
-   **Passager :** recherche les trajets et effectue des réservations.
-   **Administrateur :** supervise les utilisateurs, les trajets et les
    réservations.

#### Diagramme

``` mermaid
flowchart LR
    C[Conducteur]
    P[Passager]
    A[Administrateur]

    subgraph S["Plateforme de covoiturage"]
        UC1([S'inscrire])
        UC2([Se connecter])
        UC3([Gérer son profil])

        UC4([Publier un trajet])
        UC5([Consulter ses trajets])
        UC6([Modifier un trajet])
        UC7([Supprimer un trajet])
        UC8([Consulter les demandes de réservation])

        UC9([Rechercher un trajet])
        UC10([Consulter les détails d'un trajet])
        UC11([Demander une réservation])
        UC12([Consulter ses réservations])

        UC13([Gérer les utilisateurs])
        UC14([Gérer les trajets])
        UC15([Gérer les réservations])
    end

    C --- UC1
    P --- UC1
    C --- UC2
    P --- UC2
    C --- UC3
    P --- UC3

    C --- UC4
    C --- UC5
    C --- UC6
    C --- UC7
    C --- UC8

    P --- UC9
    P --- UC10
    P --- UC11
    P --- UC12

    A --- UC2
    A --- UC13
    A --- UC14
    A --- UC15
```

*Figure : Diagramme général des cas d'utilisation de la plateforme de
covoiturage.*

Ce diagramme représente le périmètre fonctionnel prévisionnel. Les
règles détaillées relatives à la confirmation, au refus et à
l'annulation des réservations devront être précisées dans les
spécifications détaillées.

## Branche technique

La branche technique consiste à étudier les éléments nécessaires à la
réalisation de la plateforme : technologies, architecture, organisation
des composants, stockage des données et contraintes techniques.

Les choix présentés dans cette partie doivent être confirmés avant le
démarrage du développement.

### Stack technologique

Le stack technologique définit les langages, frameworks, outils et
systèmes qui seront utilisés pour développer l'application.

À ce stade, les informations disponibles ne permettent pas de confirmer
le stack définitif du projet de covoiturage.

Les éléments suivants sont donc à renseigner après validation :

  -----------------------------------------------------------------------
  Domaine                 Technologie retenue     Rôle
  ----------------------- ----------------------- -----------------------
  Frontend                À confirmer             Construction des
                                                  interfaces utilisateur

  Backend                 À confirmer             Traitement des requêtes
                                                  et logique métier

  Base de données /       À confirmer             Conservation des
  stockage                                        utilisateurs, trajets
                                                  et réservations

  Outils de conception    À confirmer             Création des diagrammes
                                                  et maquettes

  Environnement de        À confirmer             Développement et tests
  développement                                   de l'application
  -----------------------------------------------------------------------

Le choix définitif devra prendre en compte la complexité du projet, les
compétences disponibles, la sécurité, la maintenabilité et les besoins
fonctionnels.

### Architecture logicielle

#### Architecture générale

La plateforme peut être organisée en trois grandes parties logiques :

-   **Couche de présentation :** elle contient les interfaces utilisées
    par les conducteurs, les passagers et l'administrateur.
-   **Couche métier :** elle traite les opérations et applique les
    règles de gestion, par exemple la publication d'un trajet ou la
    demande de réservation.
-   **Couche d'accès aux données :** elle assure la lecture et la
    modification des informations enregistrées.

Cette séparation permet de distinguer l'affichage, le traitement métier
et la persistance des données.

#### Schéma logique en trois couches

``` mermaid
flowchart TB
    U[Conducteur / Passager / Administrateur]
    P[Présentation : interfaces web]
    M[Logique métier : utilisateurs, trajets, réservations]
    D[Accès aux données]
    DB[(Stockage des données)]

    U --> P
    P --> M
    M --> D
    D --> DB
    DB --> D
    D --> M
    M --> P
    P --> U
```

*Figure : Organisation logique en trois couches de la plateforme.*

#### Architecture fonctionnelle globale

``` mermaid
flowchart LR
    U[Utilisateurs]
    UI[Interface web]
    AUTH[Gestion des comptes et profils]
    TR[Gestion des trajets]
    RE[Gestion des réservations]
    ADMIN[Administration]
    DATA[(Données de la plateforme)]

    U --> UI
    UI --> AUTH
    UI --> TR
    UI --> RE
    UI --> ADMIN

    AUTH <--> DATA
    TR <--> DATA
    RE <--> DATA
    ADMIN <--> DATA
```

*Figure : Vue fonctionnelle des principaux composants de la plateforme.*

Cette architecture représente une organisation conceptuelle. Elle ne
constitue pas encore une architecture technique détaillée ni une preuve
d'implémentation.

### Prototype : fonctionnalités et classes

Le prototype fonctionnel envisagé doit permettre de vérifier les
principales interactions de la plateforme.

#### Fonctionnalités principales

**1. Gestion des utilisateurs**

-   Inscription.
-   Connexion.
-   Consultation et modification du profil.
-   Identification du rôle et contrôle des accès.

**2. Gestion des trajets**

-   Création d'un trajet.
-   Consultation des trajets publiés.
-   Modification d'un trajet.
-   Suppression d'un trajet.
-   Gestion des informations du trajet.

Les informations envisagées pour un trajet sont notamment :

-   Identifiant du trajet.
-   Conducteur associé.
-   Ville de départ.
-   Ville d'arrivée.
-   Date du trajet.
-   Heure de départ.
-   Nombre de places proposées.
-   Prix éventuel.

**3. Recherche des trajets**

-   Recherche par ville de départ.
-   Recherche par destination.
-   Recherche par date.
-   Consultation des résultats.
-   Consultation des détails d'un trajet.

**4. Gestion des réservations**

-   Demande de réservation par un passager.
-   Association de la réservation à un trajet et à un passager.
-   Consultation des réservations.
-   Suivi de l'état d'une réservation.

Les statuts et les règles exactes de confirmation ou d'annulation
devront être définis dans les règles métier.

**5. Administration**

-   Gestion des utilisateurs.
-   Gestion des trajets.
-   Gestion des réservations.

#### Entités principales envisagées

-   **Utilisateur :** représente une personne inscrite sur la
    plateforme.
-   **Trajet :** représente un déplacement proposé par un conducteur.
-   **Réservation :** représente une demande de place effectuée par un
    passager.

Les attributs et associations détaillés sont présentés dans le diagramme
de classes de la partie conception.

## Conception

La conception permet de représenter la structure du système avant son
développement. Elle décrit les entités principales, leurs relations et
les interfaces prévues.

### Diagramme de classes

Le diagramme de classes représente les principales classes métier de la
plateforme ainsi que les associations entre elles.

#### Classes principales

**Utilisateur**

Représente une personne qui utilise la plateforme.

Attributs envisagés :

-   id
-   nom
-   prénom
-   email
-   motDePasse
-   téléphone
-   rôle

**Trajet**

Représente un déplacement proposé par un conducteur.

Attributs envisagés :

-   id
-   villeDépart
-   villeArrivée
-   dateDépart
-   heureDépart
-   nombrePlaces
-   prix (si retenu)
-   statut

**Réservation**

Représente la demande d'un passager pour obtenir une ou plusieurs places
sur un trajet.

Attributs envisagés :

-   id
-   dateRéservation
-   nombrePlacesDemandées
-   statut

#### Associations

-   Un utilisateur ayant le rôle conducteur peut publier plusieurs
    trajets.
-   Chaque trajet est associé à un conducteur.
-   Un passager peut effectuer plusieurs réservations.
-   Chaque réservation concerne un seul trajet.
-   Un trajet peut recevoir plusieurs réservations.

La classe Réservation permet ainsi de représenter l'association entre
les passagers et les trajets.

#### Diagramme UML

``` mermaid
classDiagram
    class Utilisateur {
        +int id
        +string nom
        +string prenom
        +string email
        +string motDePasse
        +string telephone
        +string role
    }

    class Trajet {
        +int id
        +string villeDepart
        +string villeArrivee
        +date dateDepart
        +time heureDepart
        +int nombrePlaces
        +decimal prix
        +string statut
    }

    class Reservation {
        +int id
        +date dateReservation
        +int nombrePlacesDemandees
        +string statut
    }

    Utilisateur "1" --> "0..*" Trajet : publie
    Utilisateur "1" --> "0..*" Reservation : effectue
    Trajet "1" --> "0..*" Reservation : concerne
```

*Figure : Diagramme de classes conceptuel de la plateforme de
covoiturage.*

**Remarque de conception :** le prix et les statuts sont des éléments
proposés à confirmer. La gestion du véhicule peut également être ajoutée
sous forme d'une classe distincte si le cahier des charges prévoit
l'enregistrement de plusieurs véhicules par conducteur.

### Maquettes

Les maquettes permettent de représenter l'apparence et l'organisation
des interfaces avant leur développement.

Les principales interfaces à concevoir sont :

1.  **Page d'accueil :** présentation du service et accès à la recherche
    de trajets.
2.  **Inscription et connexion :** création d'un compte et accès à la
    plateforme.
3.  **Espace conducteur :** publication et gestion des trajets.
4.  **Formulaire de publication :** saisie du départ, de la destination,
    de la date, de l'heure et des places disponibles.
5.  **Recherche de trajets :** saisie des critères de recherche et
    affichage des résultats.
6.  **Détails d'un trajet :** présentation des informations du trajet et
    accès à la réservation.
7.  **Espace passager :** consultation et suivi des réservations.
8.  **Espace administrateur :** gestion des utilisateurs, des trajets et
    des réservations.

Les captures et les maquettes réelles devront être ajoutées dans cette
section lorsqu'elles seront disponibles.

## Réalisation

Cette partie sera consacrée à la présentation de l'application
effectivement développée. Elle devra décrire les fonctionnalités
implémentées, les choix techniques appliqués, les difficultés
rencontrées et les solutions apportées.

**État du projet dans les informations disponibles :** la réalisation
n'est pas encore documentée. Il ne faut donc pas présenter les
fonctionnalités comme déjà développées ou testées.

### Interfaces

Les captures d'écran suivantes pourront être ajoutées après le
développement :

-   Interface d'accueil.
-   Interface d'inscription et de connexion.
-   Tableau de bord du conducteur.
-   Formulaire d'ajout d'un trajet.
-   Liste des trajets disponibles.
-   Détails d'un trajet.
-   Interface de réservation.
-   Espace de suivi des réservations.
-   Tableau de bord administrateur.

Pour chaque capture, il conviendra d'ajouter un titre et une courte
explication de l'action que l'utilisateur peut effectuer.

## Conclusion

Ce projet consiste à concevoir une plateforme web de covoiturage dont
l'objectif principal est de faciliter la mise en relation entre les
conducteurs qui proposent des trajets et les passagers qui recherchent
un moyen de transport partagé.

L'analyse fonctionnelle a permis d'identifier trois acteurs principaux :
le conducteur, le passager et l'administrateur. Elle a également permis
de définir les grandes fonctionnalités attendues, notamment la gestion
des utilisateurs, la publication des trajets, la recherche et la
réservation.

La démarche 2TUP permet de distinguer l'analyse fonctionnelle de l'étude
technique, tandis que Scrum propose une organisation progressive du
travail. Le Design Thinking complète ces approches en plaçant les
besoins des utilisateurs au centre de la conception.

Le diagramme de cas d'utilisation et le diagramme de classes constituent
les premières représentations du système. Ils serviront de base à la
conception détaillée, au choix des technologies et à la réalisation de
la plateforme.

Les prochaines étapes consisteront à valider les règles métier, arrêter
le stack technologique, finaliser les maquettes, développer les
fonctionnalités et effectuer les tests nécessaires afin d'obtenir une
solution cohérente avec les besoins identifiés.
