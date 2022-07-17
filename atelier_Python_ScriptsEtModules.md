# Workshop Python - Scripts et modules

##

#### Bien utiliser les scripts et les modules
----
#### 1. Prérequis
Pour réaliser ce workshop, il te faut :
* Un hôte ou une VM (avec Linux ou Windows)
***Attention*** : Si tu ne maitrise pas bien ton OS, le lancement de scripts peut amener des dysfonctionnements sur ton ordinateur. Pour plus de sécurité, utilise une VM.
* Un interpreteur Python ou un éditeur de code comme VSCode
> Ce workshop a été validé sur une machine avec les paramètres suivants :
> * Ubuntu 22.04 LTS
> * Visual Studio Code 1.68.1
> * Python3 installé sur l'OS

#### 2. Gestion de script Python
##### a. Créer le script Python demandeUtilisateur.py suivant :
```python
# demandeUtilisateur.py
# Ce script pose une question à l'utilisateur
# L'utilisateur doit donner un nombre comme réponse
nom = input("Quel est votre nom ?")
prenom = input("Quel est votre prénom ?")
age = input("Quel est votre age ?")
print("Bonjour", nom, prenom, ", vous avez", age, "ans")
```
* Attention à l'extension du fichier `.py`
* Tu dois avoir les droits d'éxécution sur le fichier

On peut exécuter le script dans un terminal comme ci-dessous :
```shell
python3 ./demandeUtilisateur.py
```
Ou directement dans la console de l'éditeur de code.

##### b. Utilisation de paramètres de fonctions
Les commandes telles que `print` sont des fonctions.
On peut modifier leur comportement avec des paramètres.

Essayons avec `sep` dans la commande `print` en changeant la dernière commande print du script précedent par cette ligne :
```python
print("Bonjour", nom, prenom, ", vous avez", age, "ans", sep="--")
```
Que constate-tu dans l'affichage de sortie ?

Tu trouveras d'autres paramètres sur la commande `print` [ici](https://www.w3schools.com/python/ref_func_print.asp#:~:text=The%20print()%20function%20prints,before%20written%20to%20the%20screen.)

#### 2. Gestion des modules

##### a. Installation du module Tkinter au niveau du système
Nous alons installer le module `Tkinter` :
```sh
sudo apt install python3-tk
```

##### b. Création du script python drawingTurtle.py
```python
# drawingTurtle.py
# Import du module turtle
from turtle import *
color('red', 'yellow')
begin_fill()
while True:
    forward(200) # Avance de 200
    left(170) # Tourne à gauche de 170 degrés
    if abs(pos()) < 1:
        break
end_fill()
done()
```
Ecrit ce script et éxecute-le.
Que ce passe t'il à l'écran ?
Grâce à l'import du module, d'autres fonctionnalités sont possible.
Tu trouveras [ici](https://ensip.gitlab.io/pages-info/ressources/transverse/tuto_turtle.html) toutes les possibilités du module `turtle`
Tu pourras t'entrainer à l'utilisation de ce module en ligne [en cliquant ici](https://trinket.io/python/e014ecb723)

##### c. Création d'un module personnel
Nous allons créer un module contenant 3 fonctions. Ces fonctions auront comme paramètre une variable **nom** de type `string` soit une **chaine de charactères**.
Enregistrer le contenu du code suivant dans un fichier python message.py :
```python
# message.py
def arrivee(nom):
    # Dit Bonjour
    return "Bonjour " + nom

def depart(nom):
    # Dit au revoir
    return "Au revoir " + nom

def derien(nom):
    # Dit merci
    return "Merci " + nom
```

##### d. Utilisation de notre module personnel
Dans l'interpreteur Python, on importe d'abord le module :
```python
>>> import message
```

Ensuite on va pouvoir appeler directement chaque fonction selon les besoins :
```python
>>> message.arrivee("Jean")
'Bonjour Jean'
>>> message.depart("Chloé")
'Au revoir Chloé'
>>> message.derien("Fabrice")
'Merci Fabrice'
```
En utilisant `import` on a pu utiliser le code contenu dans le module message.py.
Une fois cela fait, on peut utiliser chaque partie de ce module.
**Maintenant, à toi de jouer pour créer tes propres modules !**