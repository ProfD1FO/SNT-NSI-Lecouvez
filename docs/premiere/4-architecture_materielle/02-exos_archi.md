# Exercices 1 – Architecture de von Neumann

## Exercice 1 – Un ordinateur au travail

On souhaite utiliser un ordinateur pour ouvrir une photographie enregistrée sur un SSD, appliquer un filtre à cette image puis afficher le résultat à l'écran.

On rappelle que l'ordinateur possède notamment :
- un processeur composé d'une unité de contrôle, d'une UAL et de registres ;
- une mémoire vive (RAM) ;
- un SSD ;
- des périphériques d'entrée et de sortie.

1. Décrire le rôle du SSD et celui de la mémoire vive dans cette situation. Pourquoi l'image est-elle généralement chargée en RAM avant d'être traitée ?
2. Quel composant réalise les opérations mathématiques nécessaires à l'application du filtre ?
3. Quel est le rôle de l'unité de contrôle pendant le traitement ?
4. Les instructions du programme de traitement sont-elles stockées dans le SSD, dans la RAM ou dans les deux ? Expliquer leur parcours avant leur exécution.
5. Un élève affirme : « Le processeur contient le programme de traitement puisqu'il l'exécute. » Expliquer pourquoi cette affirmation est incorrecte.

## Exercice 2 – Une mémoire à explorer

On considère une mémoire centrale simplifiée composée de 16 cellules. Chaque cellule contient un octet et possède une adresse codée sur 4 bits.

Voici un **extrait** de cette mémoire :

| Adresse | Contenu |
|:---:|:---:|
| `0000` | `00101101` |
| `0001` | `11100010` |
| `0010` | `01010101` |
| `0011` | `10011001` |
| `0100` | `00001111` |
| `0101` | `11001100` |
| `0110` | `10101010` |
| `0111` | `00000001` |

1. Expliquer pourquoi une adresse est nécessaire pour accéder à une cellule mémoire.
2. Quelle est la plus grande adresse que cette mémoire peut utiliser ? Donner sa valeur en binaire.
3. Un programme souhaite lire le contenu de l'adresse `0101`. Quelle valeur récupère-t-il ? Combien cela vaut-il en base 10?
4. On souhaite remplacer le contenu de l'adresse `0010` par `11111111`. Combien de bits sont modifiés dans cette cellule ?
5. Un camarade affirme : « Comme les adresses sont codées sur 4 bits, chaque cellule ne peut contenir que 4 bits. » Expliquer son erreur.

## Exercice 3 – Enquête sur une panne

Un ordinateur rencontre plusieurs problèmes. Pour chaque situation, identifier le constituant ou le type de bus principalement concerné et justifier la réponse.

**Situation A :** Le processeur effectue correctement les opérations de lecture, mais les données récupérées depuis la mémoire sont erronées.

**Situation B :** Le processeur reçoit bien les données de la mémoire, mais il ne parvient pas à effectuer une addition.

**Situation C :** Le processeur souhaite lire le contenu de la cellule d'adresse 12. Pourtant, l'adresse transmise par le processeur n'arrive pas correctement jusqu'à la mémoire. Celle-ci reçoit une adresse différente de celle demandée.

**Situation D :** Le processeur et la mémoire sont capables de fonctionner, mais les opérations de lecture et d'écriture ne sont pas correctement distinguées.

1. Pour chaque situation, identifier le composant ou le bus susceptible d'être défectueux parmi : UAL, bus de données, bus d'adresses, bus de contrôle.
2. Expliquer le rôle de chacun de ces quatre éléments.
3. Pour la situation C, décrire les informations que le processeur doit transmettre à la mémoire pour réaliser une lecture.

## Exercice 4 – Le principe du programme enregistré


Un ordinateur possède deux programmes : un programme qui calcule la moyenne de plusieurs nombres et un autre qui trie une liste de nombres.

1. Pourquoi les deux programmes de la l'ordinateur peuvent-ils être exécutés quand on le souhaite sans avoir besoin de changer le matériel?
2. Où les instructions de ces programmes sont-elles stockées avant leur exécution ? Et pendant ?
3. Dans l'architecture de von Neumann, les instructions et les données sont-elles stockées dans des mémoires de nature différente ? Justifier.
4. Existe t-il d'autres types d'architectures que celle de von Neumann ? Cherchez et donnez des exemples.