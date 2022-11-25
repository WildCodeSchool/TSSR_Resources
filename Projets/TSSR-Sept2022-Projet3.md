# TSSR - Projet 3 - Administration d'une infrastructure réseau

## **1. Introduction**

Le but du projet 3 est de mettre en pratique, dans un contexte professionnel, toutes les connaissances et méthodes étudiées pendant la formation.

Ce projet commence en semaine 9 et se terminera en semaine 19.
Il est découpé en sprint de 4 semaines (1 semaine de cours et 3 semaines d'alternance en entreprise). Il y aura donc **11 sprints**.

***Contexte :***

Tu es un·e technicien·ne Systèmes et Réseaux nouvellement recruté·e et qui intégre la nouvelle équipe SI d'une société dont ton formateur est le Directeur du Système d'Information (DSI).

## **2. Le contexte professionnel**

|   | Sujet 1 - Ekoloclast | Sujet 2 - BillU |
| ---   |  --- | --   |
|   La société  |  La société **Ekoloclast**, est une start-up récente. Son fondateur l'a crée il y a moins de 2 ans. Sa création part d'un constat ecologique peu reluisant. A travers cette société, il souhaite apporter une vision nouvelle sur l'ecologie par des actions, des produits, et des methodes innovantes pour aider l'environnement au travers des personnes. Elle fait du B2B et du B2C en vente et en prestations de conseils. Une levée de fond vient d'être éffectué pour pouvoir se développer.  |  La société **BillU** vient d'être acquise par le groupe RemindMe. Ce dernier, propose des services aux entreprises, et emploi plus de 2000 personnes dans le monde, répartit dans une dizaine de pays. BillU est spécialisée dans le développement de logiciels de facturation avec des clients B2B. Son expertise et ses compétences pouront être mis en place dans des services proposés par RemindMe. La société mère a prévu un budget pour développer le potentiel de cette nouvelle entreprise du groupe. |
| Type de société | Start-up | Filliale d'entreprise internationnale |
| Localisation géographique | 1 site en région Parisienne | 2 sites en région Parisienne |
| Le SI | Un budget a été prévu pour créer un vrai service SI. | Un budget a été prévu pour créer un vrai service SI.|
| Les utilisateurs internes | La société est actuellement composée de 91 personnes. L'ensemble du personnel touche au SI. | L'entreprise BillU emploie 55 personnes. L'ensemble du personnel touche au SI. |
| Les utilisateurs externes | Environ 10 prestataires de services | Moins de 5 prestataires de services |
| Nomadisme | Entre 30 et 50%. | Aucun utilisateur nomade.|
| Téletravail | Pas d'accès au SI | Pas d'accès au SI |
| Matériel utilisateur | 100 % de PC portables de marques et références très héterogènes. | 80% de PC fixes et le reste en PC portables. L'ensemble du matériel est en leasing. Marques et références homogènes. |
| Matériel d'administration | Aucun serveur ni matériel réseau | Il y a un serveur de stockage de fichiers (Paris 7), 2 routeurs wifi (un sur chaque site). Pas d'autre matériel réseau |
| Le réseau | Box internet classique fournie par un FAI. 50% de couverture wifi des locaux. Les utilisateurs hors-couverture se servent de leur télephone portable personnel comme hot-spot wifi. | Chaque site possède un réseau fibré. 80% Connexion filaire pour les matériels, le reste avec un routeur wifi. |
| Sécurité réseau | Aucun matériel, aucune redondance | Aucun matériel, aucune redondance |
| Sécurité système | Tous les PC sont en workgroup. Connexion sans mot de passe. | Tous les PC sont en workgroup. Connexion avec mot de passe faible. Pas de gestion d'ACL sur le serveur de fichiers |
| Messagerie | La messagerie est hebergée chez un prestataire (insatisfaction utilisateurs). | La messagerie est hebergée en web |
| Stockage des données | Stockage local sur les machines, et sur des drives internet. | Stockage local sur les machines et sur un serveur de fichiers.|
| Statut des données utilisateur en cas de départ | Pas de gestion | Pas de gestion |
| Statut des données utilisateurs en cas de défaillance | Perte des données | Si en local : perte des données, si sur le serveur de fichiers : pas de gestion (contractuel) |
| Sauvegarde | Il n'y a aucune sauvegarde de données | Le serveur de fichiers a 2 disque dur en mirroir.|
| Téléphonie | Environ 40% des utilisateurs ont de la téléphonie fixe (taux de satisfaction bon). Tous les utilisateurs utilise leurs mobiles personnels. | 100% des utilisateurs ont de la téléphonie fixe. Tous les utilisateurs utilise leurs mobiles personnels. Les utilisateurs souhaitent avoir plus de mobilité avec des téléphones portables professionnels. |
| Maintenance | En cas de problèmes, les utilisateurs appellent un prestataire qui résoud le problème en moins de 48h (contractuel) | Il n'y a pas de gestion de maintenance pour les matériels utilisateurs. Seul le serveur de fichiers a une maintenance sous 48h auprès d'un prestataire. |
| Site web | Ce service est dévolu à un prestataire | Il n'y a pas de site web.|
| Edition | 2 copieurs sont en location | Des imprimantes individuelles équipent environ 50% des postes de travail|

## **3. Les évolutions souhaitées**

Pour les 2 sociétes, voici les besoins exprimés par les dirigeants :

* Mettre en place du téletravail
* Avoir une gestion centralisée et sécurisée des données de l'entreprise
* Que les utilisateurs aient une connexion sécurisée en interne et depuis l'exterieur (durcissement mot de passe, VPN, ...)
* Avoir une gestion complète sur les données utilisateurs (en cas de départ, en cas de problèmes, ...)
* Avoir une gestion de parc informatique (inventaire, tickets d'incidents, ...)
* Avoir une sécurisation globale du système informatique (redondance, supervision, prevention des attaques, ...)

## **4. Objectifs du projet**

***Principal :*** Avoir une équipe qui est en mesure, parce qu'elle s'y est préparée, de monter une infrastructure testée le plus rapidement possible.

* Avoir des procedures documentées et testées
* Avoir des scripts pour automatiser un déploiement et une configuration.

***Secondaire :*** Mettre en place une infrastructure réseaux virtualisée.

## **5. Gestion du projet et rendu**

***Gestion du projet :***

* Fonctionnement en mode projet
  * Sprint sur 4 semaines
  * 1 scrum master et 1 product owner différent par sprint

* Méthodologie
  * Analyse du contexte professionnel
  * Analyse des évolutions souhaitées
  * Choix (solution, matériels, conception)
  * Conception, installation, et configuration de la solution d'infrastructure
  * Création de la documentation
  * Création des scripts d'automatisation

***Le rendu :***

* Des procedures documentées et testées
* Des scripts d'automatisation
* Des schéma d'infrastructure
* Un plan d'adressage complet
* Une virtualisation complète de l'infrastructure réseau

## **6. Annexes**

### **Sujet 1 : Société Ekoloclast**

***Les utilisateurs :***

La société est actuellement composée de 91 personnes :

* Direction générale (3 personnes)
* Finance (7 personnes)
* Comptabilité (5 personnes)
* Direction commerciale (30 personnes dont 25 commerciaux nomades)
* Marketing (15 personnes)
* Communication (8 personnes)
* Stratégie (5 personnes)
* RH (10 personnes)
* Logistique (8 personnes)

***Réseaux :***

La box internet fourni un réseau wifi en `192.168.1.0/24`

### **Sujet 2 : Société BillU**

***Les utilisateurs :***

La société est actuellement composée de 55 personnes :

Site 1 - Paris 7 : 42 personnes

* Direction générale (2 personne)
* Finance (3 personnes)
* Comptabilité (3 personnes)
* Direction commerciale (5 personnes)
* Marketing (3 personnes)
* Internationnal (2 personnes)
* Developpement logiciel (12 personnes)
* Communication (6 personnes)
* Juridique (2 personnes)
* RH (2 personne)
* Logistique (1 personne)

Site 2 - Massy : 14 personnes

* Comptabilité (1 personne)
* Developpement logiciel (9 personnes)
* Logistique (1 personne)
* RH (3 personnes)

***Réseaux :***

La connection fibre fournit le réseau suivant :

* Site 1 - Paris 7 :
  * Filaire : `172.16.1.0/24`
  * Wifi : `172.16.2.0/24`
* Site 2 - Massy :
  * Filaire : `10.10.5.0/24`
  * Wifi : `10.10.6.0/24`

Le serveur de fichiers est sur le site de Paris 7 :

* **SRV1** : `172.16.1.5`
