# Cours 3 : Les boucles

Avec ce qui a été vu précédemment, nous sommes déjà capables de construire des petits programmes intéressants. Cependant, nous rencontrons rapidement une limite : lorsque nous voulons effectuer plusieurs fois la même opération, nous devons pour l'instant répéter nous-mêmes les instructions dans le programme.

C'est là qu'intervient une autre construction élémentaire des langages de programmation : **les boucles**. Elles permettent de répéter un bloc d'instructions plusieurs fois sans avoir à le réecrire. Elles se divisent en deux types de boucles :

## Les boucles bornées

Les boucles bornées sont un type de boucle très utile lorsque l'on connaît déjà le nombre de répétitions souhaitées.

En Python, on utlise le mot clé `for` suivi d'un **itérable**. Nous allons voir ce qu'est un itérable:

!!! tip "À retenir" 
    Un itérable est un ensemble de valeurs que l'on peut parcourir **une par une** . On parle d'**itérer** sur les valeurs de l'ensemble.
	
### Le range Python

En Python, on peut construire un itérable très facilement avec la fonction `range()`. Elle prend une borne de début et une borne de fin et permet de construire la suite des nombres entiers compris entre les deux bornes.

Sa forme la plus simple est : `range(debut, fin)`

Prenons des exemples : 

`range(1, 5)` correspond aux valeurs : 1, 2, 3, 4

`range(87, 94)` correspond aux valeurs : 87, 88, 89, 90, 91, 92, 93

!!! warning "Attention"
    La borne de fin est **exclue**. Dans les exemples du dessus, le 5 et le 94 ne font pas partie des ensembles de valeurs.

!!! example "À tester"
	Testez les expressions suivantes dans la console (ne faites pas attention au `list` pour le moment, nous verrons ça plus tard):
	
	```python 
	>>> list(range(1, 5)) 
	>>> list(range(3, 8)) 
	>>> list(range(0, 10))
	>>> list(range(5))
	```
	
On peut également préciser un pas, c'est-à-dire la valeur ajoutée à chaque étape :

`range(debut, fin, pas)`

!!! example "À tester"
	Que donnent les expressions suivantes ?

	```python
	>>> list(range(0, 10, 2))
	>>> list(range(1, 10, 2))
	>>> list(range(10, 0, -1))
	```
	
!!! tip "Pause — À vous de jouer"
    **Faites les exercices 1 et 2 de la fiche d'exercices 3.**
	
### La boucle `for`

Nous savons maintenant construire une suite de nombres avec `range()`.

Mais pour l'instant, nous ne savons pas encore utiliser les valeurs de cette suite. La boucle `for` va permettre de **parcourir les valeurs de l'itérable une par une** et d'exécuter un bloc d'instructions pour chacune d'elles.

Prenons un premier exemple :

!!! example "À tester"
	Que donne le programme suivant ?

	```python
	for nombre in range(1, 6):
		print(nombre)
	```

La boucle fonctionne de la manière suivante :

1. `nombre` prend la valeur `1` ;
2. le bloc d'instructions est exécuté : `print(nombre)` affiche `1` ;
3. `nombre` prend ensuite la valeur `2` ;
4. le bloc est à nouveau exécuté ;
5. et ainsi de suite jusqu'à la dernière valeur de `range(1, 6)`.

Il y a donc **autant de répétitions que de valeurs dans l'itérable**.

Ici, `range(1, 6)` contient 5 valeurs : la boucle est donc exécutée **5 fois**.

On peut traduire le code précédent en français par :

```text
Pour chaque valeur de 1 à 6 exclu :
    placer cette valeur dans la variable nombre
    afficher nombre
```


!!! tip "À retenir"
	La variable `nombre` est une **variable de boucle**.

	Elle prend automatiquement, à chaque tour de boucle, la valeur suivante de l'itérable.

	Cette variable peut être utilisée dans le bloc d'instructions comme n'importe quelle autre variable.


#### La syntaxe

La syntaxe générale d'une boucle `for` est :

```python
for <variable> in <itérable>:
    <bloc d'instructions à répéter>
```

* `for` signifie **« pour »** ;
* `<variable>` est la **variable de boucle** ;
* `in` indique que l'on parcourt l'itérable ;
* `<itérable>` contient les valeurs qui vont être parcourues ;
* le bloc indenté est exécuté **une fois pour chaque valeur de l'itérable**.

!!! warning "Attention"
	Le bloc d'instructions à répéter est **toujours** écarté de 4 espaces comme pour les conditions. On appelle ça une **indentation**.

Le nom de la variable de boucle est choisi par le programmeur, on choisit souvent i car cela signifie "indice" mais ce n'est pas obligatoire. Par exemple, ces deux programmes fonctionnent de la même manière :

```python
for nombre in range(1, 6):
    print(nombre)
```

```python
for i in range(1, 6):
    print(i)
```

La variable de boucle est importante car elle permet d'utiliser **la valeur du tour actuel** dans les instructions répétées.

!!! example "À tester"
	Observez la différence entre les deux programmes suivants :

	```python
	for i in range(5):
		print("Bonjour")
	```

	et

	```python
	for i in range(5):
		print(i ** 2)
	```

	Dans le deuxième programme, la valeur de `i` est utilisée pour calculer son carré à chaque tour. Dans le premier, la variable `i` n'est pas utilisée.

!!! tip "À retenir"
	Pour conclure, une boucle `for` permet donc de :

	- parcourir les valeurs d'un itérable ;
	- répéter un bloc d'instructions **une fois par valeur** ;
	- utiliser la variable de boucle pour accéder à la valeur du tour actuel.

!!! tip "Pause — À vous de jouer"
	Faites les exercices 3 et 4 de la fiche associée.