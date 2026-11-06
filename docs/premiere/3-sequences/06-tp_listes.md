# TP - Manipuler un jeu de cartes

## Présentation

Dans ce TP, nous allons programmer différentes fonctions permettant de manipuler un jeu de cartes classique de 52 cartes.

Un jeu classique est constitué de quatre couleurs :

- Pique
- Cœur
- Carreau
- Trèfle

Chaque couleur contient 13 cartes : les nombres de 2 à 10, ainsi que le Valet, la Dame, le Roi et l'As.

Notre objectif sera de construire un paquet de cartes, de le mélanger puis de distribuer des cartes à plusieurs joueurs.

Pour simplifier, nous représenterons chaque carte par une chaîne de caractères. Par exemple : `"7 de pique"` ou `"Dame de cœur"`.

## Partie 1 - Construire un paquet de cartes

### 1. Créer les cartes

Pour commencer, nous allons créer deux listes :

```python
couleurs = ["pique", "cœur", "carreau", "trèfle"]
valeurs = ["2", "3", "4", "5", "6", "7", "8",
           "9", "10", "Valet", "Dame", "Roi", "As"]
```

**Q1.** Écrire une fonction `creer_paquet()` qui renvoie une liste contenant les 52 cartes du jeu.

On pourra utiliser deux boucles imbriquées pour parcourir les deux listes et construire les cartes.

Par exemple :

```python
>>> paquet = creer_paquet()
>>> len(paquet)
52
>>> paquet[0]
"2 de pique"
```

**Q2.** Afficher les 52 cartes du paquet, une par une, à l'aide d'une boucle.

### 2. Vérifier le contenu du paquet

**Q3.** Écrire une fonction `compte_couleur(paquet, couleur)` qui prend en paramètres un paquet de cartes et une couleur, puis renvoie le nombre de cartes de cette couleur dans le paquet.

Par exemple :

```python
>>> compte_couleur(paquet, "pique")
13
```

**Q4.** Écrire une fonction `contient_carte(paquet, carte)` qui renvoie `True` si la carte recherchée est présente dans le paquet et `False` sinon.

Par exemple :

```python
>>> contient_carte(paquet, "As de cœur")
True
>>> contient_carte(paquet, "15 de pique")
False
```

## Partie 2 - Mélanger et manipuler le paquet

### 3. Mélanger les cartes

Un paquet de cartes est rarement utilisé dans son ordre initial : il faut généralement le mélanger avant de commencer une partie.

Pour cela, Python possède un module appelé `random`, qui contient notamment une fonction `shuffle()` permettant de mélanger aléatoirement les éléments d'une liste.

```python
from random import shuffle

cartes = [1, 2, 3, 4, 5]
shuffle(cartes)

print(cartes)
```

**Q5.** Écrire une fonction `melanger(paquet)` qui prend un paquet de cartes en paramètre et mélange directement son contenu.

On pourra utiliser la fonction `shuffle()` présentée ci-dessus.

**Q6.** Créer un paquet, le mélanger puis afficher son contenu. Vérifier que les 52 cartes sont toujours présentes après le mélange.

### 4. Piocher une carte

Lorsqu'un joueur pioche une carte, celle-ci doit être retirée du paquet.

Nous allons utiliser la méthode `pop()` pour réaliser cette opération.

**Q7.** Écrire une fonction `piocher(paquet)` qui retire et renvoie une carte du paquet.

On pourra choisir de piocher la dernière carte de la liste.

Par exemple :

```python
>>> paquet = ["As de pique", "Roi de cœur", "7 de trèfle"]
>>> carte = piocher(paquet)
>>> carte
"7 de trèfle"
>>> paquet
["As de pique", "Roi de cœur"]
```

**Q8.** Écrire une fonction `piocher_n(paquet, n)` qui permet de piocher `n` cartes dans un paquet. La fonction renverra une nouvelle liste contenant les cartes piochées.

Par exemple :

```python
>>> paquet = ["As de pique", "Roi de cœur", "7 de trèfle",
              "Dame de carreau", "10 de pique"]
>>> main = piocher_n(paquet, 3)
>>> len(main)
3
>>> len(paquet)
2
```

## Partie 3 - Distribuer les cartes

### 5. Distribuer les cartes aux joueurs

Nous allons maintenant simuler une véritable distribution de cartes.

Pour cela, nous représenterons les mains des joueurs par une liste de listes.

Par exemple, une partie avec trois joueurs pourrait être représentée ainsi :

```python
mains = [
    ["As de pique", "7 de cœur"],
    ["Roi de trèfle", "2 de carreau"],
    ["10 de pique", "Dame de cœur"]
]
```

Chaque sous-liste correspond à la main d'un joueur.

**Q9.** Écrire une fonction `distribuer(paquet, nb_joueurs, nb_cartes)` qui distribue le même nombre de cartes à chaque joueur.

La fonction devra renvoyer une liste contenant les mains de tous les joueurs.

Par exemple :

```python
>>> paquet = creer_paquet()
>>> melanger(paquet)
>>> mains = distribuer(paquet, 4, 5)
>>> len(mains)
4
>>> len(mains[0])
5
```

On supposera que le paquet contient suffisamment de cartes pour effectuer la distribution.

**Q10.** Écrire une fonction `afficher_mains(mains)` qui affiche les cartes de chaque joueur.

On pourra afficher les cartes sous la forme :

```text
Joueur 1 : As de pique, 7 de cœur, 3 de trèfle
Joueur 2 : Roi de carreau, 2 de pique, 10 de cœur
Joueur 3 : 5 de trèfle, Dame de pique, 8 de carreau
```

Ce TP est pour le moment terminé. Nous pourrons reprendre ce travail sur les cartes plus tard dans l'année à l'occasion du chapitre sur les dictionnaires Python. Ce sont des structure qui permettent d'associer une valeur à une autre. Très pratique lorsque l'on souhaite comparer deux valeurs non numériques comme le Roi et le valet.