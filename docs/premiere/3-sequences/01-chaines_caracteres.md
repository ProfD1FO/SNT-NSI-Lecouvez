# Cours 1 - Les chaînes de caractères

Vous connaissez déjà le type chaîne de caractères en Python (str), il s'agt de l'un des 4 grands types de base. Ce que vous ignorez certainement, c'est que ce type correspond également à une **séquence** de caractères.

Une **séquence** une collection ordonnée d'éléments, accessibles selon leur position. Dans le cas des str, les éléments sont des caractères. Jusqu'ici, notre manipulation des str était assez sommaire, on se contentait de les afficher ou parfois de les concaténer (fusionner). Mais le fait qu'il s'agisse de séquences va nous permettre de faire des choses bien plus intéressantes avec.

## Rappels

En Python, une chaîne de caractères est toujours entourée de "" qui contiennent un nombre quelconque de caractères. Par exemple :

```python
chaine1 = "Bonjour"
chaine2 = ""
chaine3 = "Je pense donc je suis ..."
```

On peut également additionner des str entre eux avec l'opérateur `+` :

```python
>>> chaine1 + chaine3
"BonjourJe pense donc je suis ..."
```

Ou les afficher avec `print` :

```python
print(chaine3)
```

## Partie 1 - Accéder aux éléments d'une séquence : les indices

Entrons maintenant dans le vif du sujet. Puisque nous avons face à nous une séquence de caractères, il serait intéressant de pouvoir accéder séparément à chacun d'entre eux. Pour cela, on utilise les **indices**.

Un indice est un entier positif ou nul correspondant à la position d'un élément dans une séquence. **Le premier élément est toujours associé à l'indice `0`.**

Prenons la chaîne suivante :

```text
B   o   n   j   o   u   r
0   1   2   3   4   5   6
```

Chaque caractère possède ainsi un **indice** qui permet de l'identifier au sein de la chaîne.

En Python, on utilise l'indice entre crochets pour accéder à l'élément correspondant :

```python
chaine = "Bonjour"

chaine[0]  # "B"
chaine[3]  # "j"
chaine[6]  # "r"
```

De manière générale, on peut donc considérer `chaine[i]` comme « l'élément de la chaîne situé à l'indice `i` ».

!!! example "À tester"
    Sans tester, que va afficher le programme suivant :

    ```python
    chaine = "Bonjour"

    print(chaine[1])
    print(chaine[5])
    ```

!!! tip "À retenir"
    En Python, dans une séquence, on accède aux différents éléments grâce aux **indices**, des valeurs qui correspondent à la position des éléments. On commence toujours à l'indice 0 puis 1, 2, ect ... 
    Par exemple, on aura :

    ```python
    >>> nom = "Verso"
    >>> nom[0]
    'V'
    >>> nom[3]
    's'
    ```

!!! warning "Attention"
    En python, si l'on tente d'accéder dans une séquence à un indice qui n'existe pas, on obtient une erreur de type : IndexError: index out of range (en français, "indice en dehors de la séquence"). Par exemple :

    ```python
    >>> nom = "Verso"
    >>> nom[5]
    ERREUR
    ```

### Les indices négatifs

En Python, il existe une syntaxe assez particulière : les **indices négatifs**. Ils permettent d'accéder aux éléments d'une séquence en partant de la fin.

Le dernier élément correspond à l'indice `-1`, l'avant-dernier à `-2`, puis ainsi de suite :

```text
B   o   n   j   o   u   r
0   1   2   3   4   5   6
-7 -6  -5  -4  -3  -2  -1
```

On peut donc utiliser des indices négatifs exactement comme les indices positifs :

```python
chaine = "Bonjour"

chaine[-1]  # "r"
chaine[-2]  # "u"
chaine[-7]  # "B"
```

Cela peut notamment être pratique lorsque l'on souhaite accéder aux derniers éléments d'une séquence sans avoir à connaître sa longueur.

!!! example "À tester"

    Sans tester, que va afficher le programme suivant :

    ```python
    chaine = "Bonjour"

    print(chaine[-1])
    print(chaine[-4])
    ```


!!! tip "À retenir"
    Les indices négatifs permettent de parcourir une séquence **à partir de la fin**.

    - `-1` correspond au dernier élément ;
    - `-2` correspond à l'avant-dernier ;
    - `-3` correspond au troisième élément en partant de la fin ;
    - etc...

### La longueur d'une séquence

En Python, tous les types de séquences disposent d'une fonction appelée `len` et qui renvoie sa longueur. Cela fonctionne donc pour les chaînes de caractères. Par exemple :

```python
>>> philo = "Je pense donc je suis"
>>> len(philo)
21
>>> rien = ""
>>> len(rien)
0
```

