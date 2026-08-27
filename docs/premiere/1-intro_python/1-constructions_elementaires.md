# Cours 1 : Constructions élémentaires

Le Python est un **langage** de programmation, comme pour n'importe quel langage, il dispose de différentes **constructions élémentaires** permettant de rédiger des programmes.

## Objectifs

À la fin du chapitre, vous devez être capable de :

- utiliser des variables ;
- reconnaître les principaux types de données ;
- écrire des expressions simples en Python ;
- utiliser `print()` et `input()` ;
- écrire un programme simple.

## La séquence

En python, les instructions sont lues *ligne par ligne dans l'ordre*, on appelle ça une **séquence**. Lorsque vous écrirez des programmes, il vous suffira donc de passer à la ligne pour écrire la prochaine instruction.

!!! example "À tester"
    Que va afficher le programme suivant ?

    ```python
    print("Bonjour")
    print("Comment allez-vous ?")
    print("Au revoir")
    ```

## L'affectation

L'affectation est une opération essentielle dans tous les langages de programmation. Elle permet d'associer à une variable une valeur d'un certain type. Le nom de la variable choisi est libre mais il vaut mieux s'assurer de prendre un nom qui évoque le contenu de celle-ci.

!!! tip "À retenir"
    Une variable associe un nom à une valeur.

    En Python, l'affectation s'effectue avec `=`.

!!! example "À tester"
    Que vaut le contenu de la variable `annee` après l'exécution suivante ?

    ```python
    annee = 2024
    annee = annee + 2
    ```

!!! warning "Attention"
    En programmation, `=` ne signifie pas juste « est égal à ».

    L'instruction

    ```python
    annee = annee + 2
    ```
    
    signifie que l'on calcule la valeur de `annee + 2`, puis que l'on affecte le résultat à `annee`.

## Les types

Les valeurs manipulées par un programme peuvent être différentes en fonction des besoins. On a par exemple souvent besoin de manipuler des nombres entiers ou des mots. On appelle **type** la catégorie à laquelle appartient une valeur.

En Python, il existe plusieurs types de base : 

### Les entiers (int)

En python le type entier ou (int) correspond aux nombres entiers. Par exemple:
```python
age = 25
annee = 2026
```

### Les flottants (float)

Le type flottant (ou float) permet de représenter les nombres décimaux (à virgule). La virgule est ici remplacée par un point. Par exemple :

```python
prix = 12.50
temperature = 21.5
```

!!! warning "Attention"
    En python, les flottants donnent parfois des résutats inattendus, par exemple, vous verrez que `0.1 + 0.2 != 0.3` . Nous expliquerons ce comportement dans un futur chapitre.

### Les chaînes de caractères (str)

Le type chaîne de caractères (ou str) permet de représenter des caractères, mots ou phrases. Par exemple :

```python
nom = "Alice"
message = "Bonjour !"
```

!!! tip "À retenir"
    En python, les chaînes de caractères sont **toujours** entourées de guillemets simples (`'`) ou doubles (`"`).

### Les booléens (bool)

Ce type est assez particulier puisqu'il ne peut prendre que deux valeurs : 

```python
True
False
```

Elles correspondent respectivement à Vrai et Faux. C'est un type très utile, en particulier lorsque l'on utilise des conditions (voir le prochain cours). 

## Expressions arithmétiques

Les programmes sont avant tout là pour effectuer des calculs, il est donc nécessaire de pouvoir utiliser les opérations de base en python. Vous connaissez déjà la majorité d'entre elles donc résumons-les dans le tableau suivant:

| Opérateur | Opération                    | Exemple  |   Résultat |
| --------- | ---------------------------- | -------- | ---------: |
| `+`       | Addition                     | `7 + 3`  |       `10` |
| `-`       | Soustraction                 | `7 - 3`  |        `4` |
| `*`       | Multiplication               | `7 * 3`  |       `21` |
| `**`      | Puissance                    | `7 ** 3` |      `343` |
| `/`       | Division                     | `7 / 3`  | `2.333...` |
| `//`      | Division entière             | `7 // 3` |        `2` |
| `%`       | Reste de la division entière | `7 % 3`  |        `1` |

!!! tip "À retenir"
    Pour la division il y a donc trois opérateurs, un pour division classique avec `/`, un pour le quotient de la division avec `//` et un pour le reste avec `%`. En fonction des situations, il vous faudra régulièrement utiliser les trois.


