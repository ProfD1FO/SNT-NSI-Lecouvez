# Cours 3 : Représentation des entiers relatifs en binaire

Nous avons vu comment passer de la base 10 à la base 2 et inversement pour les entiers positifs. Néanmoins, les entiers ne sont pas tous positifs, ils peuvent être négatifs et il faut donc pouvoir représenter ces entiers.

## Une première méthode inefficace : le signe + valeur absolue

La première idée est d'une grande simplicité, on va ajouter un bit au début de la représentation binaire pour le signe, 1 si c'est négatif et 0 sinon. Pour le reste, on va juste convertir la valeur comme d'habitude. 

Par exemple, si je veux représenter -33 en binaire :

Je sais que $33 = 100001_2$ . Comme le nombre est négatif, j'ajouté un 1 au début et j'obtiens $-33 = 1100001_2$

!!! warning "Attention!" 
    Pour que la conversion des nombres ait un sens, il est essentiel de définir par avance sur combien de bits on travaille. En général, on travaille sur des tailles qui sont des multiples de 8.
    Par exemple, je décide de convertir -33 en binaire sur 8 bits :
    Je sais que $33=00100001_2$ sur 8 bits donc $-33=10100001_2$ . On voit ici que c'est toujours le bit le plus à gauche pour le signe!

### Le problème de cette méthode

Aujourd'hui, aucun ordinateur n'utilise cette méthode pour les entiers négatifs et la raison est simple : 
**cette méthode casse le fonctionnement de l'addition entre entiers positif et négatif**. Je m'explique :

On sait tous que $33 + (-33) = 0$ , c'est le fonctionnement normal de l'addition. Mais lorsque l'on fait cette même addition avec les représentations binaires sur 8 bits cela donne :

$00100001_2 + 10100001_2$, si on pose rapidement ce calcul, on obtient : $11000010_2$ et ce nombre en binaire avec cette méthode représente -66 ce qui est bien loin du 0 souhaité. 

Il est trop problématique d'utiliser une représentation qui briserait l'addition. En effet, nos ordinateurs rateraient même les calculs les plus simples. On va donc préférer ignorer cette méthode et en utiliser une plus complexe mais fonctionnelle :

## Le complément à deux

Le problème que nous venons de rencontrer vient du fait que le bit de signe est complètement séparé de la valeur du nombre. L'ordinateur doit donc traiter différemment les nombres positifs et les nombres négatifs lorsqu'il effectue une addition.

L'idée du **complément à deux** est justement de trouver une représentation qui permette de faire fonctionner les additions de la même manière, que les nombres soient positifs ou négatifs.

### Comment représenter un nombre négatif ?

Pour obtenir la représentation en complément à deux d'un nombre négatif, on va procéder en deux étapes :

1. écrire la valeur positive du nombre en binaire sur le nombre de bits choisi ;
2. **inverser tous les bits**, puis **ajouter 1**.

Reprenons notre exemple de $-33$ sur 8 bits.

On commence par écrire $33$ :

$$
33 = 00100001_2
$$

On inverse ensuite tous les bits : les $0$ deviennent des $1$ et les $1$ deviennent des $0$.

$$
00100001
\quad\longrightarrow\quad
11011110
$$

Enfin, on ajoute $1$ :

$$
11011110 + 1 = 11011111
$$

Ainsi, sur 8 bits :

$$
\boxed{-33 = 11011111_2}
$$

!!! note "À retenir"
	Pour représenter un entier négatif en complément à deux, on utilise toujours la même recette :

	```
	**1.** Écrire sa valeur absolue en binaire.  
	**2.** Inverser tous les bits.  
	**3.** Ajouter $1$.
	```

### Vérifions que cela fonctionne

Maintenant que nous avons une représentation de $-33$, vérifions si notre problème d'addition a été résolu.

Nous avons :

$$
33 = 00100001_2
$$

et :

$$
-33 = 11011111_2
$$

Effectuons l'addition :

$$
\begin{array}{r}
00100001\\
+11011111\\
\hline
1\,00000000
\end{array}
$$

Nous obtenons un résultat sur **9 bits**. Or nous avons décidé de travailler sur 8 bits : le neuvième bit, tout à gauche, est donc simplement ignoré.

Il reste :

$$
\boxed{00000000_2}
$$

On retrouve bien :

$$
33+(-33)=0
$$

!!! success "Ça marche !"
	Contrairement à la représentation signe + valeur absolue, le complément à deux permet d'utiliser directement les mêmes additions binaires pour les nombres positifs et négatifs.

	C'est pour cette raison que c'est cette représentation qui est utilisée par les ordinateurs pour manipuler les entiers relatifs.

## Mais comment savoir quel nombre représente un binaire ?

Avec les entiers positifs, la conversion est simple : on utilise les puissances de $2$ comme nous l'avons vu précédemment.

Avec les entiers relatifs en complément à deux, il faut d'abord regarder **le bit le plus à gauche**.

* S'il vaut $0$, le nombre est positif et on peut le convertir normalement comme avant.
* S'il vaut $1$, le nombre est négatif et il faut retrouver sa valeur en faisant la méthode inverse du complément à deux.

Prenons par exemple :

$$
11011111_2
$$

Le premier bit vaut $1$, le nombre est donc négatif.

Pour retrouver sa valeur, on effectue l'opération inverse de celle utilisée pour le créer.

On commence par retirer $1$ :

$$
11011111 - 1 = 11011110
$$

Puis on inverse tous les bits :

$$
11011110
\quad\longrightarrow\quad
00100001
$$

On reconnaît alors :

$$
00100001_2 = 33
$$

Le nombre représenté était donc :

$$
\boxed{-33}
$$

### Une autre façon de le voir

Il existe une petite astuce pour aller plus vite : lorsqu'un nombre est négatif, on peut **inverser les bits puis ajouter 1**, exactement comme lors de la conversion vers le complément à deux.

Par exemple :

$$
11011111
$$

On inverse les bits :

$$
00100000
$$

Puis on ajoute $1$ :

$$
00100000+1=00100001
$$

On obtient $33$, donc le nombre de départ était $-33$.

## Combien de nombres peut-on représenter ?

Nous avons vu qu'il est indispensable de choisir à l'avance le nombre de bits utilisé.

Sur **8 bits**, il existe :

$$
2^8 = 256
$$

combinaisons différentes de bits.

On peut donc représenter **256 nombres différents**.

Avec le complément à deux, ces nombres vont de :

$$
\boxed{-128\text{ à }127}
$$

On remarque qu'il y a un nombre négatif de plus que de nombres positifs.

En général, avec $n$ bits, l'intervalle des entiers représentables est :

$$
\boxed{-2^{n-1}\leq x\leq2^{n-1}-1}
$$

Par exemple :

| Nombre de bits |  Minimum | Maximum |
| -------------: | -------: | ------: |
|              4 |     $-8$ |     $7$ |
|              8 |   $-128$ |   $127$ |
|             16 | $-32768$ | $32767$ |

!!! warning "Attention !"
	Le nombre de bits est encore plus essentiel lorsque l'on utilise le complément à deux.

	```
	Par exemple, la représentation de $-33$ n'est pas la même sur 8 bits et sur 16 bits :

	\[
	-33 = 11011111_2 \quad\text{sur 8 bits}
	\]

	tandis que :

	\[
	-33 = 1111111111011111_2 \quad\text{sur 16 bits}
	\]

	On conserve toujours la même valeur, mais on ajoute des $1$ à gauche lorsque l'on augmente la taille de la représentation.
```
