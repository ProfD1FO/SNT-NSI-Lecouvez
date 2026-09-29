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