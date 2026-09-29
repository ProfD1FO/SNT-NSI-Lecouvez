# Exercices 2 - Passer en binaire

## Exercice 1 - Décomposition:

### Q1 - Rappeler sur votre feuille toutes les puissances de $2^0$ à $2^8$

### Q2 - Pour chacun des nombres suivants, donner sa décomposition en **puissance de 2**.

- 11
- 35
- 81
- 201
- 404

### Q3 - Une fois cela fait, en utilisant les résultats précédents donner la représentation en binaire des 5 nombres.


## Exercice 2 - Divisions par 2 successives:

## Q1 - En utilisant la méthode des divisions par 2 successives, donner la représentation binaire des nombres suivants :

- 66
- 139
- 417
- 6131
- 10000

## Q2 - Vérifier chacun de vos résultats précédents en les repassant en base 10.

## Exercice 3 : Programmation de la méthode

Comme dit dans le cours, l'avantage de cette méthode est qu'il s'agit d'un algorithme très facile à implémenter en Python. Voici l'idée de l'algorithme en français (aussi appelé pseudo-code).

```
Tant que nombre n'est pas à 0 :
    On stocke le reste de la division euclidienne par 2 de nombre
    nombre <- quotient de la division euclidienne par 2 de nombre
on affiche les restes stockées à l'envers
```

En vous aidant de ce code, programmez une fonction `divisions_par_2` qui prendre en paramètre un entier `nombre` et qui renverra la représentation binaire de nombre **sous forme de chaîne de caractères (str)**.

Voici des exemples d'utilisation :

```python
>>> divisions_par_2(20)
"10100"

>>> divisions_par_2(2)
"10"
```
