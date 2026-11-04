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
>>> combien_de_bob(["Verso", "Maëlle", "Cléa"])
0
```

---

## Exercice 3 - Le maximum

Ecrire une fonction `maximum` qui prend en paramètre une liste `li` d'entiers et qui renvoie **la valeur** du plus grand entier de la liste.

Par exemple :

```python
>>> maximum([2, 1, 7, 12, 10])
12
>>> maximum([3, 9, 1, 2])
9
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

## Exercice 5 — Modifier une liste

On considère le programme suivant :

```python
nombres = [4, 8, 12, 16, 20]

nombres[1] = 10
nombres.append(25)
nombres.pop(3)
nombres[0] = nombres[0] + 2
nombres.append(29)
nombres.append(10)
nombres.pop(-1)

print(nombres)
```

**Sans exécuter le programme**, donner le contenu de la liste `nombres` après chacune des instructions et indiquer ce qu'affiche le programme à la fin.

---

## Exercice 6 — Sélectionner des prénoms

On considère une liste contenant des prénoms :

```python
prenoms = ["Alice", "Thomas", "Emma", "Alexandre", "Léa", "Antoine"]
```

Écrire une fonction `prenoms_courts(li)` qui prend en paramètre une liste de prénoms et qui renvoie une nouvelle liste contenant uniquement les prénoms comportant **au maximum** 4 caractères.

Par exemple :

```python
>>> prenoms_courts(["Alice", "Tom", "Emma", "Léa", "Antoine"])
["Tom", "Emma", "Léa"]
```

---

## Exercice 7 — Mise à jour des notes

On considère une liste contenant les notes d'un élève :

```python
notes = [12, 8, 15, 9, 14]
```

Écrire une fonction `ajoute_points(notes, points)` qui ajoute un nombre de points à chacune des notes de la liste.

Par exemple :

```python
>>> notes = [12, 8, 15, 9, 14]
>>> ajoute_points(notes, 2)
>>> notes
[14, 10, 17, 11, 16]
```

Attention, la fonction devra uniquement modifier directement la liste reçue en paramètre. Celle-ci ne renverra donc rien (pas de return), elle va se contenter de modifier le paramètre.

---

## Exercice 8 — Retirer les derniers éléments d'une liste

On considère une liste de nombres :

```python
nombres = [5, 12, 8, 17, 3, 21]
```

Écrire une fonction `retire_derniers(li, n)` qui prend en paramètres une liste `li` et un entier `n`, et qui supprime les `n` derniers éléments de la liste.

La fonction ne renvoie rien : elle modifie directement la liste reçue en paramètre.

Par exemple :

```python
>>> nombres = [5, 12, 8, 17, 3, 21]
>>> retire_derniers(nombres, 2)
>>> nombres
[5, 12, 8, 17]
```

On pourra supposer que `n` est inférieur ou égal à la longueur de la liste pour éviter que le programme renvoie une erreur.

## Exercice Bonus 1:

Écrire une fonction `sans_doublons(li)` qui prend en paramètre une liste et qui renvoie une nouvelle liste contenant les mêmes éléments, mais sans doublons.

On conservera uniquement la première apparition de chaque élément.

Par exemple :

```python
>>> sans_doublons([3, 5, 3, 2, 5, 8, 2])
[3, 5, 2, 8]
```