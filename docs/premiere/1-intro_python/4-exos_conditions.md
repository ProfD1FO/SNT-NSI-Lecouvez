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
age = 20

if age >= 18:
    print("Majeur")
```

Puis faites de même avec :

```python
age = 15

if age >= 18:
    print("Majeur")
```

**Question :** que se passe-t-il lorsque la condition est fausse ?

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


