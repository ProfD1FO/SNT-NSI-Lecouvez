# Exercices 1 – Constructions élémentaires

## Exercices écrits

### Exercice 1 — Affectations et séquences

Sans exécuter le programme, indiquer la valeur de chaque variable à la fin.

**a.**

```python
x = 5
x = 8
```

**b.**

```python
x = 5
x = x + 3
```

**c.**

```python
x = 5
y = x + 2
x = 10
```

---

### Exercice 2 — Les types

Donner le type de chacune des valeurs suivantes :

```text
17
3.14
"17"
True
"Bonjour"
-5
"True"
"'bonsoir'"
7 + 3.12
4 / 2
" 2.4 "
```

**Question :** quelle est la différence entre `17` et `"17"` ?

---

### Exercice 3 — Prévoir l'affichage

Sans exécuter le programme, prévoir ce qui sera affiché :

```python
a = 7
b = 3

print(a + b)
print(a * b)
print(a ** b)
print(a // b)
print(a % b)
```

Vérifier ensuite votre réponse avec Python.

---

### Exercice 4 — Priorité des opérations

Calculer les valeurs des variables suivantes :

```python
a = 2 + 3 * 4
b = (2 + 3) * 4
c = 20 - 8 // 2
```

Vérifier vos réponses avec Python.



### Exercice 5 — Une erreur ?

Expliquer l'erreur de l'instruction suivante :

```python
>>> "3" + 2
    Traceback (most recent call last):    File "<stdin>", line 1, in <module>
    TypeError: unsupported operand type(s) for +: 'str' and 'int'
```

---

### Exercice 6 — print et input

Sans tester avec python, devinez ce que va renvoyer le programme suivant si le nombre entré par l'utilisateur est 32 ?

```python
nombre = input("Choisissez un nombre")
print(nombre*4)
```

Que rajouter dans le programme pour qu'il multiplie réelement par 4 le nombre de départ? Testez le maintenant sur Python.

---

## Exercices de programmation

### Exercice 7 — Calcul d'un prix

Écrire un programme qui :

1. demande le prix d'un article ;

2. demande la quantité achetée ;

3. calcule le prix total ;

4. affiche le résultat.

**Exemple :**

```text
Prix : 2.50
Quantité : 4
Total : 10.0
```

---

### Exercice 8 — Convertir une durée

Écrire un programme qui demande une durée en minutes et affiche sa correspondance en heures et minutes.

**Exemple :**

```text
Durée en minutes : 137
2 h 17 min
```

**Indication :** utiliser les opérateurs `//` et `%`.

### Défis de programmation :

#### Défi 1 — Échanger deux variables

On suppose deux variables `a` et `b` contenant des valeurs quelconques :

```python
a = 12
b = 35
```

Le but est **d'échanger les valeurs contenues dans ces deux variables**.

À la fin du programme, on veut obtenir :

```python
a = 35
b = 12
```

⚠️ **Attention :** vous ne devez pas simplement réaffecter directement les valeurs de `a` et `b`.

Votre programme doit fonctionner **quelle que soit la valeur initiale de `a` et `b`**.

Par exemple, si on remplace :

```python
a = 12
b = 35
```

par :

```python
a = 7
b = 42
```

le même programme doit automatiquement donner :

```python
a = 42
b = 7
```

**Vous ne devez donc pas modifier votre programme lorsque les valeurs initiales changent.**

**Objectif :** trouver une méthode permettant de conserver les valeurs initiales tout en les échangeant.

#### Défi 2 - Le super convertisseur

Reprenons le convertisseur de l'exercice 8 et améliorons le.
Il demandera maintenant une valeur en seconde et l'affichera en heures, minutes et secondes

```
Nombre de secondes : 4523
Conversion : 1 h 15 min 23 s
```

**Objectif :** Ecrire un programme qui convertit une durée en secondes en heure, minutes et secondes

#### Défi 3 - Les taxes

**Objectif :** Ecrire un programme qui demande un prix hors taxe et un taux de TVA puis qui calcule

```
Prix HT : 20
TVA (%) : 20
Prix TTC : 24
```