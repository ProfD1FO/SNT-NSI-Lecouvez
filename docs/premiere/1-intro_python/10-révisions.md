# Exercices de révision — Fonctions, conditions et boucles

Pour chaque exercice, écrivez la fonction demandée. Il faudra parfois faire des conditions, des boucles ou même les deux.


### Exercice 1 — Dans l'intervalle

Écrire une fonction `dans_intervalle(x)` qui renvoie `True` si `x` est compris entre 10 et 20 inclus, et `False` sinon.

```python
>>> dans_intervalle(15)
True

>>> dans_intervalle(25)
False
```

### Exercice 2 — Température

Écrire une fonction `est_froid(temperature)` qui renvoie `True` si la température est strictement inférieure à 10 degrés, et `False` sinon.

### Exercice 3 — Tarif réduit

Un cinéma propose un tarif réduit aux personnes de moins de 18 ans.

Écrire une fonction `tarif_reduit(age)` qui renvoie `True` si la personne bénéficie du tarif réduit et `False` sinon.

### Exercice 4 — Catégorie d'âge

Écrire une fonction `categorie_age(age)` qui renvoie :

* `"enfant"` si l'âge est inférieur à 12 ;
* `"adolescent"` si l'âge est compris entre 12 et 17 ;
* `"adulte"` à partir de 18 ans.


### Exercice 5 — Somme jusqu'à n

Écrire une fonction `somme_jusqua(n)` qui renvoie la somme des entiers de 1 à`n`.

Exemple :

```python
>>> somme_jusqua(4)
10
```

### Exercice 6 — Compter les nombres pairs

Écrire une fonction `nombre_pairs(n)` qui renvoie combien de nombres pairs sont compris entre 1 et `n` inclu.

Exemple :

```python
>>> nombre_pairs(10)
5
```

### Exercice 7 — Dernier chiffre 

Écrire une fonction `dernier_chiffre(n)` qui renvoie le dernier chiffre d'un entier positif. 

Exemple :

```python
>>> dernier_chiffre(384)
4
```


### Exercice 8 — Compter les chiffres

Écrire une fonction `nombre_chiffres(n)` qui renvoie le nombre de chiffres de `n`.

Exemples :

```python
>>> nombre_chiffres(7)
1

>>> nombre_chiffres(42)
2

>>> nombre_chiffres(384)
3
```

### Exercice 9 — Trois nombres

Vous disposez de la fonction `plus_grand(a, b)` écrite dans la fiche précédente.

Écrire une fonction `plus_grand_trois(a, b, c)` qui renvoie la plus grande des trois valeurs **en utilisant la fonction `plus_grand` déjà programmée **.

### Exercice 10 — Nombre mystère

Écrire une fonction indice(nombre, mystere) qui renvoie :

"trop petit" si nombre est inférieur à mystere ;
"trop grand" si nombre est supérieur à mystere ;
"gagné" si les deux nombres sont égaux.
