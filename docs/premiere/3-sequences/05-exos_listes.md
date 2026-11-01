# Exercices 2: Les listes

## Exercice 1 — Les indices

```python
liste1 = [1, 9, 10, 0]
liste2 = ["Sam", "Bilbo", "Frodon"]

print(liste1[3])
print(liste1[-4])
print(liste2[-1])
print(len(liste2))
print (liste2[1][2])
```
---

## Exercice 2 - Nombre de Bob

Ecrire une fonction `combien_de_bob` qui prend en paramètre une liste `prenoms` de chaînes de caractères correspondant à des prénoms et qui renvoie le nombre de personnes s'appelant `"Bob"` dans cette liste. 

Par exemple :

```python
>>> combien_de_bob(["Bob", "Cléa", "Bob", "Xavier"])
2
>>> maximum(["Verso", "Maëlle", "Cléa"])
0
```

---

## Exercice 3 - Le maximum

Ecrire une fonction `maximum` qui prend en paramètre une liste `li` d'entiers et qui renvoie **la valeur** du plus grand entier de la liste.

Par exemple :

```python
>>> maximum([2, 1, 7, 12, 10])
12
>>> maximum([2, 1, 7, 12, 10])
1
```
---

## Exercice 4 - La moyenne

Ecrire une fonction `moyenne` qui prend en paramètre une liste `notes` de flottants correspondant à des notes et qui renvoie la **moyenne des valeurs** de cette liste.

Par exemple :

```python
>>> moyenne([12, 14, 16])
14
>>> moyenne([6.5, 12.5, 20])
13
```

---

