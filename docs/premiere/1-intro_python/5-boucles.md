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
	
## Les boucles non bornées

Le deuxième type de boucle, appelé "boucle non bornée", est utile lorsque l'on ne sait pas à l'avance le nombre de répétitions à faire.

### Fonctionnement du while et exemple

En Python, on utilise le mot clé `while` suivi d'une expression booléenne (voir cours précédent). En français, while signifie "tant que" ce qui prend tout son sens lorsqu'il est suivi d'une condition.

!!! example "À tester"
	Voici un premier exemple:
	
	```python
	nombre = 5
	while nombre > 0:
		print(nombre)
		nombre = nombre - 1
	```
	
Ce code peut se traduire littéralement par :

```text
nombre = 5
Tant que nombre est strictement supérieur à 0 :
	afficher nombre
	enlever 1 à nombre
```

Le fonctionnement est le suivant :

1. `nombre` vaut `5`.
2. Python vérifie si `nombre > 0`. La condition est vraie.
3. Le bloc d'instructions est exécuté : `5` est affiché, puis `1` est retiré à `nombre`.
4. Python vérifie à nouveau la condition.
5. La boucle continue tant que la condition est vraie.
6. Lorsque `nombre` vaut `0`, la condition `nombre > 0` devient fausse : la boucle s'arrête.

!!! tip "À retenir"
    Une boucle `while` répète un bloc d'instructions **tant qu'une condition est vraie**.

    Contrairement à une boucle `for`, on ne connaît pas nécessairement à l'avance le nombre de répétitions.
	
### Attention aux boucles infinies

Regardons maintenant ce qui se passe si on oublie de modifier `nombre` dans le programme précédent:

!!! example "À tester"
    ```python
    nombre = 5

    while nombre > 0:
        print(nombre)
    ```

    Que va faire ce programme ?
	
!!! warning "Attention"
	Dans les boucles `while`, il faut faire très attention à la condition. En effet, il faut s'assurer qu'elle puisse **devenir fausse** à un moment donné.

	Dans l'exemple précédent, la variable `nombre` n'est jamais modifiée. Elle vaut donc toujours `5` et la condition `nombre > 0` reste toujours vraie.

	La boucle continue alors indéfiniment : on parle de **boucle infinie**.

Pour éviter cela, il faut généralement qu'une ou plusieurs variables utilisées dans la condition évoluent au cours de la boucle.

Dans notre premier exemple, `nombre` évoluait à chaque répétition :

```text
5 → 4 → 3 → 2 → 1 → 0
```

Lorsque `nombre` atteint `0`, la condition `nombre > 0` devient fausse et la boucle s'arrête.

On appelle **variant** une variable qui évolue au cours des répétitions d'une boucle et qui permet à la boucle de progresser vers sa fin.

!!! tip "À retenir"
	Dans une boucle `while`, il faut vérifier que la condition puisse devenir fausse.
	
	Une variable utilisée dans cette condition peut servir de **variant** et varier au cours de la boucle pour qu'elle se termine.


### L'intérêt du while

L'intérêt principal d'une boucle `while` apparaît lorsque l'on ne peut pas connaître à l'avance le nombre de répétitions nécessaires.

Par exemple, on peut demander à un utilisateur de saisir un mot de passe jusqu'à ce qu'il soit correct :

!!! example "À tester"
	```python
	mot = input("Mot de passe : ")

	while mot != "NSI":
		print("Mot de passe incorrect.")
		mot = input("Réessayez : ")

	print("Bienvenue !")
	```

Ici, on ne sait pas à l'avance combien de fois l'utilisateur va saisir un mauvais mot de passe.

* S'il saisit directement `NSI`, la boucle ne s'exécute pas.
* S'il se trompe une fois, la boucle s'exécute une fois et redemande un mot à l'utilisateur.
* S'il se trompe plusieurs fois, la boucle s'exécute à nouveau jusqu'à ce qu'il saisisse `NSI`.

Le nombre de répétitions dépend donc de la situation rencontrée pendant l'exécution du programme.

!!! tip "À retenir"
	Une boucle `while` est particulièrement adaptée lorsque le nombre de répétitions **dépend d'une condition** et n'est pas connu à l'avance.

### La syntaxe

La syntaxe générale d'une boucle `while` est :

```python
while <condition>:
    <bloc d'instructions à répéter>
```

* `while` signifie **« tant que »** ;
* `<condition>` est une expression booléenne ;
* le bloc indenté est exécuté tant que la condition est vraie.

!!! tip "Pause — À vous de jouer"
	Faites les exercices 5, 6 et 7.