!!! tip "Pause - à vous de jouer"
    Faites les exercices 1, 2 et 3 de la fiche d'exercices 1 du chapitre


## Partie 2 - Parcourir une séquence 

Nous arrivons à la partie difficile mais aussi la plus importante pour la suite de l'année. Comment faire pour parcourir les éléments d'une séquence un par un afin de les manipuler?

### Parcourir une séquence par éléments

Nous savons maintenant accéder à n'importe quel élément d'une séquence grâce à son indice.

Mais imaginons que nous souhaitions **afficher tous les caractères** d'une chaîne, un par un.

On pourrait bien sûr écrire :

```python
chaine = "Bonjour"

print(chaine[0])
print(chaine[1])
print(chaine[2])
print(chaine[3])
print(chaine[4])
print(chaine[5])
print(chaine[6])
```

Cela fonctionne, mais cette solution présente un problème évident : elle devient rapidement très longue et dépend de la longueur de la chaîne que l'on ne connaît pas forcément à l'avance, surtout dans les fonctions.

Il serait beaucoup plus intéressant de pouvoir dire à Python :

> « Pour chaque caractère de cette chaîne, effectue cette instruction. »

Si vous vous rappelez, c'est précisément ce que permet la boucle `for`.

Nous allons donc utiliser une boucle `for` pour parcourir notre chaîne :

```python
chaine = "Bonjour"

for caractere in chaine:
    print(caractere)
```

Ici, la variable de boucle `caractere` prend successivement la valeur de chacun des éléments de la chaîne.

On peut donc visualiser ce qui se passe de la manière suivante :

```text
Tour 1 : caractere = "B"
Tour 2 : caractere = "o"
Tour 3 : caractere = "n"
Tour 4 : caractere = "j"
Tour 5 : caractere = "o"
Tour 6 : caractere = "u"
Tour 7 : caractere = "r"
```

À chaque tour de boucle, l'instruction `print(caractere)` est donc exécutée avec une nouvelle valeur.

!!! tip "À retenir"

    Pour parcourir directement les éléments d'une séquence, on peut utiliser une boucle `for` :

    ```python
    for element in sequence:
        # instructions
    ```

    La variable `element` prend successivement la valeur de chacun des éléments de la séquence. On effectue donc un nombre de tours qui correspond au nombre d'éléments de la séquence


!!! example "À tester"

    Sans tester, que va afficher le programme suivant ?

    ```python
    mot = "Python"

    for caractere in mot:
        print(caractere)
    ```


Mais parcourir une séquence ne signifie pas forcément uniquement afficher ses éléments. On peut également les **manipuler**.

Par exemple :

```python
mot = "Bonjour"

for caractere in mot:
    print(caractere * 2)
```

Ici, chaque caractère est récupéré l'un après l'autre puis affiché deux fois.

!!! example "À vous de jouer"

    Modifiez le programme précédent afin qu'il affiche uniquement les caractères `o` présents dans le mot.

    ```python
    mot = "Bonjour"

    for ... in ...:
        ...
        ...
        
    ```


### Parcourir une séquence avec ses indices

La méthode précédente est très pratique lorsque l'on s'intéresse directement aux éléments de la séquence.

Mais imaginons maintenant que nous souhaitions afficher **à la fois le caractère et son indice**.

On pourrait accéder aux caractères grâce aux indices que nous avons vus précédemment :

```python
chaine = "Bonjour"

print(chaine[0])
print(chaine[1])
print(chaine[2])
...
```

Il faudrait cependant trouver un moyen de faire varier automatiquement l'indice.

Nous avons justement vu qu'un indice est un entier et que `len` permet de connaître le nombre d'éléments d'une séquence. Nous pouvons donc utiliser `range` pour générer les différents indices :

```python
chaine = "Bonjour"

for i in range(len(chaine)):
    print(i, chaine[i])
```

La variable `i` prend ici successivement les valeurs `0`, `1`, `2`, ..., `6`.

À chaque tour de boucle, `chaine[i]` permet alors d'accéder au caractère correspondant.

On obtient donc :

```text
0 B
1 o
2 n
3 j
4 o
5 u
6 r
```

!!! example "À vous de jouer"
    Écrivez un programme qui affiche chaque caractère du mot `"Informatique"` accompagné de son indice.

    Le résultat devra avoir la forme :

    ```text
    0 I
    1 n
    2 f
    ...
    ```


!!! tip "À retenir"
    Il existe donc deux manières principales de parcourir une séquence avec une boucle `for`.

    Lorsque l'on a seulement besoin des éléments :

    ```python
    for element in sequence:
        ...
    ```

    Lorsque l'on a besoin des indices dans notre programme:

    ```python
    for i in range(len(sequence)):
        ...
    ```

!!! tip "Pause - à vous de jouer"
	Faites le reste des exerices de la fiche d'exercices 1.



