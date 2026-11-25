# Exercices 3 : Architectures multicœurs et parallélisme

## Exercice 1 – Peut-on paralléliser ces tâches ?

On dispose d'un processeur possédant deux cœurs. On souhaite effectuer les opérations suivantes dans deux situations différentes.

**Situation A :**

- A : calculer 12+8.

- B : calculer 15 × 3.

- C : calculer 40-7.

- D : calculer 25 ÷ 5.

**Situation B :**

- A : calculer 12+8.

- B : multiplier le résultat de A par 3.

- C : soustraire 7 au résultat de B.

- D : diviser le résultat de C par 5.

**1.** Pour chacune des deux situations, indiquer si les quatre opérations peuvent être réparties entre deux cœurs et exécutées simultanément en partie ou en totalité.

**2.** Pour la situation A, proposer une répartition des opérations sur les deux cœurs. Combien de temps faut-il pour effectuer les quatre calculs si chaque opération nécessite une seconde ?

**3.** Pour la situation B, expliquer pourquoi les opérations doivent être effectuées dans un ordre précis.

**4.** En comparant les deux situations, expliquer ce qui détermine la possibilité d'exécuter plusieurs calculs en parallèle.

## Exercice 2 – Quel gain de temps ?

Un programme nécessite 100 secondes de calcul sur un processeur monocœur.

On suppose que :

- Le travail peut être réparti parfaitement entre plusieurs cœurs.

- Tous les cœurs effectuent la même quantité de travail à la même vitesse.

- Il n'y a aucun temps supplémentaire lié à la répartition du travail ou à la communication entre les cœurs.

Dans ces conditions, le temps d'exécution est divisé par le nombre de cœurs utilisés.

| Nombre de cœurs | Temps d'exécution théorique |
|---:|---:|
| 1 | 100 s |
| 2 | |
| 4 | |
| 5 | |
| 8 | |

**1.** Compléter le tableau avec les suppositions effectuées ci-dessus.

**2.** Quel est le facteur d'accélération obtenu avec 4 cœurs ? Et avec 8 cœurs ?

**3.** Dans la réalité, pourquoi le temps d'exécution peut-il être supérieur aux valeurs calculées dans le tableau ?