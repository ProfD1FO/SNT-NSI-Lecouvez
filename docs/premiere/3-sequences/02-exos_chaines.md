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

