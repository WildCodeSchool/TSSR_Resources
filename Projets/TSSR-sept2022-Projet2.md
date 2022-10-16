# TSSR septembre 2022 - PROJET 2

##  Création d'un architecture client-serveur

### 1. Objectifs

* Installer et préparer un ordinateur de type client et un ordinateur de type serveur
* Faire communiquer ces 2 machines sur un même réseau
* Mettre à disposition des services
* Mettre en place de la sécurité
* Créer un mode opératoire
* Faire une démonstration de la réalisation finale

### 2. Sujets

Le sujet est unique. Seul le choix des OS est possible:

* OS client : Windows 10 ou Ubuntu 22.04
* OS serveur : Windows server 2019/2022 ou Ubuntu server 22.04

> Les OS peuvent être mixé entre le serveur et le client

#### 2.1 Réseau

Les ordinateurs seront installés sur un réseau virtuel sous un hyperviseur de type 2 comme Virtualbox.
La machine cliente aura une configuration IP dynamique.
Le réseau sera en **/24**.

> Le choix de l'hyperviseur doit permettre à tous les membre d'un groupe de pouvoir travailler avec la même technologie.

#### 2.2 Fonctionnalités proposées

Un script devra être accessible et executable sur le serveur par un compte ayant des privilèges élevés.
Ce script, codé en Bash ou en PowerShell, affichera un menu de choix de fonctionnalités :

* **Actions vers le client** :
  * Verrouillage/Arrêt/Redémarrage machine
  * Création/Modification/Suppression de répertoire
  * Création/Suppression/Modification/Désactivation de compte
* **Teleassistance** :
  * Du serveur vers le client
  * Du client vers le serveur
* **Récupération d'informations** (qui seront stockées sur le serveur dans un fichier) :
  * Version OS client
  * Espace disque Total/Restant
  * Liste des lecteurs
  * Adresse IP/Masque/Passerelle/MAC
  * Liste des utilisateurs locaux
* **Sécurité** :
  * Les accès au poste client seront sécurisé
  * Les accès en téléassistance seront sécurisé

> Vous n'êtes pas obligé de garder cette structure de menu. Par contre, toutes les fonctionnalités évoquées doivent être présente.

### 3. Présentation orale

Toutes les semaines :

* Durée : 15 min
* Bilan des objectifs de la semaine
  * Bilan de groupe et individuel
* Avancement du projet
  * Explication des choix techniques
  * Démonstration de l'avancée du projet
* Objectifs de la semaine suivante au niveau groupe et individuel

### 4. Mode opératoire et sources à fournir

Le mode opératoire devra être fourni en **format markdown** et **pdf** à la fin du projet.
Une ebauche de ce MO devra être fourni toute les semaines.
L'ensemble de l'architecture doit être fournie sous format exportable (par exemple **ova**) à la fin du projet.

### 5. Groupes de projet

Vous serez réparti par groupe de la manière suivante :

|   Groupe 1 | Groupe 2   |  
| ----       | ----       |
| François   | Rayan      |
| Dilan      | Iliasse    |
| Maxime     | Nessim     |
| Joanie     | Fergane    |

Pour le groupe 1 :

|   Semaine   | Scrum master | Product owner |
| ----        | ----         | ----          |
| Semaine 1   | Dilan        | Maxime        |
| Semaine 2   | François     | Joanie        |
| Semaine 3   | Maxime       | François      |

Pour le groupe 2 :

|   Semaine   | Scrum master | Product owner |
| ----        | ----         | ----          |
| Semaine 1   | Rayan        | Fergane       |
| Semaine 2   | Fergane      | Iliasse       |
| Semaine 3   | Iliasse      | Nessim        |

### 6. Critères de validation de projet

1. Architecture et communication client-serveur fonctionnelle.
2. Toutes les fonctionnalités demandées sont présente et fonctionnelles
3. La sécurité est présente, que cela soit au niveau des accès (client ou serveur) ou bien dans la communication client-serveur.
4. Un mode opératoire ainsi que les sources associées sont mis à disposition.
