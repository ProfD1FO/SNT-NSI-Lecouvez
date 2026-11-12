# Cours 3 : Les tuples Python

Pour conclure ce chapitre sur les séquences, nous allons en voir une dernière : **les tuples**

En Python, le type `tuple` est un type très pratique car il permet comme les listes de stocker des éléments de plusieurs types différents. Jusqu'ici, rien de nouveau, les listes le permettent également. 

La différence fondamentale est que les tuples sont **immutables**, c'est à dire qu'**on ne peut pas** y ajouter / retirer ou modifier d'éléments à l'intérieur. C'est comme pour les chaînes de caractères.

Ce cours sera court, notamment car la manipulation des tuples fonctionne exactement comme pour les autres séquences. La différence réside principalement dans les utilisations possibles des tuples.

## Objectifs:

- Savoir écrire des tuples

- Pouvoir manipuler les données des tuples

- Savoir quand utiliser un tuple plutôt qu'une liste ou une chaîne de caractères.

## Définir un tuple

En Python, les tuples sont entourés **de parenthèses**. Voici différents exemples :

```python
prenoms = ("Verso","Clea", "Maelle")

notes = (12.4, 20, 6.5, 4)
```

Comme les tuples sont immutables, une fois créés, impossible de les modifier. Ils sont donc fixes mais garantissent une vraie fiabilité des données. En effet, si on ne peut pas le modifier, je sais que les données qu'il contient ne seront pas faussées avec le temps. Par exemple les coordonnées d'un point ne sont pas destinées à changer, on les met donc dans un tuple `(x,y)` . Les couleurs d'un pixel auront toujours trois composantes (rouge, vert, bleu), on les mettra donc dans un tuple `(r, v, b)` .

## Indices de tuples

Vous avez probablement compris le fonctionnement des **indices**. Ils représentent la position des éléments dans les séquences et sont évidemment présents dans les tuples.

Quelques exemples pour vérifier s :

!!! example "À faire"
    Sans tester au préalable, donnez les résultats des affichages suivants:

    ```python
    prenoms = ("Verso","Clea", "Maelle")

    notes = (12.4, 20, 6.5, 4)

    print(prenoms[2])

    print(notes[-1])

    print(prenoms[0][2])

    note = notes[1]

    print(note+1)
    ```

## Parcourir les tuples

Encore une fois, aucune différence par rapport aux autres séquences dans la manière de les manipuler. On a besoin de pouvoir les parcourir et pour cela deux méthodes :

- parcourir par éléments

- parcourir par indices

### Parcourir par éléments

Même chose que pour les autres, le parcours par éléments suit toujours la même syntaxe :

```python

temperatures = (22, 30, 17, 19, 23)

for elt in temperatures:
    print(elt)
```

### Parcourir par indices

Même chose que pour les autres, le parcours par indices suit toujours la même syntaxe :

```python

temperatures = (22, 30, 17, 19, 23)

for i in range(len(temperatures)) :
    print(i , temperatures[i])
```


!!! warning "Attention"
    Vous l'aurez compris, les tuples ont **une taille fixe** puisqu'on ne peut ni ajouter ni retirer d'éléments. Cela fait qu'on utilise régulièrement les tuples pour des séquences avec un nombre d'éléments très limité (coordonnées de points, couleurs rvb, ...). 
    Cette particularité fait que l'on a rarement besoin de parcourir un tuple. Par exemple, si il contient 3 éléments, on va plutôt les stocker dans les variables et les manipuler directement, pas les parcourir. Par exemple pour une couleur :

    ```python
    couleur = (255, 0, 100)

    rouge = couleur[0]
    vert = couleur[1]
    bleu = couleur[2]

    print(rouge, vert, bleu)
    ```

    Ici, on peut se permettre de faire ça car on sait qu'un tuple de couleur **contiendra toujours** 3 éléments. 

