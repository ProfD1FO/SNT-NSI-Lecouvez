# Exercices 2 : Exécution des instructions par le processeur

## Partie 1 – Exercices sur papier

### Exercice 1 – Du programme aux instructions machine

On souhaite réaliser le programme Python suivant :

```python
a = 15
b = 4
c = a + b
d = c * 2
```

On considère que sa traduction en instructions machine simplifiées donne le programme suivant :

| Adresse | Instruction |
|---:|---|
| 0 | `LOAD 10` |
| 1 | `ADD 11` |
| 2 | `STORE 12` |
| 3 | `LOAD 12` |
| 4 | `MULT 13` |
| 5 | `STORE 14` |
| 6 | `HALT` |

Les données sont initialement stockées aux adresses suivantes :

| Adresse | Valeur |
|---:|---:|
| 10 | 15 |
| 11 | 4 |
| 12 | 0 |
| 13 | 2 |
| 14 | 0 |

**1.** À quelles variables Python correspondent les adresses 10 à 14 (sauf 13)?
**2.** Deviner les valeurs qui seront finalement stockées aux adresses 12 et 14 après exécution du programme.
**3.** Compléter le tableau suivant pour suivre l'évolution de l'accumulateur et des données en mémoire.

| Instruction exécutée | ACC | Mémoire[12] | Mémoire[14] |
|---|---:|---:|---:|
| État initial | — | 0 | 0 |
| `LOAD 10` | | | |
| `ADD 11` | | | |
| `STORE 12` | | | |
| `LOAD 12` | | | |
| `MULT 13` | | | |
| `STORE 14` | | | |
| `HALT` | | | |

**4.** Une instruction machine correspond-elle nécessairement à une ligne du programme Python ? Justifier à partir de cet exemple.
**5.** On remplace la valeur située à l'adresse 11 par 8, sans modifier le programme. Quel sera le nouveau contenu de l'adresse 14 ? Expliquer.

### Exercice 2 – Suivre l'exécution d'un programme

On considère le programme suivant :

| Adresse | Contenu |
|---:|---|
| 0 | `LOAD 8` |
| 1 | `ADD 9` |
| 2 | `SUB 10` |
| 3 | `STORE 11` |
| 4 | `HALT` |
| 8 | 20 |
| 9 | 7 |
| 10 | 5 |
| 11 | 0 |

Le processeur démarre avec un CO égal à 0 et un ACC vide.

**1.** Prévoir le résultat final qui sera stocké à l'adresse 11.
**2.** Compléter le tableau suivant. Les valeurs indiquées correspondent à l'état du processeur **après l'exécution complète de chaque instruction**.

| Instruction exécutée | CO | RI | ACC | Mémoire[11] |
|---|---:|---|---:|---:|
| État initial | 0 | — | — | 0 |
| `LOAD 8` | | | | |
| `ADD 9` | | | | |
| `SUB 10` | | | | |
| `STORE 11` | | | | |
| `HALT` | | | | |

**3.** Lors de l'exécution de `LOAD 8`, le processeur accède deux fois à la mémoire. Expliquer à quoi correspondent ces deux accès.
**4.** Un élève affirme qu'après `SUB 10`, la valeur 5 est déjà stockée à l'adresse 11. Expliquer son erreur.
**5.** On supprime l'instruction `STORE 11`. Le calcul est-il toujours réalisé ? Le résultat est-il conservé en mémoire à l'adresse 11 ? Justifier.

### Exercice 3 – Modifier le déroulement d'un programme

On considère le programme suivant :

| Adresse | Instruction |
|---:|---|
| 0 | `LOAD 8` |
| 1 | `JUMP 4` |
| 2 | `ADD 9` |
| 3 | `STORE 10` |
| 4 | `SUB 11` |
| 5 | `STORE 10` |
| 6 | `HALT` |
| 8 | 20 |
| 9 | 100 |
| 10 | 0 |
| 11 | 3 |

