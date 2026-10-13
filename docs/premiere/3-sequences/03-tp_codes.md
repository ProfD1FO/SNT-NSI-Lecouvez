# TP - Détecter les erreurs dans les codes

**Objectif :** découvrir comment certains codes connus permettent de détecter des erreurs grâce à des algorithmes de contrôle.

Dans ce TP, nous allons étudier plusieurs exemples de codes utilisés en informatique ou dans la vie quotidienne. Nous allons progressivement écrire des fonctions Python permettant de vérifier leur **validité**.

## Partie 1 - Le bit de parité

### 1. Principe

Nous avons vu dans le chapitre précédent comment représenter des nombres en binaire. Mais comment vérifier qu'un message binaire n'a pas été altéré lors de sa transmission ?

Une méthode simple consiste à ajouter un **bit de parité** au message. Ce bit est choisi de manière à obtenir un nombre pair de bits égaux à `1`.

Par exemple, considérons le message suivant :

```text
Message :       1011001
Nombre de 1 :   4
```

Le nombre de `1` est déjà pair. On ajoute donc un bit `0` :

```text
Message transmis : 10110010
Nombre de 1 :      4
```

En revanche, pour le message suivant :

```text
Message :       1011011
Nombre de 1 :   5
```

On ajoute un bit `1` afin d'obtenir un nombre pair de `1` :

```text
Message transmis : 10110111
Nombre de 1 :     6
```

Si un seul bit est modifié lors de la transmission, le nombre de `1` change de parité. On peut alors détecter une erreur.

### 2. Écrire les fonctions de contrôle

**Q1.** Écrivez une fonction `compte_uns(code)` qui prend en paramètre une chaîne composée de `0` et de `1` et renvoie le nombre de `1` qu'elle contient.

Exemples :

```python
>>> compte_uns("1011001")
4

>>> compte_uns("1111")
4

>>> compte_uns("0000")
0
```

**Q2.** Écrivez une fonction `parite_valide(code)` qui renvoie `True` si le nombre de `1` dans `code` est pair, et `False` sinon.

Exemples :

```python
>>> parite_valide("10110010")
True

>>> parite_valide("10110111")
True

>>> parite_valide("10110011")
False
```

**Q3.** On considère le message suivant :

```text
10110010
```

Un bit a été modifié pendant la transmission et le message reçu est devenu :

```text
10100010
```

Utilisez votre fonction pour vérifier si une erreur peut être détectée.

**Q4.** Un message contenant deux erreurs peut-il être détecté par cette méthode ? Et pour 4 ? Justifiez votre réponse à l'aide d'un exemple.

---

## Partie 2 - Les tranches de chaînes de caractères

Nous savons déjà accéder à un élément d'une séquence grâce à son indice. Mais il est également possible d'extraire plusieurs éléments à la fois grâce aux **tranches**.

Par exemple, pour les chaînes de caractères :

```python
mot = "Informatique"

mot[0:3]  # "Inf"
mot[3:7]  # "orma"
mot[:3]   # "Inf"
mot[3:]   # "ormatique"
```

Une tranche `mot[a:b]` récupère les caractères situés entre les indices `a` et `b`. L'indice `a` est inclus, mais l'indice `b` est **exclu** comme pour le range.

Lorsque le premier indice est omis, la tranche commence au début de la chaîne. Lorsque le second est omis, elle se termine à la fin.

**Q5.** Sans tester, donnez le résultat des expressions suivantes :

```python
code = "123456789"

code[2:5]
code[:4]
code[4:]
code[-3:]
```

**Q6.** Le numéro de Sécurité sociale, également appelé NIR, comporte treize chiffres suivis d'une clé de contrôle à deux chiffres.

On dispose d'un numéro fictif de quinze chiffres :

```python
numero = "180057512345678"
```

Écrivez deux instructions permettant d'extraire :

- les treize premiers chiffres du numéro ;
- les deux derniers chiffres, correspondant à la clé de contrôle.

Vérifiez vos réponses avec Python.

---

## Partie 3 - Vérifier un numéro de Sécurité sociale

### 1. Principe

Le numéro de Sécurité sociale français comporte treize chiffres suivis d'une clé de contrôle à deux chiffres.

Cette clé est calculée à partir des treize premiers chiffres. Elle permet de vérifier la cohérence du numéro, mais ne garantit pas à elle seule qu'il correspond à une personne réelle.

Pour calculer la clé, on interprète les treize premiers chiffres comme un entier \(N\), puis on effectue le calcul suivant :

