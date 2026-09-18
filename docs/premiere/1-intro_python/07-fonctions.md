# Cours 4 - Les fonctions

Pour conclure ce premier chapitre sur les constructions élémentaires, il ne nous en manque qu'une seule. Ce n'est certainement pas la plus difficile mais c'est l'une des plus essentielles lorsque l'on programme.

Jusqu'à présent, lorsque vous programmiez, tous vos programmes et exercices apparaissaient dans le même fichier et s'exécutaient tous un par un dès que vous exécutiez le programme. Ce comportement n'est pas souhaitable : chaque programme ne doit pas nécessairement tout exécuter à chaque lancement.

Nous avons donc besoin d'une dernière construction pour conserver nos programmes et ainsi avoir un code plus clair et lisible, c'est là tout l'intérêt des **fonctions**.

## Partie 1 - Premières fonctions et syntaxe

Une fonction est simplement un bloc de code auquel on donne un nom afin de pouvoir l'appeler quand on le souhaite et avec les valeurs de notre choix. Voyons d'abord un exemple :

!!! example "À tester"
	Dans un premier temps, écrivez dans votre éditeur de code :

	```python
	def f(x):
		return x+12
	```

	Exécutez ce programme dans un premier temps, se passe-t-il quelque chose ?

	Maintenant écrivez dans la console :

	```python
	>>> f(10)
	```

	Ensuite essayez :

	```python
	>>> f(34)
	```

	Qu'est-ce qui se passe à chaque fois ?

Ce que vous venez de tester est le cœur même des fonctions, il y a plusieurs choses à expliquer :

### La définition

Pour fabriquer une fonction, on utilise en Python le mot-clé `def` suivi du nom que l'on souhaite lui donner. Dans l'exemple précédent, j'ai choisi de l'appeler `f` pour faire référence aux fonctions mathématiques.

### Les paramètres

Les paramètres sont des variables qui reçoivent une valeur lors de **l'appel** de la fonction. On écrit leur nom dans des **parenthèses** juste après le nom de la fonction. Il est possible de mettre plusieurs paramètres séparés par des virgules.

### Le bloc de code

Une fois les paramètres prêts et la parenthèse fermée, il ne faut surtout pas oublier les `:` à la fin de la ligne. Ensuite, tout le code indenté de 4 espaces après cette première ligne appartiendra à la fonction. Cela fonctionne comme pour les conditions ou les boucles.

### Le retour de la fonction

Jusqu'ici, on utilisait principalement `print` pour afficher les résultats des programmes. Mais dans les fonctions, on évitera de les utiliser. Pour renvoyer une valeur dans une fonction, on utilise le mot-clé `return` suivi de la valeur à renvoyer. Cette valeur pourra être stockée dans une variable lors de **l'appel** ou simplement affichée dans la console.

### L'appel de la fonction

Comme vous l'avez vu, lorsque l'on exécute le programme qui contient une fonction, rien ne se passe. C'est normal, la fonction attend d'être **appelée** pour s'exécuter. Il est bien entendu possible de l'appeler depuis l'éditeur de code mais également depuis la console, ce qui est très pratique lorsque l'on souhaite la tester. Pour appeler une fonction, il suffit d'écrire son nom suivi de parenthèses contenant des **arguments**.

Les **arguments** sont simplement les valeurs que vous souhaitez attribuer aux **paramètres** lors de l'appel. Dans notre exemple précédent, le seul paramètre était la variable `x`. Dans le premier appel, l'argument correspondant à `x` était `10` et dans le deuxième, c'était `34`.

---

!!! example "À tester"
	Maintenant que vous avez la théorie, retentons une autre fonction. Dans votre éditeur de code, écrivez :

	```python
	def somme(a, b):
		return a+b
	```

D'après vous, que va faire cette fonction ? Essayez de l'appeler avec les arguments `6` et `14`.

!!! tip "À retenir"
	Récapitulons la syntaxe et le vocabulaire des fonctions en Python :

	```python
	def ma_fonction(paramètre1,......):
		......
		return ......
	```

	- La première ligne, aussi appelée **signature**, est composée du mot-clé `def` suivi du nom de la fonction et des paramètres utiles au code de la fonction dans des parenthèses.

	- Les paramètres sont les variables qui contiendront les valeurs nécessaires au fonctionnement de la fonction.

	- Le mot-clé `return` permet de renvoyer une valeur calculée dans la fonction. NB : Toutes les fonctions ne renvoient pas nécessairement quelque chose, ainsi le `return` n'est pas un élément obligatoire.

	Pour appeler une fonction, il suffit d'écrire :

	```python
	ma_fonction(argument1,......)
	```

	- On met d'abord le nom de la fonction que l'on souhaite utiliser.

	- Ensuite, on met des parenthèses contenant des arguments : les **valeurs** que l'on souhaite associer aux paramètres. On les met dans le même ordre que les paramètres.

!!! tip "Pause - à vous de jouer"
	Faites les exercices 1, 2 et 3 de la fiche d'exercices 4.

## Des fonctions qui utilisent des fonctions

En plus de permettre une meilleure organisation, l'intérêt principal des fonctions est leur **réutilisation**. En effet, une fois qu'une fonction est écrite, n'importe quelle autre fonction ou programme aura l'occasion de s'en servir. D'ailleurs, c'est déjà ce que l'on fait très régulièrement lorsque l'on utilise `print` et `input`. En effet, ces deux éléments sont des fonctions qui prennent en argument des chaînes de caractères.

!!! example "À tester"
	Recopiez et exécutez le programme ci-dessous :

	```python
	def f(x):
		return 3*x + 12

	def g(y):
		a = f(y)
		return a + y
	```

	Appelez la fonction `g` avec l'argument `10`. Quel résultat obtenez-vous ?


Dans l'exemple plus haut, la fonction nommée `g` appelle la fonction nommée `f` et stocke son résultat dans la variable `a`. C'est une utilisation courante des fonctions qui permet de diviser les tâches.

!!! tip "À retenir"
	Une fonction peut donc utiliser le résultat d'une autre fonction comme n'importe quelle autre valeur. Cela permet de construire des programmes plus complexes en combinant plusieurs fonctions simples. C'est le coeur de la programmation.
	



