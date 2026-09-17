# TP — Fonctions et bibliothèque Turtle

## Objectifs

Dans ce TP, nous allons découvrir comment utiliser une bibliothèque Python et utiliser les fonctions d'une bibliothèque dans nos propres fonctions.

À la fin du TP, vous devez être capables de :

* importer une bibliothèque ;
* utiliser une fonction provenant d'une bibliothèque ;
* créer une fonction utilisant une bibliothèque ;
* utiliser des paramètres pour rendre une fonction réutilisable ;
* combiner plusieurs fonctions pour réaliser un dessin.

---

## 1. Découvrir la bibliothèque Turtle

Python possède de nombreuses bibliothèques contenant des fonctions déjà programmées par d'autres utilisateurs dans un but bien spécifique.

Nous allons utiliser la bibliothèque `turtle`. Elle permet de contrôler une tortue virtuelle qui se déplace sur l'écran et dessine lorsqu'elle avance. C'est donc une bibliothèque créee dans le but de pouvoir faire du dessin en Python.

Voici quelques fonctions de la bibliothèque que nous allons utiliser :

| Fonction                    | Rôle                                    | Exemple               |
| --------------------------- | --------------------------------------- | --------------------- |
| `turtle.forward(distance)`  | Avance de `distance` pixels             | `turtle.forward(100)` |
| `turtle.backward(distance)` | Recule de `distance` pixels             | `turtle.backward(50)` |
| `turtle.right(angle)`       | Tourne vers la droite de `angle` degrés | `turtle.right(90)`    |
| `turtle.left(angle)`        | Tourne vers la gauche de `angle` degrés | `turtle.left(45)`     |

### 1.1 Utiliser une bibliothèque

**1.** Créez un nouveau fichier Python et importez la bibliothèque `turtle` en écrivant au début du fichier:

```python
import turtle
```

Lorsque l'on importe une bibliothèque, on écrit toujours `import` suivi du nom de la bibliothèque.

**2.** Utilisez les fonctions `forward()` et `right()` pour faire avancer la tortue et lui faire effectuer plusieurs changements de direction.

---

## 2. Créer une fonction avec Turtle

Nous pouvons utiliser les fonctions de `turtle` dans les fonctions que nous créons nous-mêmes.

### 2.1 Dessiner un carré

Voici une fonction permettant de dessiner un carré :

```python
def carre(cote):
    for i in range(4):
        turtle.forward(cote)
        turtle.right(90)
```

**3.** Recopiez cette fonction et appelez-la avec un côté de 100 pixels.

**4.** Modifiez ensuite l'appel afin de pouvoir dessiner un carré de la taille de votre choix.

**5.** Expliquez en une phrase pourquoi le paramètre `cote` rend cette fonction réutilisable.

---

!!! tip "Pause — À vous de jouer"

À partir de maintenant, vous allez créer vous-mêmes les fonctions permettant de dessiner différentes formes.

---

## 3. Créer des fonctions pour différentes formes

### 3.1 Le triangle

**6.** En utilisant les fonctions de la bibliothèque turtle, écrivez une fonction `triangle(cote)` permettant de dessiner un triangle équilatéral de côté `cote`.

### 3.2 Le rectangle

**7.** En utilisant les fonctions de la bibliothèque turtle, écrivez une fonction `rectangle(longueur, largeur)` permettant de dessiner un rectangle dont les dimensions sont données en paramètres.

---

## 4. Généraliser avec les polygones

Les fonctions `carre()` et `triangle()` sont finalement très similaires : elles dessinent un certain nombre de côtés de même longueur en tournant à chaque fois du même angle.

**8.** Écrivez donc une fonction :

```python
def polygone(nombre_cotes, longueur):
    ...
```

Elle prend en paramètre le nombre de côtés souhaité et leur longueur. Elle doit permettre de dessiner n'importe quel polygone régulier.

**Indice** Il vous faudra déterminer l'expression permettant de calculer l'angle de rotation de la tortue à partir du nombre de côtés.

**10.** Utilisez votre fonction pour dessiner différents polygones.

---

## 5. Combiner les fonctions

Une fois une fonction écrite, nous pouvons l'utiliser autant de fois que nécessaire dans notre programme.

**11.** Réalisez un dessin composé d'au moins trois formes géométriques différentes en utilisant les fonctions que vous avez créées.

Vous ne devez pas recopier les instructions permettant de dessiner les formes : utilisez vos fonctions.

---

## 6. Défi — La maison

Avec les fonctions définies précédemment, il nous est possible de dessiner une maison, il faudra pour cela un carré avec un triangle par dessus et éventuellement un rectangle au dessus pour la cheminée et un autre pour la porte.

**12.** Réalisez donc une fonction `maison` sans paramètre qui réalise une maison aux dimensions de votre choix.

### Défi bonus : 

**13.** Importez la bibliothèque `random` au début de votre fichier. Cette bibliothèque contient des fonctions permettant de générer des valeurs "aléatoires". 

Par exemple, la fonction `random.randint(debut, fin)` génère un entier aléatoire entre les valeurs `debut` et `fin` .

**14.** Mettez à jour votre fonction `maison` pour que les dimensons des éléments de la maison soient générés aléatoirement.

## 7. Défi — La rosace

Nous pouvons également utiliser une boucle pour répéter une forme en faisant tourner la tortue entre chaque répétition.

Par exemple :

```python
for i in range(12):
    carre(100)
    turtle.right(30)
```

**15.** À partir de cet exemple, créez votre propre rosace.

Vous pouvez modifier la forme, sa taille, le nombre de répétitions et l'angle de rotation.

Votre programme devra utiliser au moins une des fonctions que vous avez créées.

---

!!! tip "À retenir"

Une bibliothèque contient des fonctions déjà programmées que nous pouvons utiliser dans nos propres programmes.

Pour utiliser une bibliothèque, on l'importe avec :

```python
import nom_de_la_bibliotheque
```

On peut ensuite utiliser ses fonctions avec :

```python
nom_de_la_bibliotheque.fonction(arguments)
```

Nous pouvons également utiliser les fonctions d'une bibliothèque dans **nos propres fonctions**.

Par exemple :

```python
def carre(cote):
    for i in range(4):
        turtle.forward(cote)
        turtle.right(90)
```

Les bibliothèques permettent ainsi de réutiliser du code déjà écrit et de construire plus facilement des programmes complexes.
