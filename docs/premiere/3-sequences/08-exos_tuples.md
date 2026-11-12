# Exercices 3: Les tuples

## Exercice 1 - Tuple ou liste ?

Pour chacune des situations suivantes, indiquez si il vaut mieux utiliser une liste ou un tuple Python pour les stocker. Justifiez votre réponse par une phrase courte.

1. Les notes d'un élève durant un trimestre.
2. Les coordonnées géographiques d'une ville (latitude et longitude).
3. Une paire de prénoms qui représente un binôme en classe.
4. La couleur (format rvb) d'un pixel.
5. Les élèves présents dans une salle de classe.

## Exercice 2 - Manipuler un tuple 

Un programme stocke les coordonnées de plusieurs points dans des tuples :

```python
point_A = (3, 5)
point_B = (7, 2)
point_C = (-1, 4)
```

Sur Python, écrivez les instructions suivantes :

1. Affichez l'abscisse du point A.
2. Affichez l'ordonnée du point B.
3. Créez deux variables x et y contenant respectivement l'abscisse et l'ordonnée du point C.
4. Calculez et affichez la somme des coordonnées du point A.
5. Peut-on remplacer l'abscisse du point A par 10 ? Expliquez pourquoi.


## Exercice 3 - Une liste de tuples

On souhaite maintenant stocker les coordonnées de plusieurs points dans une même structure :

```python
points = [(3, 5), (7, 2), (-1, 4), (0, 0)]
```


1. Quel est le type de la variable points ?
2. Combien de points sont stockés dans cette liste ?
3. Affichez les coordonnées du deuxième point.
4. Affichez uniquement l'abscisse du troisième point.
5. Modifiez les coordonnées du deuxième point pour qu'il devienne (10, 10). Est-ce possible ? Pourquoi ?