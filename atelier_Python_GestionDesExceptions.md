# Workshop Python - Gestion des exceptions

##

#### Comment gérer les erreurs de sortie ?
---
#### 1. Prérequis
Pour réaliser ce workshop, il te faut :
* Un hôte ou une VM (avec Linux ou Windows)
***Attention*** : Si tu ne maitrise pas bien ton OS, le lancement de scripts peut amener des dysfonctionnements sur ton ordinateur. Pour plus de sécurité, utilise une VM.
* Un interpreteur Python ou un éditeur de code comme VSCode
> Ce workshop a été validé sur une machine avec les paramètres suivants :
> * Ubuntu 22.04 LTS
> * Visual Studio Code 1.68.1
> * Python3 installé sur l'OS

#### 2. Compréhension des messages d'erreurs
##### a. Exception ou erreur de syntaxe ?
* Une erreur de syntaxe (ou de saisie) est une erreur d'écriture dans la forme du code. L'interpreteur ne comprend pas le code écrit car il est mal formaté, il manque des paramètres, etc.
* Une exception est une une erreur de gestion sur le fond du code. Par exemple provenant d'une variable non-initialisée, et qui par la suite amène une erreur de calcul non-gérée.

##### b. Erreur de syntaxe
Dans l'interpreteur Python, les erreurs de saisies sont retournées par le système.
En clair, Python va t'indiquer tout ce qui correspond à une erreur de saisie ou de syntaxe du code.
###### *exemple 1 :*
Tape le code suivant dans un interpreteur Python (c'est la 1ère ligne de définition d'une fonction), et éxecute-le :
```python
>>> def ma_fonction(a)
```
L'interpreteur va te renvoyer ceci :
```python
File "<stdin>", line 1
    def ma_fonction(a)
                        ^
SyntaxError: expected ':'
```

* **File "< stdin >", line 1** ==> indique une erreur à la ligne 1
* **def ma_fonction(a)** ==> la flèche indique l'emplacement de l'erreur, soit ici à la fin de la ligne
* **SyntaxError: expected ':'** ==> indication de l'erreur, ici, il manque un caractère deux point `:`

Ici, le message indique **une erreur de syntaxe**, il manque deux points à la fin de la ligne. Effectivement, on doit mettre le caractère deux point `:` à la fin de la ligne de définition d'une fonction.

###### *exemple 2 :*
Toujour dans l'interpreteur, écrit le code suivant et éxecute-le :
```python
>>> while i>0
  File "<stdin>", line 1
    while i>0
             ^
SyntaxError: expected ':'
```
Comme pour l'erreur dans la ligne de la définition d'une fonction, ici le message d'erreur indique clairement qu'il manque un caractère deux points `:`.

##### c. Les exceptions
###### *exemple 1:*
Ecrit le code suivant. Si tu as déjà utilisé la variable `my_var` change le nom par une toute nouvelle.
```python
>>> print(my_var)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'my_var' is not defined
```
Ici on veut afficher avec `print` le contenu de la variable `my_var`, or elle n'est pas définie, d'où le message d'erreur **"name 'my_var' is not defined"**
Dans ce cas, **l'exception** de l'affichage d'une variable non-connu n'a pas été gerée.

###### *exemple 2 :*
Ecrit le code suivant dans ton interpreteur :
```python
>>> 50/0
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: division by zero
```
Ici, c'est une erreur de calcul de division par zéro qui est generée et affichée avec **"ZeroDivisionError: division by zero"**.
Dans ce cas, on a encore **une exception** non-gérée.

#### 3. Gestion des exceptions
##### a. La commande *try...except...else...finally*
Pour gérer les erreurs de saisie, et plus globalement d'entrée et de sortie du code, on va devoir gérer des **exceptions**.
Pour cela, en Python, on va utiliser la commande **`try...except...else...finally`** avec la structure suivante :
```python
try:
        bloc de code
except Exception 1 :
        bloc de code
except Exception 2 :
        bloc de code
...
except Exception n :
        bloc de code n
else :     #(optionnel)
        bloc de code 
finally :  #(optionnel)
        bloc de code 
```
Regardons de plus près cette commande et ce qui la compose :
* `try` : va vérifier le bloc de code et l'évaluer pour savoir s'il contient une erreur
* `except` : si une ou des erreurs sont detectées dans le 1er ***bloc de code***, c'est ici que l'on va gérer les exceptions
On peut mettre autant d'`except` que l'on veut
* `else` : s'il n'y a aucune erreur détéctée dans le `try` , cette partie est exécutée (section facultative)
* `finally` : les instructions placées ici seront exécutées dans tous les cas, on ignore les blocs de **try** et **except** (section facultative)

