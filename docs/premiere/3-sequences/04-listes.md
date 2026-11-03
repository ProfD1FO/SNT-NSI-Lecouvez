# Cours 2 : Les listes Python

Maintenant que vous êtes capables de manipuler une séquence (indices et parcours), il est temps pour vous de découvrir un tout nouveau type de séquence : les **listes Python**

## Partie 1 - Manipuler et comprendre les listes

### Définition des listes

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
	
	
!!! warning "Attention"
	Attention, comme une liste accepte différents types d'éléments, il est théoriquement possible de mettre plusieurs types différents dans une seule liste, par exemple, `li = [2, "Jean", True, 6.1]`. 
	
	Cependant, en pratique, il est extrêmement rare que cela puisse être utile, en plus de rendre le débuggage plus difficile. On évitera donc de mélanger les types dans une même liste.

### Indices de liste

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

### Parcourir les listes

Encore une fois, qui dit séquence d'éléments dit forcément moyen de les parcourir. Ici comme pour les indices, la méthode est **exactement** la même que pour les chaînes de caractères. On utilise donc encore une fois les boucles. La partie qui va suivre sera donc presque en tout point identique à celle du cours précédent.

#### Parcours élément par élément

Pour parcourir une séquence **élément par élément**, (ce qui veut dire qu'à chaque tout, la variable de boucle devient l'élément suivant de la séquence), on utilise la boucle `for`. 

!!! example "À tester"
    Sans tester avec Python, déduire ce que va afficher le programme suivant :

    ```python
    li = [33, 21, 11, 99, 2]

    for element in li :
        print(element)
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
#### Parcours par indices

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
	
	NB : En Python, None est une valeur spéciale qui signifie "rien". Il peut être pratique de l'utiliser lorsque l'on souhaite ne rien renvoyer dans certains cas d'une fonction, comme au dessus.

### Listes de listes

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

!!! tip "À vous de jouer"
    Faites les exercices 1,2,3 et 4 de la fiche d'exercices 2 du chapitre

## Partie 2 - Fabriquer et modifier des listes

Jusqu'à présent, nous avons appris à créer des listes et à accéder à leurs éléments. Cependant, les listes Python possèdent une propriété très intéressante que les chaînes de caractères ne possèdent pas : elles sont **modifiables** (on dit aussi **mutables**)!

Cela signifie que nous pouvons changer leur contenu après leur création, en ajoutant, supprimant ou remplaçant des éléments.

### Modifier un élément

Nous avons vu qu'il était possible d'accéder à un élément d'une liste grâce à son indice. Il est également possible de modifier directement cet élément en utilisant cette même notation.

Par exemple :

```python
notes = [12, 15, 8, 17]

notes[2] = 14

print(notes)
# [12, 15, 14, 17]
```

Ici, nous avons remplacé l'élément d'indice 2, qui valait initialement `8`, par la valeur `14`.

!!! example "À tester"
    On considère la liste suivante :

    ```python
    nombres = [4, 8, 12, 16, 20]
    ```

    1. Remplacer le premier élément par `10`.
    2. Remplacer le dernier élément par `30`.
    3. Afficher la liste obtenue.

### Ajouter et supprimer des éléments

Il est également possible de modifier la taille d'une liste, en ajoutant ou en supprimant des éléments.

Pour cela, nous allons découvrir deux méthodes particulièrement utiles.

#### Ajouter un élément avec `append`

La méthode `append()` permet d'ajouter un élément **à la fin** d'une liste.

Elle prend en paramètre l'élément à ajouter.

Attention, sa synatxe est particulière, il faut écrire : `liste.append(element)` .

Par exemple :

```python
prenoms = ["Alice", "Bob", "Charlie"]

prenoms.append("David")

print(prenoms)
# ["Alice", "Bob", "Charlie", "David"]
```

On remarque que la liste contient désormais un élément supplémentaire, placé à la fin.

!!! example "À tester"
    1. Créer une liste `animaux` contenant les chaînes de caractères `"chat"` et `"chien"`.
    2. Ajouter `"lapin"` à cette liste avec `append()`.
    3. Afficher la liste obtenue.

#### Supprimer un élément avec `pop`

À l'inverse, la méthode `pop()` permet de supprimer un élément d'une liste.

Elle prend en paramètre l'**indice** de l'élément à supprimer.

Attention, sa synatxe est particulière, il faut écrire : `liste.pop(indice)` .

Par exemple :

```python
prenoms = ["Alice", "Bob", "Charlie", "David"]

