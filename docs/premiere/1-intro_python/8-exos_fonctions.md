# Exercices 4 - Les fonctions

## Exercice 1 - Fonction mystère et appels

On suppose la fonction suivante :

```python
def mystere(secret):
    return secret>=0
```

1. Sans la tester, quel est l'intérêt de cette fonction ?

2. Recopiez maintenant cette fonction puis exécutez le programme. Dans la console, appeler cette fonction avec l'argument `-82` puis avec l'argument `12`.

## Exercice 2 - Première fonction à écrire:

Ecrivez une fonction nommée `carre` qui prend en paramètre un entier `x` et renvoie le carré de ce nombre. Par exemple, on doit obtenir à l'appel :

```python
>>> carre(3)
9
>>> carre(10)
100
```

## Exercice 3 - Autre fonction

Ecrivez une fonction nommée `plus_grand` qui prend en paramètre deux valeurs comparables `a` et `b` et renvoie la plus grande valeur entre les deux. Par exemple, on doit obtenir à l'appel :

```python
>>> plus_grand(2, 9)
9
>>> plus_grand(33, 3)
33
>>> plus_grand(2, 2)
2
```

## Exercice 4 - Utiliser une fonction

On considère la fonction suivante :

```python
def double(x):
    return 2 * x
```

1. Que renvoient les appels suivants ?

```python
>>> double(4)
>>> double(15)
>>> double(-3)
```

2. Écrivez une fonction triple qui renvoie le triple de son paramètre.
3. Écrivez une fonction moitie qui renvoie la moitié de son paramètre.
4. Sans tester, que vaut double(triple(5)) ?


## Exercice 5 - Calculer un prix

On souhaite calculer le prix payé pour un article après réduction.

Écrivez une fonction `prix_reduit` qui prend en paramètres :

- `prix` : le prix initial de l'article ;
- `reduction` : le pourcentage de réduction.

La fonction doit renvoyer le prix après réduction.

Par exemple :

```python
>>> prix_reduit(100, 20)
80.0
>>> prix_reduit(50, 10)
45.0
```

## Défi 1 - Manipuler des dates

On souhaite créer un programme permettant de manipuler des dates.

Une date est représentée par trois nombres :

```text
jour, mois, année
```

Par exemple :
15 / 9 / 2026

### Partie 1 - Vérifier une année

Écrivez une fonction `est_bissextile(annee)` qui renvoie True si l'année est bissextile et False sinon. Vous pourrez bien entendu vous inspirer de l'exercice sur les années bissextiles déjà fait pour la programmer.

Une année est bissextile si :

- pour une année de fin de siècle, elle est divisible par 400
- pour les autres années, si elle est divisible par 4

Par exemple :

>>> est_bissextile(2024)
True
>>> est_bissextile(1900)
False
>>> est_bissextile(2000)
True

### Partie 2 - Nombre de jours d'un mois

Écrivez une fonction `nombre_jours(mois, annee)` qui renvoie le nombre de jours du mois donné.

Elle devra utiliser `est_bissextile` pour déterminer le nombre de jours du mois de février.

Par exemple :

>>> nombre_jours(2, 2024)
29
>>> nombre_jours(2, 2025)
28
>>> nombre_jours(4, 2026)
30

### Partie 3 - Vérifier une date

Écrivez une fonction `date_valide(jour, mois, annee)` qui renvoie True si la date est valide et False sinon.

Cette fonction devra utiliser `nombre_jours`.

Par exemple :

```python
>>> est_bissextile(2024)
True
>>> est_bissextile(1900)
False
>>> est_bissextile(2000)
True
```
