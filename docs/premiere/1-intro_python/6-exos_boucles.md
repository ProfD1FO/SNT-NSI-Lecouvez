# Exercices 3 — Les boucles

## Partie 1 : le range

### Exercice 1 : Les suites de valeurs

Sans testez avec Python, donnez les valeurs produites par les itérables suivants:

1. `range(2, 7)`
2. `range(5, 10)`
3. `range(0, 10, 2)`
4. `range(10, 0, -2)`
5. `range(10)`
6. `range(90, 91)`

Vous pouvez ensuite tester dans la console en faisant `print(list(range(2, 7))` etc....

### Exercice 2 : Fabriquer un range

Écrivez des range permettant d'obtenir les suites de valeurs suivantes :

1. `[0, 1, 2, 3, 4, 5]`
2. `[9, 10, 11, 12, 13]`
3. `[3, 6, 9, 12, 15]`
4. `[12, 11, 10, 9, 8]`
5. `[10, 8, 6, 4, 2, 0]`

### Exercice 3 : Prédire le comportement d'une boucle

Sans utiliser Python, prédire les valeurs de `a` et `b` à la **fin** des programmes suivants, prenez le temps de bien écrire l'évolution des variables sur votre feuille pour ne pas perdre le fil :

1. Premier programme

```python
a = 0
for i in range(0,10) :
    a = a + 2
```

2. Deuxième programme

```python
a = 0
for i in range(0,10) :
    a = a + i
```

3. Troisième programme

```python
a = 0
b = 10
for i in range(5) :
    a = 2**i
	b = b-a
```

### Exercice 4 : Ecrire des boucles simples

1. Ecrivez une boucle qui **affiche** tous les nombres entre 1 et 100.

Exemple :

```text
1
2
3
4
...
```

2. Ecrivez une boucle qui affiche les résultats de la table de 9  de 0 × 9 jusque 10 × 9 . 

Exemple :

```text
0
9
18
27
...
```

3. Écrivez une boucle qui affiche les carrés des nombres de 1 à 10 .

Exemple :

```text
1
4
9
16
...
```