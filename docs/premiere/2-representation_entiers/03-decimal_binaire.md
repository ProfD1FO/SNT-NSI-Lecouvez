# Cours 2 - Passer du décimal au binaire

Dans le cours précédent, vous avez découvert les bases de nombres, en particulier la base 2 qui est utilisée dans nos ordinateurs. 

Connaître l'écriture décimal d'un entier en base 2 est très facile, il suffit de décomposer comme nous l'avons fait précédemment. Néanmoins, l'opération inverse est plus complexe, comment passer efficacement du décimal au binaire?

## La méthode de la décomposition

La méthode la plus rapide et simpliste est celle de la décomposition. On va tout simplement décomposer la valeur à convertir dans la base souhaitée pour pouvoir écrire le nombre.

Prenons un exemple en essayant d'écrire 26 en binaire. Pour cela, je vais le décomposer en puissance de 2 :

Je sais que $ 26 = 16 + 8 + 2 $

Cela est égal à $1\times2^4 + 1\times2^3 + 0\times2^2 + 1\times2^1 + 0\times2^0$ 

Donc en binaire mon nombre s'écrira : $11010_2$

### L'avantage 

Cette méthode est simple et très rapide lorsque l'on connaît ses puissances de deux par coeur et que l'on aime faire des calculs de tête. Elle est particulièrement adaptée lorsqu'il faut convertir de petites valeurs.

### Le problème

Premièrement, si vous avez du mal à calculer de tête et que vous écrivez tout, vous ne gagnerez pas vraiment de temps dans vos calculs. De plus, cette méthode nécessite de bien connaître les puissances de deux et de bien les manipuler, une erreur faussera tout le calcul.

De plus, décomposer un très grand nombre en puissance de deux devient pratiquement impossible : imaginez devoir convertir $10729$ juste en décomposant de tête....

On a donc besoin d'une méthode qui marchera à tous les coups et sans poser de difficultés particulières. Cette méthode existe et s'appelle **divisions par deux successives**.

## La méthode des divisions par deux successives

Cette méthode repose sur un principe simple : **diviser successivement le nombre par 2 et conserver les restes obtenus**.

Prenons à nouveau le nombre $26$. On effectue une première division euclidienne par $2$ :

$$
26 = 2\times13 + \mathbf{0}
$$

On recommence ensuite avec le quotient obtenu, c'est-à-dire $13$ :

$$
13 = 2\times6 + \mathbf{1}
$$

Puis on continue avec les quotients successifs :

$$
\begin{array}{rcl}
26 &=& 2\times13 + \mathbf{0}\\
13 &=& 2\times6 + \mathbf{1}\\
6  &=& 2\times3 + \mathbf{0}\\
3  &=& 2\times1 + \mathbf{1}\\
1  &=& 2\times0 + \mathbf{1}
\end{array}
$$

On s'arrête lorsque le quotient vaut $0$.

!!! warning "attention"
    En général lorsque l'on rédige la méthode, on utilise les divisions posées (comme à l'école primaire). Inspirez-vous des exemples au tableau.

### Lire les restes

Les restes obtenus sont :

$$
0\quad1\quad0\quad1\quad1
$$

Il faut cependant les lire **dans l'ordre inverse** :

$$
\boxed{1\quad1\quad0\quad1\quad0}
$$

On obtient donc :

$$
\boxed{26_{10}=11010_2}
$$

Mais pourquoi faut-il lire les restes à l'envers ?

Lors de la première division, le reste est nécessairement $0$ ou $1$. Il correspond au coefficient de $2^0$ dans l'écriture binaire.

Lors de la deuxième division, le nouveau reste correspond au coefficient de $2^1$, puis le suivant à celui de $2^2$, et ainsi de suite.

Les restes sont donc obtenus **du bit de droite vers le bit de gauche**. C'est pour cette raison qu'on doit les lire de bas en haut.

### Avantages

Cette méthode marche à tous les coups, si vous êtes concentrés et faites vos divisions par 2 correctement, cette méthode est inratable et ne nécessite pas de bien connaître ses puissances de deux (bien que ce soit utile pour vérifier son résultat)

Lorsque l'on a à faire à des très grandes valeurs à convertir, cette méthode s'avère terriblement plus efficace qu'une décomposition bien que cela puisse être très long.

Cette méthode correspond a un algorithme ce qui veut dire que nous allons pouvoir la programmer avec Python !

### Problème

Poser des divisions est parfois assez long, surtout pour des valeurs petites qui ne nécessitaient pas forcément son utilisation


!!! example "À tester"
    Convertissez $57$ en binaire en utilisant la méthode des divisions successives par $2$.


## Vérifier son résultat

Une erreur de calcul est vite arrivée, même avec la méthode précédente. Il fait donc vérifier son résultat et pour cela c'est très facile, il vous suffit de reconvertir dans l'autre sens comme dans le cours précédent.

Par exemple si nous avions trouvé le résultat $11110_2$ en convertissant $26$, il est possible de le décomposer et vérifier si le résultat correspond. Ici on a :

$1\times2^4 + 1\times2^3 + 1\times2^2 + 1\times2^1 +0\times2^0 = 28$

Le résultat ne correspond pas à 26 donc vous savez que ce résultat est une erreur.

!!! tip "À retenir" 
    Il est nécessaire de toujours vérifier ses calculs lorsque l'on convertit d'une base à une autre en reconvertissant dans l'autre sens.

