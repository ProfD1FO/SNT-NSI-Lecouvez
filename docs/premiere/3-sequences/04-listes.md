# Cours 2 : Les listes Python

Maintenant que vous êtes capables de manipuler une séquence (indices et parcours), il est temps pour vous de découvrir un tout nouveau type de séquence : les **listes Python**

## Définition des listes

En Python, le type `list` est un type de données qui correspond à une séquence : c'est une suite ordonnée d'éléments accessibles selon leur position. Néanmoins, elles diffèrent des chaînes de caractères sur plusieurs points que nous allons voir ensemble dans ce cours. Il est également à noter que les listes sont un outil très puissant lorsque l'on manipule en Python, ce cours est donc essentiel.

Pour commencer, voyons déjà la syntaxe qui permet d'écrire une liste :

```python
liste_exemple = [3, 1, 4, 1, 2]
liste_exemple2 = ["Verso", "Mark", "Steve"]
```

Ici, il y a déjà deux choses à constater :

- Une liste Python est entourée de crochets `[` et `]` qui délimitent le début et la fin de la liste. C'est la syntaxe de base pour écrire une liste, cela correspond plus ou moins aux guillemets des chaînes de caractères.

- Une liste peut contenir plusieurs types d'éléments. Cela diffère nettement des chaînes de caractères qui ne contenaient que des caractères. Ici, on peut construire des listes de `int`, de `str`, de `float` ou même de `bool` . Cela multiplie nos possibilités et explique donc le grand intérêt des listes : nous allons pouvoir manipuler de grandes séquences de n'importe quel type.

!!! example "À faire"
    Créer une liste appelée `notes` et qui contiendra vos notes du trimestre en NSI pour le moment

## Indices de liste

Comme dit plus tôt, les listes sont des séquences et donc comme les chaînes de caractères, les mêmes outils peuvent être employés pour les manipuler à commencer par les indices et la fonction `len()`.

!!! example "À tester"
    Sans tester avec Python, déduire ce que va afficher le programme suivant :

    ```python
    ma_liste = [2, 4, 7, 8, 10]
    ma_liste_v2 = ["Axel", "Cloud", "Kena"]

    print(ma_liste[3])
    print(ma_liste[-1])
    print(ma_liste_v2[1])
    print(ma_liste_v2[9])
    print(len(ma_liste_v2))
    ```

Comme vous pouvez le constater, le fonctionnement est exactement le même qu'avec les `str`. On accède à un élément grâce à son **indice** correspondant à sa position dans la liste. Pour cela, on utilise toujours la même notation avec les crochets contenant l'indice auquel on souhaite accéder. 
Par exemple :

```python
>>> [1, 3, 9, -4, 0][3]
-4
```

Ici, on cherche à accéder à l'élément d'indice 3 de la liste `[1, 3, 9, -4, 0]`. Comme les indices commencent à 0, cela correspond au 4ème élément qui est donc -4.

## Parcourir les listes

Encore une fois, qui dit séquence d'éléments dit forcément moyen de les parcourir. Ici comme pour les indices, la méthode est **exactement** la même que pour les chaînes de caractères. On utilise donc encore une fois les boucles. La partie qui va suivre sera donc presque en tout point identique à celle du cours précédent.

### Parcours élément par élément

Pour parcourir une séquence **élément par élément**, (ce qui veut dire qu'à chaque tout, la variable de boucle devient l'élément suivant de la séquence), on utilise la boucle `for`. 

!!! example "À tester"
    Sans tester avec Python, déduire ce que va afficher le programme suivant :

    ```python
    li = [33, 21, 11, 99, 2]

    for element in li :
        print(li)
    ```

    Et maintenant que va afficher le programme suivant ?

    ```python
    li = [33, 21, 11, 99, 2]
    somme = 0

    for element in li :
        somme = somme + element
    print(somme)
    ```

On retrouve donc la syntaxe que nous avons vu qui permet de manipuler directement les éléments sans s'encombrer avec des indices. On peut la résumer de manière générale par :

```python
for variable in sequence :
    ...
    ...
```
### Parcours par indices

En fonction des besoins, il peut-être essentiel de pouvoir parcourir la séquence indice par indice. Par exemple lorsque l'on recherche la position précise d'un élément. Pour cela, on peut utiliser n'importe laquelle des deux types de boucles que vous connaissez : `for` et `while` et en utilisant ingénieusement la fonction `len`. 

!!! example "À tester"
    **Sans tester avec Python**, que va faire le programme suivant ? 

    ```python
    def mystere(li):
        for i in range(len(li)):
            if li[i] > 10 :
                return i
        return None
    
    >>> mystere([2,-6, 3, 12, 19])

    >>> mystere([2,-6, 3, 0, 9])

    ```

## Listes de listes

Nous avons vu au début que la grande particularité des listes était de pouvoir contenir des éléments de différents types. Pour le moment, nous n'avons mis dans les listes que les types de base que vous connaissez mais puisque que nous pouvons y mettre ce que l'on veut, on peut y mettre d'autres listes.

Par exemple :

```python
mega_liste = [[False, False, False],
              [False, True, False],
              [True, False, False],
              [True, True, True]]
```

Comme vous pouvez le voir, la liste `mega_liste` contient 4 listes qui contiennt chacune 3 booléens. Ce genre de listes est très utilisé en particulier lorsqu'il faut représenter un tableau à deux dimensions ou une matrice mathématiques. On l'utilise par exemple pour les pixels d'une image.

Il est surtout intéressant d'essayer de comprendre comment manipuler une telle liste. 

!!! example "À tester"
    Sans tester, que va afficher selon vous le programme suivant ?

    ```python
    mega_liste = [[False, False, False],
                [False, True, False],
                [True, False, False],
                [True, True, True]]
    
    print(mega_liste[2])
    print(mega_liste[-1])
    print(mega_liste[1][1])
    print(mega_liste[0][2])
    ```

Intéressons-nous rapidement à la syntaxe : `mega_liste[1][1]` . Ici, Python va agir en deux temps :

- D'abord on regarde qui est `mega_liste[1]` : cela correspond à la liste `[False, True, False]`
- Ensuite, il ne reste plus qu'à faire : `[False, True, False][1]` ce qui correspond à True. 

Le résultat final est donc True. 

