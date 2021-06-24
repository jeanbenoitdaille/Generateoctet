# Generateoctet
Générer un octet obligatoire 
Dans cet exercice, le but était de générer un octet aléatoire. Un octet est composé uniquement des chiffres 0 et 1, et contient 8 chiffres.

Il fallait donc pouvoir générer une séquence aléatoire de 8 chiffres de 0 à 1.

En Python, pour tout ce qui touche aux fonctions aléatoires, on utilise le module random, que nous importons donc à la première ligne de notre script :

    import random

La ligne suivante contient toute la logique du script. On aurait pu décomposer cette ligne en plusieurs lignes pour rendre la lecture plus facile, mais nous sommes quand même rendus assez loin dans les exercices pour pouvoir écrire du code un peu plus optimisé.

Nous utilisons donc une compréhension de liste pour créer une suite de 8 chiffres aléatoire allant de 0 à 1.

Pour récupérer un nombre aléatoire entre 0 et 1, on utilise la fonction "choice" du module random :

    random.choice(range(2))

La fonction range(2) nous retourne une liste contenant les nombres 0 et 1, et la fonction choice du module random va choisir un nombre aléatoire entre tous les nombres de la liste (donc soit 0 soit 1).

Nous utilisons ensuite une boucle for pour répéter l'opération 8 fois :

    for _ in range(8)

Vous noterez qu'on utilise un nom de variable quelque peu particulier pour la boucle for. En effet, cette boucle sert uniquement à répéter une opération un certains nombre de fois, mais on ne fait aucune utilisation de la variable générée à chaque itération de la boucle for. Par convention, quand on déclare une variable qui n'est pas utilisée, on utilise un tiret du bas.

Cette syntaxe en une seule ligne avec une compréhension de liste est équivalente à la syntaxe suivante, si cela peut vous aider à comprendre ce qu'il se passe ici :

    octet = []
    for _ in range(8):
        octet.append(str(random.choice(range(2))))

Notez également que nous convertissons directement en chaîne de caractère le nombre généré avec la fonction choice.

Nous faisons cela car nous utilisons ensuite la fonction "join" pour joindre tous les nombres de la liste et la fonction join ne marche qu'avec des chaînes de caractère.

    >>> liste_random = [str(random.choice(range(2))) for _ in range(8)]
    >>> print(liste_random)
    ["0", "1", "1", "0", "0", "1", "1", "0"]
    print("".join(liste_random))
    "01100110"