##### b. Quelles sont les exceptions gerées ?
On va pouvoir gérer :
* Des valeurs incorrectes avec `ValueError`
* Des problèmes de type de données avec `TypeError`
* Des problèmes d'indexe ou de non-accès à des listes, des tuples, ... avec `IndexError`
* Des clés non-existante dans des dictionnaires avec `KeyError`
* Des erreurs de divizion par zéro avec `ZeroDivisionError`
Et encore bien d'autres !
Tu trouveras dans la documentation officielle [ici](https://docs.python.org/3/library/exceptions.html) la liste des exceptions. Pour avoir quelques exemples supplémentaires, tu peux aller [ici](https://www.tutorialsteacher.com/python/error-types-in-python).

##### c. Exemple 1 : gestion de valeur incorrecte
Ecrit ou colle le code ci-dessous dans un script Python et execute-le :
```python
#script1.py
while True:
    try:
        x = int(input("Merci d'entrer un nombre entier: "))
        break
    except ValueError:
        print("Un nombre entier svp, merci !")
```
Essaye de rentrer différentes valeurs comme ci-dessous :
```python
Merci d'entrer un nombre entier: a
Un nombre entier svp, merci !
Merci d'entrer un nombre entier: 3.4
Un nombre entier svp, merci !
Merci d'entrer un nombre entier: 10
```
* En mettant `int` devant la commande `input` on force l'entrée d'une valeur de type `int`, soit un nombre entier.
* Si on rentre un nombre entier, le code de sortie sera **True** et on peut passer à la ligne d'apès, soit la commande `break` qui nous fait sortir du `try` et de la boucle `while`
* Si on rentre un autre caractère qu'un nombre entier, le code de sortie sefa **Talse**, et donc on va passer dans la partie `except` de la commande. 
On a fait un `except` sur une **ValueError**, donc dès que mauvaise valeur est détectée, on passe dans cette partie.
Donc on affiche le contenu du `print` et on revient dans la boucle.

##### d. Exemple 2 : Gestion d'interruption clavier
Exécute le script ci-dessous :
```python
#script2.py
try:
    x = input()
    print ("Essaye de faire une interuption clavier avec ctrl+c par exemple !")
except KeyboardInterrupt:
    print ("Interruption clavier détectée !!!")
else:
    print ("Aucune interuption clavier détectée...")
```
* Le code attend un evenement clavier
* Soit on rentre quelque-chose au clavier et on a ceci :
```python
Essaye de faire une interuption clavier avec ctrl+c par exemple !
Aucune interuption clavier détectée...
```
* Ou bien on ne rentre rien et on fait `CTRL + C` et on a ceci :
```python
Interruption clavier détectée !!!
```
##### e. Exemple 3 : Gestion d'erreur de calcul
Reprenons l'exemple de la division par zero. Le code du script ci-dessous montre une manière de la traiter :
```python
# script3.py
try:
    a = int(input("Entrer un nombre : "))
    b = int(input("Entrez un autre nombre : "))
    resultat = a / b
    print("Le resultat de la division est", resultat)
except ValueError:
    print("Désolé, les valeurs saisies ne sont pas des nombres.")
except ZeroDivisionError:
    print("Désolé, la division par zéro n'est pas permise.")
```
* Si on rentre deux nombres dont le deuxième n'est pas égal à zéro, comme 10 et 2, on aura :
```python
Le resultat de la division est 5
```
* Si on rentre autre-chose que des nombres, on aura le message suivant :
```python
Désolé, les valeurs saisies ne sont pas des nombres.
```
> Remarque :
Ce message apparait directement si l'entrée du 1er nombre n'est pas bonne. On voit ainsi que le `try` traite toutes les instructions séparement, et pas en bloc.
* Si on rentre deux nombres dont le deuxième est égal à zero, on n'a pas de message d'erreur mais le message suivant :
```python
Désolé, la division par zéro n'est pas permise.
```

#### 4. Aller plus loin avec try...except
##### a. Cumulation d'except
On peut écrire le dernier code qui traite de la division par zéro de cette autre manière :
```python
# script4.py
try:
    a = int(input("Entrer un nombre : "))
    b = int(input("Entrez un autre nombre : "))
    resultat = a / b
    print("Le resultat de la division est", resultat)
except (ValueError, ZeroDivisionError):
    print("Désolé, quelque chose ne s'est pas bien passé.")
```
* Ici on a cumulé les excepts pour traiter toutes les erreurs de valeur en une seule fois
* Le code est plus court, mais on pert en précision de traitement par type d'exception

##### b. Utilisation du else
Toujours avec le traitement de la division par zéro, on peut écrire le code plus **proprement** avec la partie `else` :
```python
# script5.py
try:
    a = int(input("Entrer un nombre : "))
    b = int(input("Entrez un autre nombre : "))
    resultat = a / b
except (ValueError, ZeroDivisionError):
    print("Désolé, quelque chose ne s'est pas bien passé.")
else:
    print("Le resultat de la division est", resultat)
```
* Comprend-tu l'interêt de mettre le `print("Le resultat de la division est", resultat)` dans la partie `else` et pas dans le `try` ?
> `else` traite les instructions si le bloc `try` ne retourne pas d'erreurs. Donc ça peut être un bon moyen de **valider** le bloc `try`

##### c. Utilisation du finally
Enfin on peut avoir besoin d'instructions qui s'executeront quel que soit le code :
```python
# script6.py
try:
    a = int(input("Entrer un nombre : "))
    b = int(input("Entrez un autre nombre : "))
    resultat = a / b
except (ValueError, ZeroDivisionError):
    print("Désolé, quelque chose ne s'est pas bien passé.")
else:
    print("Le resultat de la division est", resultat)
finally:
    print("Merci d'avoir participé à ce workshop !")
```
* Les instructions dans la partie `finally` sont toujours executées.
> En réalité, comme les instructions dans la clause `finally` sont toujours exécutées, on profite de cette partie pour libérer des ressources (fichiers, scripts, processus, connexions réseaux, ...)

##### d. Lancer une exception
On peut avoir besoin de créer une exception pour la traiter ensuite.
Exemple :
```python
# script7.py
def inverse(x):
    if x == 0:
        raise ValueError
    y = 1.0 / x
    return y

valeur = int(input("Donner un nombre :"))
try:
    resultat = inverse(valeur)  # erreur
    print(resultat)
except ValueError:
    print("erreur de type ValueError")
```
* `raise` déclenche une exception, ici de type **ValueError**.
* La fonctio **inverse** compare **x** à **0** et déclenche l'exception **ValueError** si x est nul.
* Cette exception est *"attrappée"* dans la partie `except` du `try`.
* En faisant cela, on n'affiche pas le message d'erreur et on traite l'exception.

Tu vas pouvoir maintenant commencer à traiter tes exceptions dans tes fichiers python.
**A toi de jouer !**