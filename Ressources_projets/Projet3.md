# TSSR - Projet 3

## Projet infrastructure d'entreprise

## Introduction
Le but du projet 3 est de te faire mettre en pratique toutes les connaissances que tu as reçue et que tu vas recevoir pendant cette formation.
Tu vas te mettre dans la peau d'un-e technicien-ne Systèmes et Réseaux nouvellement recruté-e dans une société fictive, et qui intégre une nouvelle équipe SI.

## **1. Le contexte**

### a. La société

La société **Ekoloclast**, est une start-up assez récente. Son fondateur l'a crée il y a moins de 2 ans.
Sa création part d'un constat ecologique peu reluisant. Le fondateur d'Ekoloclast souhaite à travers cette société apporter une vision nouvelle sur l'ecologie par des actions, des produits, et des methodes innovantes pour aider l'environnement au travers des personnes.
Elle fait du B2B et du B2C en vente et en prestations de conseils.

### b. Le SI

Au bout de 2 ans d'existence, la société a fait une levée de fond pour se developper, et un budget a été prévu pour créer un vrai service SI.
Vous intégrez ce nouveau service SI, en tant que TSSR. Votre formateur jouera le rôle du DSI.

### c. Le projet

Les différentes phases du projet accompagneront les connaissances et les thématiques abordées au fur et à mesure.
Ce projet commence le **lundi 25 juillet 2022**, et se terminera le **7 avril 2023**.
Il sera découpé en 9 phases, chacune durant 1 mois.

## **2. L'informatique de la société à l'état actuel**

### a. Au niveau des utilisateurs

La société est actuellement composée de 85 personnes. L'ensemble du personnel touche au SI.

Voici les différents services concernés:
* Comptabilité
* Finance (5 personnes)
* Comptabilité (3 personnes)
* Direction générale (3 personnes)
* Direction commerciale (30 personnes dont 25 commerciaux nomades)
* Marketing (15 personnes)
* Communication (8 personnes)
* Stratégie (5 personnes)
* RH (10 personnes)
* Logistique (6 personnes)

A cela s'ajoute environ une dizaine de prestataire qui viennent dans les locaux et qui interviennent sur le SI.

### c. Etat du réseau
* Le réseaux est fourni par 1 box classique fournie par un FAI qui n'alimente en wifi qu'une partie des locaux (environ 30 %)
* Environ 50% des utilisateurs ont accès au réseau d'entreprise, les autres utilisent leur connexion personnelle.
* Il n'y a pas de domaine, tous les PC sont en workgroup
* Il n'y a pas de vlans
* Il n'y a pas de serveur, pas de redondance matériel ni réseau
* Les PC portable sont en wifi, mais le signal est très mauvais

### d. Etat du stockage
* Le stockage est actuellement partagé entre les PC des collaborateurs et du cloud privé.
* En cas de départ d'un collaborateur, il y a perte des données
* En cas de problème technique sur un suport matériel de type ordinateur ou sur un support amovible, il y a perte des données.
* Un drive est mis en place pour les données centralisées

### e. Etat des sauvegardes

* Il n'y a aucune sauvegarde de données

### f. Etat de la messagerie

* La messagerie est hebergé chez une SSII en IDF.
* Le taux de satisfaction envers ce prestataire est plutôt mauvais

### g. Etat de la téléphonie

* Environ 40% des utilisateurs ont de la téléphonie fixe.
* Tous les utilisateurs utilise leurs mobiles personnels.
* Le taux de satisfaction envers la téléphonie est plutôt bon

### h. Au niveau de la maintenance

* Il n'y a pas de système de ticketing dans l'ensemble de la société
* Les utilisateurs appellent un prestataire qui se doit de résoudre contractuellement le problème sous 48h.
* Les utilisateurs sont clairement mécontent de ce service

### i. Le serveur web d'entreprise

* Ce service est dévolu à un prestataire

### j. Mobilité

* Les utilisateurs en déplacement n'ont pas d'accès au SI
* Les utilisateurs en télétravail n'ont pas de VPN pour acceder à leurs données d'entreprise

### k. Gestion des licences

* Il n'y a pas de licences en volume
* Toutes les licences sont OEM

### l. Impression

* 2 copieurs sont en location

## **3. L'évolution souhaitée**

La société est en évolution croissante. Cela se voit au niveau du CA, comme au niveau du nombre d'employés.
De même, une évolution par rachat est possible et doit être prise en compte dans l'architecture informatique.

Vous trouverez ci-dessous un synthèse des évolutions fonctionnelles souhaitées :

|                      | Objectifs prioritaires              | Objectifs secondaires                         | Objectifs optionnels          |  
|----------------------|-----------------------------------|---------------------------------------------|-------------------------------|
| Connexion interne    | centralisée et sécurisée          |    Prestataires                             |         -                     |
| Connexion externe    | -                                 | Tout le monde (sauf prestataires) |   Prestataires  |
| Sauvegarde           |              -                    |   Sauvegarde mensuelle                    |   Sauvegarde hebdomadaire        |
| Serveurs             |    Redondance de serveurs         |  -   |     Redondance de salle serveurs |
| Réseaux              | Réseaux séparés (VLANS)                 |    Supervision                               |         -                     |
| Automatisation       |       -                           |          -                                  |     Automatisation de process |
| Stockage             | Serveurs de fichiers             | Dossiers individuels                           |   Profils itinérant         |
| Messagerie           | montage serveur                |                -                             |             -                 |
| Maintenance          | Solution de ticketing             |   Accès depuis l'exterieur                  |   -                           |
| Web                  |      nom de domaine             |             montage serveur WEB                               |   -          |
| Impression           | Centralisation               |             -                    |   -                           |
| Gestion des licences |  optimiser pour du logiciel libre  |                       -                      |  Passer en licence en volume  |
| Pare-feu             | VPN interne                   |    VPN prestataires                                        |        -                      |
| Téléphonie           | SVI                               |    VOIP                                      |        -                      |

## **4. Gestion du projet et rendu**

### a. Gestion du projet

* Fonctionnement en mode projet
  * Sprint sur 4 semaines
  * 1 scrum master par sprint

* Méthodologie
  * Analyse de la synthèse
  * Analyse des besoins
  * Choix (solution, matériels, conception)
  * Conception de la solution d'infrastructure
  * Installation de la solution d'infrastructure
  * Configuration
  * Tests
  * Création de la documentation finale cliente
  * Création de la documentation finale technique

* Planning
  * S9 :
    * Analyse de la synthèse
    * Analyse des besoins
    * Choix (solution, matériels, conception)
    * Début de la mise en place de l'infrastructure réseaux et systèmes

  * S10 :
    * Rendu d'infrastructure virtualisée comme vue en S9
 
### b. Le rendu
* Une virtualisation complète de l'infrastructure réseau
* Un schéma de cette infrastructure
* Le plan d'adressage complet
* La documentation associée