\[
K = 97 - (N \bmod 97)
\]

Le résultat est écrit sur deux chiffres. Si la clé vaut `7`, par exemple, on l'écrit `"07"`.

### 2. Calculer la clé

**Q7.** Écrivez une fonction `cle_nir(numero)` qui prend en paramètre une chaîne contenant les treize premiers chiffres d'un numéro et renvoie la clé de contrôle sous forme d'une chaîne de deux caractères.

Vous pourrez convertir la chaîne en entier avec la fonction `int` que vous connaissez bien.

**Q8.** Écrivez une fonction `nir_valide(numero)` qui prend en paramètre un numéro complet de quinze chiffres et renvoie `True` si la clé est correcte, et `False` sinon.

Vous utiliserez les tranches pour séparer les treize premiers chiffres des deux derniers, ainsi que votre fonction précédente.

**Q9.** Modifiez un chiffre d'un numéro fictif dont la clé est correcte, puis vérifiez si votre fonction détecte l'erreur.

Le contrôle permet-il de détecter toutes les erreurs possibles ?

---

## Partie 4 - Vérifier un ISBN-13

### 1. Principe

Un ISBN est un numéro permettant d'identifier une édition particulière d'un livre. Les ISBN actuels comportent treize chiffres, dont le dernier est un **chiffre de contrôle**.

Ce dernier chiffre est calculé à partir des douze chiffres précédents.

Nous allons utiliser l'exemple suivant :

```text
ISBN : 9780306406157
```

Le dernier chiffre, `7`, est le chiffre de contrôle.

### 2. Calculer le chiffre de contrôle

Pour calculer le chiffre de contrôle d'un ISBN-13, on utilise les douze premiers chiffres.

On multiplie alternativement chaque chiffre par `1` puis par `3`, en commençant par `1`, puis on additionne les résultats.

Pour notre exemple :

| Chiffre | 9 | 7 | 8 | 0 | 3 | 0 | 6 | 4 | 0 | 6 | 1 | 5 |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Multiplicateur | 1 | 3 | 1 | 3 | 1 | 3 | 1 | 3 | 1 | 3 | 1 | 3 |
| Résultat | 9 | 21 | 8 | 0 | 3 | 0 | 6 | 12 | 0 | 18 | 1 | 15 |

La somme obtenue est :

```text
9 + 21 + 8 + 0 + 3 + 0 + 6 + 12 + 0 + 18 + 1 + 15 = 93
```

On cherche ensuite le plus petit entier positif ou nul à ajouter à cette somme pour obtenir un multiple de `10`.

Ici, `93 + 7 = 100`. Le chiffre de contrôle est donc `7`.

De manière générale, le chiffre de contrôle est donné par :

\[
c = (10 - (S \bmod 10)) \bmod 10
\]

où `S` est la somme pondérée des douze premiers chiffres.

### 3. Programmer le calcul

**Q10.** Écrivez une fonction `somme_ponderee(isbn)` qui prend en paramètre une chaîne contenant les douze premiers chiffres d'un ISBN et renvoie la somme pondérée calculée précédemment.

Vous utiliserez une boucle et un indice pour accéder successivement aux chiffres. Pensez à alterner les multiplicateurs `1` et `3`.

**Q11.** Écrivez une fonction `cle_isbn(isbn)` qui prend en paramètre les douze premiers chiffres d'un ISBN et renvoie le chiffre de contrôle calculé. Votre fonction réutilisera la fonction `somme_ponderee` écrite précédemment.

Exemple :

```python
>>> cle_isbn("978030640615")
7
```

**Q12.** Écrivez une fonction `isbn_valide(isbn)` qui prend en paramètre un ISBN de treize chiffres et renvoie `True` si son chiffre de contrôle est correct, et `False` sinon.

Vous pourrez utiliser les fonctions précédentes ainsi que les tranches pour séparer les douze premiers chiffres du dernier.

Exemples :

```python
>>> isbn_valide("9780306406157")
True

>>> isbn_valide("9780306406158")
False
```

**Q13.** Modifiez un chiffre parmi les douze premiers chiffres de l'ISBN `9780306406157`, puis vérifiez si votre fonction détecte l'erreur.

---

## Bilan

**Q14.** Un code peut-il être considéré comme correct simplement parce que sa clé de contrôle est valide ? Pourquoi ?

**Q15.** Dans les fonctions de validation, pourquoi est-il utile de manipuler les codes sous forme de chaînes de caractères plutôt que de nombres entiers ?