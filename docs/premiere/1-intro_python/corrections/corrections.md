# Corrections — Exercices 1 à 4

## Exercices 1 — Constructions élémentaires

### Exercice 1 — Affectations et séquences

**a.**

```python
x = 8
```

**b.**

```python
x = 8
```

**c.**

```python
x = 10
y = 7
```

---

### Exercice 2 — Les types

| Valeur        | Type    |
| ------------- | ------- |
| `17`          | `int`   |
| `3.14`        | `float` |
| `"17"`        | `str`   |
| `True`        | `bool`  |
| `"Bonjour"`   | `str`   |
| `-5`          | `int`   |
| `"True"`      | `str`   |
| `"'bonsoir'"` | `str`   |
| `7 + 3.12`    | `float` |
| `4 / 2`       | `float` |
| `" 2.4 "`     | `str`   |

`17` est un entier (`int`) alors que `"17"` est une chaîne de caractères (`str`).

---

### Exercice 3 — Prévoir l'affichage

```text
10
21
343
2
1
```

---

### Exercice 4 — Priorité des opérations

```python
a = 14
b = 20
c = 16
```

---

### Exercice 5 — Une erreur ?

`"3"` est une chaîne de caractères tandis que `2` est un entier.

Python ne peut pas additionner directement ces deux types :

```python
"3" + 2
```

provoque donc une `TypeError`.

---

### Exercice 6 — `print` et `input`

`input()` renvoie toujours une chaîne de caractères.

Avec la saisie `32`, la variable `nombre` contient donc `"32"`.

```python
print(nombre * 4)
```

affiche :

```text
32323232
```

Pour effectuer réellement une multiplication, il faut convertir la saisie en entier :

```python
nombre = int(input("Choisissez un nombre"))
print(nombre * 4)
```

---

### Exercice 7 — Calcul d'un prix

```python
prix = float(input("Prix : "))
quantite = int(input("Quantité : "))

total = prix * quantite

print("Total :", total)
```

---

### Exercice 8 — Convertir une durée

```python
duree = int(input("Durée en minutes : "))

heures = duree // 60
minutes = duree % 60

print(heures, "h", minutes, "min")
```

---

# Exercices 2 — Booléens et instructions conditionnelles

## Exercice 1 — Vrai ou faux ?

1. `8 > 5` → `True`
2. `12 < 4` → `False`
3. `15 == 15` → `True`
4. `7 != 7` → `False`
5. `10 >= 10` → `True`
6. `3 <= 2` → `False`

---

## Exercice 2 — Comparer des variables

1. `age >= 18` → `False`
2. `age < 18` → `True`
3. `note >= 10` → `True`
4. `note == 14.5` → `True`
5. `prenom == "Alice"` → `True`
6. `prenom == "alice"` → `False`

---

## Exercice 3 — `and`, `or` et `not`

1. `True and True` → `True`
2. `True and False` → `False`
3. `False or True` → `True`
4. `False or False` → `False`
5. `not True` → `False`
6. `not False` → `True`

---

## Exercice 4 — Plusieurs conditions

L'énoncé contient une erreur : les variables données sont `age` et `nom`, mais certaines expressions utilisent `prenom`.

1. `age != 20` → `True`

2. `age > 30 and prenom = "Cléa"` → erreur de syntaxe.

Pour comparer, il faudrait utiliser `==` :

```python
age > 30 and prenom == "Cléa"
```

Mais `prenom` n'est pas défini dans l'énoncé.

3. `age <= 33 and nom == "Verso"` → `True`

4. `not (age >= 18)` → `False`

5. `prenom == "Maëlle" or age == 33` → `NameError` car `prenom` n'est pas défini.

---

## Exercice 5 — Prévoir l'affichage

Premier programme :

```text
Fin du programme
```

Deuxième programme :

```text
Majeur
Fin du programme
```

---

## Exercice 6 — `if` et `else`

```python
nombre = int(input("Entrez un nombre : "))

if nombre >= 0:
    print("Positif")
else:
    print("Négatif")
```

---

# Exercices 3 — Les boucles

## Exercice 1 — Les suites de valeurs

1. `range(2, 7)` → `2, 3, 4, 5, 6`
2. `range(5, 10)` → `5, 6, 7, 8, 9`
3. `range(0, 10, 2)` → `0, 2, 4, 6, 8`
4. `range(10, 0, -2)` → `10, 8, 6, 4, 2`
5. `range(10)` → `0, 1, 2, 3, 4, 5, 6, 7, 8, 9`
6. `range(90, 91)` → `90`

---

## Exercice 2 — Fabriquer un `range`

1.

```python
range(6)
```

2.

```python
range(9, 14)
```

3.

```python
range(3, 16, 3)
```

4.

```python
range(12, 7, -1)
```

5.

```python
range(10, -1, -2)
```

---

## Exercice 3 — Prédire le comportement d'une boucle

### Premier programme

À chaque tour, `2` est ajouté à `a`.

```python
a = 20
```

### Deuxième programme

On additionne les valeurs de `0` à `9` :

```python
a = 45
```

### Troisième programme

Les valeurs successives de `a` sont :

```text
1
2
4
8
16
```

La valeur finale de `b` est :

```python
b = -21
```

---

## Exercice 4 — Écrire des boucles simples

### 1. Nombres de 1 à 100

```python
for i in range(1, 101):
    print(i)
```

### 2. Table de 9

```python
for i in range(11):
    print(i * 9)
```

### 3. Carrés de 1 à 10

```python
for i in range(1, 11):
    print(i ** 2)
```

---

## Exercice 5 — Que va afficher ce programme ?

```text
100
50
25
12
6
3
1
```

La boucle s'arrête ensuite car `nombre` devient `0`.

---

## Exercice 6 — Combien de tickets ?

La valeur finale de `billets` est :

```python
billets = 6
```

Il reste alors `2 €`.

---

## Exercice 7 — L'épargne

```python
argent = 100
mois = 0

while argent < 500:
    argent = argent + 25
    mois = mois + 1
```

À la fin :

```python
mois = 16
argent = 500
```

---