prenoms.pop(1)

print(prenoms)
# ["Alice", "Charlie", "David"]
```

Ici, nous avons supprimé l'élément d'indice 1, c'est-à-dire `"Bob"`.

Une particularité intéressante : `pop()` **renvoie également** l'élément qui vient d'être supprimé, elle fait deux choses en même temps. Il est donc possible de récupérer sa valeur dans une variable.

```python
prenoms = ["Alice", "Bob", "Charlie"]

supprime = prenoms.pop(1)

print(supprime)  # "Bob"
print(prenoms)   # ["Alice", "Charlie"]
```

!!! example "À tester"
    On considère la liste suivante :

    ```python
    couleurs = ["rouge", "vert", "bleu", "jaune"]
    ```

    1. Supprimer l'élément d'indice 2.
    2. Afficher la liste obtenue.
    3. Supprimer le premier élément et stocker sa valeur dans une variable `couleur`.
    4. Afficher la couleur supprimée puis la liste.
	
!!! tip "A savoir"
	Comme dit plus haut, la méthode `pop()` supprime l'élément d'indice voulu dans une liste. Elle a donc besoin d'un paramètre qui correspond à l'indice. 
	
	Cependant il est également possible de ne pas lui donner d'indice en paramètre. Par défaut, la méthode va supprimer et renvoyer le dernier élément de la liste. Par exemple:
	
	```python
	notes = [11, 10, 20, 14]
	notes.pop()
	print(notes)
	```
	Ce programme affichera `[11, 10, 20]` car le dernier élément a été supprimé.
	
### Construire une liste progressivement

Maintenant que nous savons ajouter des éléments à une liste, nous pouvons commencer à construire des listes progressivement grâce aux boucles.

Prenons un exemple : nous souhaitons créer une liste contenant uniquement les nombres pairs d'une autre liste.

```python
nombres = [3, 8, 12, 5, 7, 10]
pairs = []

for nombre in nombres:
    if nombre % 2 == 0:
        pairs.append(nombre)

print(pairs)
# [8, 12, 10]
```

Dans cet exemple, nous avons procédé en plusieurs étapes :

- Nous avons d'abord créé une liste vide appelée `pairs`.
- Nous avons ensuite parcouru tous les éléments de la liste `nombres`.
- Pour chaque élément, nous avons vérifié s'il était pair.
- Si c'était le cas, nous l'avons ajouté à la liste `pairs` avec `append()`.

Cette méthode est particulièrement utile lorsque l'on souhaite extraire certains éléments d'une liste en fonction d'une condition.

!!! example "À vous de jouer"
    Écrire une fonction `positifs(li)` qui prend en paramètre une liste d'entiers et qui renvoie une nouvelle liste contenant uniquement les nombres positifs de `li`.

    Par exemple :

    ```python
    >>> positifs([-3, 5, 0, -8, 12, 4])
    [5, 0, 12, 4]
    ```

### Quelques opérations utiles

Pour terminer, voici quelques opérations supplémentaires qui peuvent être utilisées avec les listes Python. Les trois dernières ne sont pas à connaître par coeur mais pourrons vous être utile par la suite .

| Instruction | Fonctionnement |
|---|---|
| `element in liste` | Vérifie si un élément appartient à une liste (renvoie True ou False) |
| `liste1 + liste2` | Fusionne deux listes (comme pour les chaînes de caractères) |
| `liste * 3` | Répète une liste trois fois (comme pour les chaînes de caractères) |
| `min(liste)` | Renvoie le plus petit élément |
| `max(liste)` | Renvoie le plus grand élément |
| `sum(liste)` | Calcule la somme des éléments |

Ces opérations permettent de manipuler plus facilement les listes sans avoir systématiquement besoin d'écrire une boucle.

!!! tip "À vous de jouer"
    Finissez les exercices de la fiche d'exercices 2 du chapitre.
