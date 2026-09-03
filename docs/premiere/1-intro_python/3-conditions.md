# Cours 2 : Les booléens et les instructions conditionnelles

Un autre outil essentiel pour bien programmer est de pouvoir utiliser des **instructions conditionnelles** . Elles permettent de placer un morceau du programme qui ne s'exécutera que si une certaine condition est respectée, c'est ce que nous verrons dans ce cours.

Pour permettre à un programme de déterminer si une condition est vraie ou fausse, nous avons besoin d'un type de données particulier : le type booléen.

## Objectifs

À la fin du chapitre, vous devez être capable de :

- Savoir faire des comparaisons en Python
- Comprendre l'intérêt des booléens et le fonctionnement de leurs opérateurs
- Connaître la syntaxe de l'instruction conditionnelle en Python ;
- Utiliser des instructions conditionnelles pour résoudre des problèmes de programmation simples;

## Partie 1 : Les booléens et les comparaisons

Durant le cours précédent, vous avez vu le type booléen (bool), celui-ci ne peut prendre que deux valeurs : `True` et `False`. Cela en fait le candidat parfait pour rédiger des conditions dans des programmes.

Dans un premier temps, nous allons voir des expressions capables de générer des booléens aussi appelées : **expressions booléennes**

### Les comparaisons

En Python, il est possible de comparer des valeurs de différents types (int, str, float...). En Python, le résultat d'une comparaison est soit vrai (True) soit faux (False), ce sont donc des expressions booléennes.

!!! example "À tester"
    Dans l'éditeur de code, écrivez :
    ```python
    annee = 2026
    age >= 2025
    ```
    Quel est le résultat de cette expression?


On peut résumer les différents opérateurs de comparaisons dans le tableau suivant :

| Opérateur | Signification       |
| --------- | ------------------- |
| `==`      | égal à              |
| `!=`      | différent de        |
| `<`       | strictement inférieur à |
| `>`       | strictement supérieur à |
| `<=`      | inférieur ou égal à |
| `>=`      | supérieur ou égal à |

!!! warning "Attention"
    En Python, il faut faire la différence entre le égal simple `=` qui permet de faire une **affectation** du double égal `==` qui permet de comparer deux valeurs.


!!! warning "Attention"
    Il faut bien différencier les opérateurs `>` et `<` des opérateurs `>=` et `<=`. Par exemple, on a :
    
    ```python
    >>> 16 > 16
    False
    >>> 16 >= 16
    True
    ```

!!! tip "À retenir" 
    Il est également possible de comparer des chaînes de caractères entre-elles. C'est facile à imaginer pour le `==` et le `!=` mais beaucoup moins pour les opérateurs d'ordre.
    Pour les comparaisons d'ordre sur des str, c'est l'ordre lexicographique (alphabétique qui est utilisé). Par exemple :
    
    ```python
    >>> "pomme" > "palmier"
    True
    ```

!!! tip "Pause — À vous de jouer"
    **Faites les exercices 1 et 2 de la fiche d'exercices 2.**


### Combinaisons d'expressions

Lorsqu'une situation est soumise à plusieurs contraintes, il est nécessaire de pouvoir combiner des expressions booléennes afin de les prendre en compte.

Prenons un exemple simple, une attraction n'est accessible que si la personne a plus de 12 ans **ET** mesure plus de 140 cm.

On peut dans un premier temps vérifier séparément les deux conditions :

```python
age > 12
taille > 140
```

Ces deux expressions produisent chacune une valeur booléenne (`True` ou `False`).

Il est ensuite possible de les combiner à l'aide d'un **opérateur booléen** :

```python
age > 12 and taille > 140
```

Cette expression n'est vraie que si **les deux conditions sont vraies**.

### Les opérateurs booléens

Python possède trois principaux opérateurs permettant de combiner ou de modifier des expressions booléennes :

| Opérateur | Signification                                     |
| --------- | ------------------------------------------------- |
| `and`     | ET : les deux expressions doivent être vraies     |
| `or`      | OU : au moins une des expressions doit être vraie |
| `not`     | NON : inverse la valeur de l'expression           |


!!! tip "À retenir"
    - `A and B` est vrai uniquement si `A` **et** `B` sont vrais.
    - `A or B` est vrai si `A` **ou** `B` est vrai.
    - `not A` inverse la valeur de `A`.

!!! example "À tester"

    Essayez de prévoir le contenu de a, b et c après exécution du programme suivant puis testez le :

    ```python
    age = 16
    taille = 150
    a = age >= 12 and taille >= 140
    b = age >= 18 or taille >= 140
    c = not (age >= 18)
    ```

!!! tip "Pause — À vous de jouer"
    **Faites les exercices 3 et 4.**

## Partie 2 : Les instructions conditionnelles

Nous savons maintenant construire des expressions qui permettent à Python de déterminer si une condition est vraie ou fausse.

Mais pour l'instant, Python se contente de nous donner le résultat de cette condition. **Comment faire pour que le programme exécute certaines instructions uniquement lorsque la condition est vraie ?**

C'est le rôle de l'instruction `if` qui signifie en français "si".

### L'instruction `if`

La syntaxe générale est la suivante :

```python
if condition:
    instruction
```

La `condition` est une expression booléenne. Les instructions indentées (décalées de 4 espaces) après le `if` ne sont exécutées que si cette condition vaut `True`.

!!! example "À tester"
    Testez le programme suivant :

    ```python
    age = 17

    if age >= 18:
        print("Vous êtes majeur")
    ```

    Que se passe-t-il si vous remplacez `17` par `20` ?

!!! warning "Attention"
    L'indentation est obligatoire en Python. Il s'agit d'un décalage de 4 espaces qui permet de déterminer quelles instructions appartiennent au bloc conditionnel.

    ```python
    if age >= 18:
        print("Vous êtes majeur")

    Ici, `print()` appartient au bloc du `if`. Cela veut dire qu'il ne s'exécutera que si la condition est vraie.

### `if` et `else`

Avec `if`, il est également possible de prévoir ce que le programme doit faire lorsque la condition est fausse.

On utilise pour cela le mot-clé `else` qui veut dire en français "sinon" :

```python
if condition:
    instruction_si_vrai
else:
    instruction_si_faux
```

!!! example "À tester"
    Complétez puis testez le programme suivant :

    ```python
    age = int(input("Quel âge avez-vous ? "))

    if age >= 18:
        print("Vous êtes majeur")
    else:
        print("Vous êtes mineur")
    ```

    Testez le programme avec plusieurs âges.

    !!! tip "À retenir"
    Une instruction conditionnelle permet à un programme de **choisir quelles instructions exécuter** en fonction du résultat d'une expression booléenne.

    ```python
    if condition:
        # exécuté si la condition est vraie
    else:
        # exécuté si la condition est fausse
    ```


!!! tip "Pause — À vous de jouer"
    **Faites les exercices 5 et 6.**

Une fois les exercices terminés, vous pourrez débuter le TP 1 (à venir)


 






