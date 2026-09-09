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

## Partie 2 : le for

### Exercice 3 : Prédire le comportement d'une boucle

Sans utiliser Python, prédire les valeurs de `a` et `b` à la **fin** des programmes suivants, prenez le temps de bien écrire l'évolution des variables sur votre feuille pour ne pas perdre le fil :

- Premier programme

```python
a = 0
for i in range(0,10) :
    a = a + 2
```

- Deuxième programme

```python
a = 0
for i in range(0,10) :
    a = a + i
```

- Troisième programme

```python
a = 0
b = 10
for i in range(5) :
    a = 2**i
	b = b-a
```

### Exercice 4 : Ecrire des boucles simples

- Ecrivez une boucle qui **affiche** tous les nombres entre 1 et 100.

	Exemple :

	```text
	1
	2
	3
	4
	...
	```

- Ecrivez une boucle qui affiche les résultats de la table de 9  de 0 × 9 jusque 10 × 9 . 

	Exemple :

	```text
	0
	9
	18
	27
	...
	```

- Écrivez une boucle qui affiche les carrés des nombres de 1 à 10 .

	Exemple :

	```text
	1
	4
	9
	16
	...
	```
	

## Partie 3 : le while

### Exercice 5 — Que va afficher ce programme ?

Sans exécuter le programme, indiquez ce qu'il va afficher.

```python
nombre = 100

while nombre > 0:
    print(nombre)
    nombre = nombre // 2
```

### Exercice 6 — Combien de tickets ?

Un billet de cinéma coûte 8 €. On dispose de 50 €.

Le programme ci-dessous permet de calculer le nombre de billets achetables selon l'argent de départ :

```python
argent = 50
billets = 0

while argent >= 8:
    argent = argent - 8
    billets = billets + 1
```

Sans tester avec Python, quelle valeur contient la variable `billets` à la fin du programme ?

### Exercice 7 - L'épargne

On place 100 € sur un compte. Chaque mois, on ajoute 25 €.

Écrivez un programme qui détermine au bout de combien de mois l'épargne atteint au moins 500 €.

Vous devez obtenir le résultat dans une variable mois et vous aurez également besoin d'une variable pour l'argent.