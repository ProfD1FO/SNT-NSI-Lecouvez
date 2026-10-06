# Exercices 1 : Les chaînes de caractères

## Exercice 1 — Les indices

**Sans exécuter** le programme, donner la valeur affichée dans chaque cas.

```python
mot = "Informatique"

print(mot[0])
print(mot[3])
print(mot[7])
print(mot[-1])
print(mot[-4])
print(mot[19])
print(len(mot))
```

---

## Exercice 2 — À toi de jouer

On suppose disposer d'une variable `prenom` contenant le prénom de votre choix

Écrire les instructions permettant d'afficher :

1. le premier caractère de `prenom` ;
2. le dernier caractère de `prenom` ;
3. le troisième caractère de `prenom` ;
4. l'avant-dernier caractère de `prenom`.

Pour tester, on pourra supposer que
```python
prenom = "Lune"
```

---

## Exercice 3 — Extraire une information

On souhaite créer une fonction permettant d'obtenir les initiales d'une personne dont on connaît le prénom et le nom.

Écrire une fonction `initiales(prenom, nom)` qui renvoie la première lettre du prénom suivie de la première lettre du nom.

Exemple :

```python
>>> initiales("Verso", "Dessendre")
"VD"

>>> initiales("Mark", "Evans")
"ME"
```

Tester ensuite votre fonction avec plusieurs personnes.

---
## Exercice 4 - Compter les caractères

Ecrivez une fonction `nombre_caracteres` qui prend en paramètre une chaîne de caractères et renvoie le nombre total de caractères de la chaîne. Attention : **interdiction** d'utiliser la fonction `len()`.

Exemple:
```python
>>> nombre_caracteres("Bonjour")
7
```

---

## Exercice 5 - Parcourir une chaîne

Écrivez une fonction `compte_a` qui prend en paramètre une chaîne de caractères `mot` et compte le nombre de lettres `a` présentes dans une chaîne.

Par exemple :

```python
>>> compte_a("abracadabra")
5
```

---

## Exercice 6 - Les voyelles

Écrivez une fonction :

```python
def compte_voyelles(mot):
    ...
```

qui renvoie le nombre de voyelles présentes dans `mot`.

On considérera que les voyelles sont :

```text
a, e, i, o, u, y
```

Par exemple :

```python
>>> compte_voyelles("informatique")
6
```

---

## Exercice 7 - Recherche d'un caractère

Écrivez une fonction :

```python
def recherche_caractere(mot, caractere):
    ...
```

qui renvoie `True` si `caractere` est présent dans `mot`, et `False` sinon.

Exemples :

```python
>>> recherche_caractere("Bonjour", "o")
True

>>> recherche_caractere("Bonjour", "z")
False
```


## Exercice 8 - Remplacer des caractères

Écrivez une fonction :

```python
def remplace_a(mot):
    ...
```

qui renvoie une nouvelle chaîne dans laquelle toutes les lettres `a` ont été remplacées par des `o`.

Exemples :

```python
>>> remplace_a("banane")
"bonono"

>>> remplace_a("abracadabra")
"obrocodobro"
```

!!! warning "Attention"

````
Une chaîne de caractères ne peut pas être modifiée directement caractère par caractère.

Par exemple, l'instruction suivante provoque une erreur :

```python
mot = "Bonjour"
mot[0] = "b"
```

Il faudra donc construire une **nouvelle chaîne de caractères**.
````

---

### Pour aller plus loin

#### Exercice 9 - Position

Écrivez une fonction :

```python
def position_caractere(mot, caractere):
    ...
```

qui renvoie la position de la **première occurrence** de `caractere` dans `mot`.

Si le caractère n'est pas présent, la fonction renverra `-1`.

Exemples :

```python
>>> position_caractere("Bonjour", "o")
1

>>> position_caractere("Bonjour", "z")
-1
```

---

#### Exercice 10 - Palindrome 

Un **palindrome** est un mot qui peut être lu dans les deux sens.

Par exemple :

```text
kayak
radar
été
```

Écrivez une fonction :

```python
def palindrome(mot):
    ...
```

qui renvoie `True` si `mot` est un palindrome et `False` sinon.

Exemples :

```python
>>> palindrome("kayak")
True

>>> palindrome("radar")
True

>>> palindrome("python")
False
```