**1.** Avant de dérouler le programme, prévoir le contenu final de l'adresse 10.
**2.** Compléter le tableau suivant en indiquant les instructions réellement exécutées. Le CO correspond à sa valeur après l'exécution complète de l'instruction.

| Instruction exécutée | CO | ACC | Mémoire[10] |
|---|---:|---:|---:|
| État initial | 0 | — | 0 |
| | | | |
| | | | |
| | | | |
| | | | |
| | | | |

**3.** Quelles instructions du programme ne sont jamais exécutées ?
**4.** Que se passerait-il si l'instruction `JUMP 4` était supprimée ? Prévoir le nouveau résultat final.
**5.** Proposer une modification permettant d'obtenir ce nouveau résultat, puis justifier votre réponse.

---

## Partie 2 – Exercices sur machine avec VNSim

Pour cette partie, utiliser le simulateur VNSim :

https://apps.lyceum.fr/vnsim/

**Attention :** le simulateur utilise une notation différente de celle de nos exercices papier.

| Dans le cours | Dans VNSim |
|---|---|
| `LOAD` | `LOD` |
| `STORE` | `STO` |
| `MULT` | `MUL` |
| `HALT` | `HLT` |
| `JUMP` | `JMP` |

Les instructions `ADD` et `SUB` conservent le même nom.

Dans VNSim, les variables désignent des emplacements de mémoire. Pour enregistrer une valeur, on utilise donc par exemple `STORE W`, et non `STORE 8`.

### Exercice 4 – Construire et observer un programme

On souhaite calculer :

\[
(15+7)\times 2
\]

On dispose des variables suivantes :

| Variable | Valeur initiale |
|---|---:|
| X | 15 |
| Y | 7 |
| Z | 2 |
| W | 0 |

**1.** Écrire un programme VNSim permettant d'effectuer ce calcul et d'enregistrer le résultat dans `W`.
**2.** Avant de lancer le programme, prévoir le résultat final.
**3.** Exécuter le programme pas à pas (mettez pour cela la vitesse à 1500 ms). Après chaque instruction, relever la valeur de l'accumulateur et celle de `W`.

| Instruction exécutée | ACC | W |
|---|---:|---:|
| État initial | — | 0 |
| Première instruction | | |
| Deuxième instruction | | |
| Troisième instruction | | |
| Quatrième instruction | | |
| Cinquième instruction | | |

**4.** Recommencer en remplaçant `Y = 7` par `Y = 12`, sans modifier le programme. Quel est le nouveau résultat ?
**5.** Expliquer pourquoi le programme peut effectuer un calcul différent alors que ses instructions n'ont pas changé.

### Exercice 5 – Déboguer un programme

Un programmeur souhaite calculer la somme de trois valeurs et enregistrer le résultat dans la variable `W`.

Il écrit le programme suivant :

```asm
LOAD X
ADD Y
STORE W
ADD Z
HALT
```

Les variables sont initialisées ainsi :

| Variable | Valeur initiale |
|---|---:|
| X | 8 |
| Y | 4 |
| Z | 6 |
| W | 0 |

**1.** Sans lancer le programme, prévoir la valeur finale de l'accumulateur et celle de `W`.
**2.** Exécuter le programme pas à pas et compléter le tableau.

| Instruction exécutée | ACC | W |
|---|---:|---:|
| État initial | — | 0 |
| `LOAD X` | | |
| `ADD Y` | | |
| `STORE W` | | |
| `ADD Z` | | |
| `HALT` | | |

**3.** Le programme réalise-t-il correctement le calcul demandé ? Expliquer.
**4.** Corriger le programme pour que le résultat soit correctement enregistré.
**5.** Exécuter le programme corrigé et vérifier son fonctionnement.
**6.** Dans le programme initial, pourquoi l'accumulateur contient-il une valeur différente de celle enregistrée dans `W` à la fin de l'exécution ?