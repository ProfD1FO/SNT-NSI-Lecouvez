# Exercices 2 — Booléens et instructions conditionnelles

## Partie 1 — Comparaisons

### Exercice 1 — Vrai ou faux ?

Sans utiliser Python, indiquez si chacune des expressions suivantes vaut `True` ou `False`.

1. `8 > 5`
2. `12 < 4`
3. `15 == 15`
4. `7 != 7`
5. `10 >= 10`
6. `3 <= 2`

Puis vérifiez vos réponses dans la console Python.

---

### Exercice 2 — Comparer des variables

On considère :

```python
age = 17
note = 14.5
prenom = "Alice"
```

Indiquez si les expressions suivantes valent `True` ou `False`.

1. `age >= 18`
2. `age < 18`
3. `note >= 10`
4. `note == 14.5`
5. `prenom == "Alice"`
6. `prenom == "alice"`

---

## Partie 2 — Les opérateurs booléens

### Exercice 3 — `and`, `or` et `not`

Sans utiliser Python, indiquez le résultat de chaque expression.

1. `True and True`
2. `True and False`
3. `False or True`
4. `False or False`
5. `not True`
6. `not False`

Puis vérifiez vos réponses dans la console Python.

---

### Exercice 4 — Plusieurs conditions

On considère :

```python
age = 33
nom = "Verso"
```

Indiquez si les expressions suivantes valent `True` ou `False`.

1. `age != 20`
2. `age > 30 and prenom = "Cléa"`
3. `age <= 33 and nom == "Verso" `
4. `not (age >= 18)`
5. `prenom == "Maëlle" or age == 33`

---

## Partie 3 — Les instructions conditionnelles

### Exercice 5 — Prévoir l'affichage

Sans exécuter le programme, indiquez ce qui sera affiché.

```python
age = 12

if age >= 18:
    print("Majeur")
print("Fin du programme")
```

Puis faites de même avec :

```python
age = 33

if age >= 18:
    print("Majeur")
print("Fin du programme")

```

---

### Exercice 6 — `if` et `else`

Complétez le programme afin qu'il affiche `"Positif"` si le nombre est positif ou nul, et `"Négatif"` sinon.

```python
nombre = int(input("Entrez un nombre : "))

if __________________:
    print("Positif")
else:
    print("Négatif")
```

Testez votre programme avec plusieurs valeurs.

---

### Défis de programmation :

#### Défi 1 — Les années bissextiles

On dit qu'une année est bissextile si :

- Elle est divisible par 4
- Exception pour les années de fin de siècle (finissant par 00) : elles ne sont bissextiles que si elles sont divisibles par 400.

**Objectif :** écrire un programme qui demande une année à l'utilisateur et lui indique si elle est bissextile ou non.

#### Défi 2 — Tarification d'une place de cinéma

Un cinéma applique les tarifs suivants :

* moins de 12 ans : **6 €** ;
* de 12 à 25 ans : **8 €** ;
* de 26 à 64 ans : **11 €** ;
* à partir de 65 ans : **7 €**.

Le mercredi, une réduction de **2 €** est appliquée à tous les tarifs.

**Objectif :** écrire un programme qui demande l'âge de l'utilisateur ainsi que le jour de la semaine, puis affiche le prix de la place.

Exemples :

```python
Quel âge avez-vous ? 17
Quel jour sommes-nous ? mercredi

Prix de la place : 6 €
```

```python
Quel âge avez-vous ? 70
Quel jour sommes-nous ? samedi

Prix de la place : 7 €
```

**Défi supplémentaire :** le cinéma propose également une réduction de 1 € aux étudiants de moins de 26 ans. Modifiez votre programme pour prendre en compte cette réduction.

#### Défi 3 : Les triangles

On souhaite écrire un programme capable d'analyser un triangle à partir de la longueur de ses trois côtés.

Le programme demande les trois longueurs à l'utilisateur.

##### 1. Le triangle est-il possible ?

Pour que trois longueurs puissent former un triangle, **la longueur du plus grand côté doit être strictement inférieure à la somme des deux autres côtés**.

Écrire un programme qui indique si les trois longueurs peuvent former un triangle.

Exemples :

```text
Premier côté : 3
Deuxième côté : 4
Troisième côté : 5

Ces longueurs peuvent former un triangle.
```

```text
Premier côté : 2
Deuxième côté : 3
Troisième côté : 8

Ces longueurs ne peuvent pas former un triangle.
```

---

##### 2. Quel est le type du triangle ?

Si les trois longueurs peuvent former un triangle, déterminer s'il est :

* **équilatéral** : les trois côtés sont de même longueur ;
* **isocèle** : deux côtés sont de même longueur ;
* **scalène** : les trois côtés sont de longueurs différentes.

Par exemple :

```text
3  →  3  →  3
Triangle équilatéral
```

```text
4  →  4  →  6
Triangle isocèle
```

```text
3  →  4  →  5
Triangle scalène
```

---

##### 3. Le triangle est-il rectangle ?

Un triangle est rectangle si le carré de la longueur de son plus grand côté est égal à la somme des carrés des deux autres côtés.

Par exemple :

```text
3² + 4² = 5²
```

Le triangle de côtés `3`, `4` et `5` est donc rectangle.

Modifier le programme afin qu'il indique également si le triangle est rectangle.

!!! tip "Attention"
Il faut d'abord déterminer quel est le **plus grand côté**.

---

##### ⭐ Etape finale

Essayez de faire en sorte que votre programme puisse donner une réponse complète, vous pourrez notamment utiliser des **fonctions** si vous maîtrisez la notion :

```text
Triangle valide
Triangle isocèle
Triangle non rectangle
```

ou :

```text
Triangle valide
Triangle scalène
Triangle rectangle
```

**Question :** dans quel ordre devez-vous effectuer les différents tests ?

Votre programme doit notamment éviter d'essayer de déterminer le type d'un triangle qui n'existe pas.

