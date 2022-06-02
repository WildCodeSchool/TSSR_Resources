# Atelier Analyse de trame ethernet

## Pré-requis

* Un ordinateur ou une VM
* Le logiciel Wireshark installé
Si ce n'est pas fait tu peux faire la quête Odyssey qui te permettra de l'installer.

## Capture d'un ping

1. Noter l'adresse IP et l'adresse MAC du PC (ou de la VM) qui va lancer la capture
2. Désactiver le pare-feu sur la machine (cela peut poser des problèmes)
2. Lancer une capture Wireshark
3. Lancer une commande ping vers l'adresse IP 104.21.79.167 en forçant l'IPv4 :
    ```shell
    ping 104.21.79.167 -4
    ```
4. Attendre quelques instant et arreter la capture

## Analyse de la capture

1. Dans la fenêtre de capture principale, chercher une ligne qui a dans la colonne **Info** l'information **"Echo (ping) request"** et selectionner là
2. Dans la zone de détails des paquets, cliquer sur la croix pour voir le détail de la ligne **"Ethernet II"**
3. Vérifier que :
    - **"Source"** correspond à ton adresse MAC
    - **"Destination"** correspond à l'adresse MAC physique du poste cible
      - En l'occurence ici, il est possible que cela corresponde à l'adresse MAC de ta box internet
4. De la même manière, aller sur la ligne **"Internet Protocol version 4"**, et vérifier que :
    - **"Source"** correspond à ton adresse IP
    - **"Destination"** correspond à l'adresse IP distante
5. Enfin, aller sur la ligne **"Internet Control Message Protocol"**
    - Tu es en train de consulter  en  détail  une  trame **"Info = Echo (ping) request"**
    - Vérifie  que  tu as bien  ici  **"Type:  8  (Echo  (ping) request)"**.
6. Essaye de trouver les mêmes informations mais cette fois-ci pour une ligne **"Echo (ping) reply"**:
    - L'adresse MAC source
    - L'adresse MAC destination
    - L'adresse IP source
    - L'adresse IP destination
    - l'information **"Echo (ping) reply"**
7. Autres questions:
    - Sur  quel  type  de  codage  (du  système  de  numération)  est  codée  l’adresse  MAC  physique  ?
    - Sur combien d’octets est codée l’adresse MAC physique ?
    - À quoi correspondent les 3 premiers octets d'une adresse MAC physique ?
    - Et les 3 autres octets ? 
8. Bonus :
Va sur le site https://www.courbis.fr/Recherche-du-constructeur-pour-une.html et rentre ton adresse MAC pour avoir des informations sur le constructeur


## Complément d'informations: Structure de différentes trames


### Structure de la trame Ethernet
![image](https://www.ionos.fr/digitalguide/fileadmin/DigitalGuide/Screenshots_2019/ethernet-frame-FR-1.png)
* Quelques types :
  - 0x0200 = XEROX PUP
  - 0x0800 = DoD Internet (IPv4)
  - 0x0806 = ARP
  - 0x8035 = RARP
  - 0x86DD = Internet Protocol Version 6 (IPv6)

### Structure de la trame ARP
![image](https://docplayer.fr/docs-images/43/13107575/images/page_11.jpg)
* Quelques types :
  - 0x0001 = Ethernet
  - 0x0800 = DoD Internet (IPv4)
* Opérations :
  - 0x0001 = Requête
  - 0x0002 = Réponse

### Structure du paquet IPv4
![image](https://www.ciscomadesimple.be/wp-content/uploads/2014/11/ipv4-header.png)
* Version = Version d’IP
* IHL = Longueur de l’en-tête IP (en mots de 32 bits)
* TOS = Type de service (zero généralement)
* Flag  (3 premiers bits) = Bits pour la fragmentation
  - 1er = Reservé
  - 2me = Ne pas fragmenter
  - 3me = Fragment suivant existe
* Fragment Offset (13 bits suivants) = Décalage du fragment
* TTL = Durée de vie restante
* Protocoles:
   - 1 = ICMP
   - 4 = IP (encapsulation) 
   - 6 = TCP
   - 8 = EGP
   - 11 = GLOUP
   - 17 = UDP
   - 46 = RSVP

### Structure du paquet ICMP
![image](https://rex.plil.fr/Enseignement/Reseau.Archives/Reseau.BCEE/reseau057.gif)
* Quelques types ICMP :
  - 0 = Réponse d’echo
  - 8 = Demande d’écho
  - 11 = Durée de vie écoulée
  - 12 = Erreur de paramètre

### Structure de segment TCP
![image](https://sites.google.com/site/6hyperyon9/_/rsrc/1269971733572/reseau/differents-protocoles/tcp/EnteteTCP.PNG)
* Taille entête (THL) = Longueur de l’entête TCP sur 4 bits (*32bits)
* Code (Flag) = indicateur codé sur 6 bits gauche à droite
  - 1er = Données urgentes (URG°
  - 2me = Acquittement (ACK)
  - 3me = Données immédiates (PSH)
  - 4me = Réinitialisation (RST)
  - 5me = Synchronisation (SYN)
  - 6me = Terminaison (FIN)
* Options = suites d’option codées sur
  - 1 octet à 00 = Fin des options
  - 1 octet à 01 = NOP (pas d’opération)
  - plusieurs octets de type TLV
    - T = un octet de type:
      - 2 Annonce de la taille max. du segment
      - 3 Adaptation de la taille de la fenêtre
      - 4 Autorisation des acquittements sélectifs
      - 8 Estampilles temporelles
    - L = un octet pour la taille totale de l’option
    - V = valeur de l’option (sur L-2 octets)

### Structure de datagramme UDP
![image](https://i2.wp.com/ipwithease.com/wp-content/uploads/2018/01/091-udp-user-datagram-protocol-01.png)


