# Cours 2 - Exécution des instructions par le processeur

Un programme informatique est constitué d'une succession d'instructions que le processeur doit exécuter. Nous avons vu dans le cours précédent que l'architecture de von Neumann stockait les instructions ET les données dans une même mémoire.

Mais comment le processeur sait-il quelle instruction exécuter ? Comment récupère-t-il les données nécessaires ? Et comment réalise-t-il les opérations demandées ?

Pour répondre à ces questions, nous allons étudier le fonctionnement interne du processeur à travers un modèle simplifié.

## 2.1. Du programme au langage machine

Les programmes informatiques sont généralement écrits dans des langages de programmation conçus pour être compréhensibles par les humains, comme Python ou C. Cependant, le processeur ne peut pas exécuter directement ces instructions : il ne comprend que des **instructions machine**, codées en binaire.

Il est donc nécessaire de traduire le programme avant son exécution.

### Les différents niveaux de langage

On peut distinguer plusieurs niveaux :

- **Les langages de programmation** (Python, C...) : ils permettent au programmeur d'écrire des instructions relativement faciles à comprendre et à manipuler.
- **Le langage assembleur** : il utilise des instructions symboliques proches des instructions réellement exécutées par le processeur. Par exemple, `LOAD`, `ADD` ou `STORE`.
- **Le langage machine** : il correspond aux instructions codées en binaire que le processeur est capable d'exécuter directement.

### La compilation

Un **compilateur** est un programme chargé de traduire le code source écrit dans un langage de programmation en instructions machine.

Par exemple, le programme suivant :

```python
a = 12
b = 7
c = a + b
```

peut être traduit en une succession d'instructions machine permettant notamment de charger les valeurs, de réaliser leur addition et de stocker le résultat.

Cette traduction produit un programme exécutable, qui peut ensuite être enregistré sur un support de stockage, comme un SSD.

Certains langages, comme Python, utilisent plutôt un interpréteur pour exécuter les programmes. Celui-ci prend en charge leur traduction et leur exécution.

### Le chargement en mémoire

Lorsqu'un programme est lancé, le système d'exploitation organise son chargement en mémoire vive (RAM). Le processeur peut alors récupérer les instructions du programme en mémoire et commencer leur exécution.

On retrouve ainsi le principe de l'architecture de von Neumann : **les instructions du programme et les données qu'il manipule sont stockées dans la mémoire centrale**.

**À retenir :** le programmeur écrit dans un langage de programmation, mais le processeur exécute des instructions machine codées en binaire. La compilation permet notamment de traduire un programme en instructions que le processeur peut exécuter.

## 2.2. Les registres du processeur

Le processeur dispose de petites zones de mémoire internes, très rapides, appelées **registres**. Ils permettent de conserver temporairement les informations nécessaires à l'exécution des instructions.

Nous allons nous intéresser à trois registres :

- **Le compteur ordinal (CO)** : il contient l'adresse de la prochaine instruction à exécuter. Il permet donc au processeur de savoir où poursuivre le programme.
- **Le registre accumulateur (ACC)** : il conserve temporairement une donnée ou un résultat sur lequel le processeur travaille. Il est notamment utilisé lors des opérations arithmétiques.
- **Le registre d'instruction (RI)** : il conserve l'instruction actuellement en cours de traitement, après sa récupération en mémoire.

Ces registres ont des rôles différents : le CO indique où trouver la prochaine instruction, le RI conserve l'instruction en cours et l'ACC contient une donnée ou un résultat utile à son exécution.

## 2.3. Le cycle d'exécution d'une instruction

Le processeur exécute les instructions d'un programme en répétant continuellement un cycle composé de trois grandes étapes :

1. **Recherche (Fetch)** : le processeur récupère en mémoire l'instruction située à l'adresse indiquée par le CO. Cette instruction est placée dans le RI. Le CO est ensuite avancé pour désigner l'instruction suivante.
2. **Décodage (Decode)** : l'unité de commande (UC) interprète l'instruction récupérée. Elle identifie l'opération à effectuer ainsi que les éventuelles données nécessaires, puis organise son exécution.
3. **Exécution (Execute)** : le processeur réalise l'opération demandée. Selon l'instruction, cela peut impliquer une lecture ou une écriture en mémoire, un calcul effectué par l'UAL ou encore une modification du CO.

Une fois l'instruction exécutée, le processeur recommence le cycle avec l'instruction suivante.

**À retenir :** ce cycle est souvent appelé cycle *recherche-décodage-exécution*. Il permet au processeur de traiter successivement les instructions d'un programme.

## 2.4. Jeu d'instructions et exécution d'un programme simple

Chaque processeur possède ce que l'on appelle un **jeu d'instructions** : il s'agit de l'ensemble des instructions qu'il comprend et qu'il est capable d'exécuter.

Cette année, nous considérons un processeur simplifié qui utilise le jeu d'instructions suivant :

| Instruction | Signification |
|---|---|
| `LOAD adresse` | Charge dans l'ACC la valeur située à l'adresse indiquée. |
| `ADD adresse` | Ajoute à l'ACC la valeur située à l'adresse indiquée. |
| `STORE adresse` | Écrit le contenu de l'ACC à l'adresse indiquée. |
| `SUB adresse` | Soustrait de l'ACC la valeur située à l'adresse indiquée. |
| `MULT adresse` | Multiplie le contenu de l'ACC par la valeur située à l'adresse indiquée. |
| `HALT` | Arrête le cycle d'exécution en cours. |

Ces instructions sont volontairement simplifiées : elles permettent de comprendre les mécanismes fondamentaux sans avoir à étudier le langage machine d'un véritable processeur.

Considérons le contenu suivant de la mémoire :

| Adresse | Contenu |
|---:|---|
| 0 | `LOAD 5` |
| 1 | `ADD 6` |
| 2 | `STORE 8` |
| 5 | `12` |
| 6 | `7` |
| 8 | `0` |

Les trois premières cases contiennent les instructions du programme. Les autres contiennent les données sur lesquelles il travaille.

Au départ, le CO vaut 0 et l'ACC ne contient aucune valeur utile.

### Première instruction : `LOAD 5`

Le processeur commence par récupérer l'instruction située à l'adresse 0 : `LOAD 5`.

- **Recherche :** le processeur récupère `LOAD 5` et la place dans le RI. Le CO passe à 1.
- **Décodage :** l'UC identifie une instruction de chargement et comprend qu'il faut récupérer la valeur située à l'adresse 5.
- **Exécution :** le processeur lit la mémoire à l'adresse 5 et transfère la valeur 12 dans l'ACC.

À la fin de cette instruction, l'ACC contient donc 12.

Attention : le processeur a effectué deux lectures distinctes en mémoire. La première lui a permis de récupérer l'instruction `LOAD 5`, tandis que la seconde lui a permis de récupérer la donnée 12 située à l'adresse 5.

### Deuxième instruction : `ADD 6`

Le processeur récupère maintenant l'instruction située à l'adresse 1 : `ADD 6`.

- **Recherche :** l'instruction est placée dans le RI et le CO passe à 2.
- **Décodage :** l'UC identifie une addition et comprend qu'il faut ajouter à l'ACC la valeur située à l'adresse 6.
- **Exécution :** le processeur récupère la valeur 7 à l'adresse 6. L'UAL effectue alors l'addition entre cette valeur et le contenu actuel de l'ACC.

On obtient :

`12 + 7 = 19`

Le résultat 19 est placé dans l'ACC.

### Troisième instruction : `STORE 8`

Le processeur récupère enfin l'instruction située à l'adresse 2 : `STORE 8`.

- **Recherche :** l'instruction est placée dans le RI et le CO passe à 3.
- **Décodage :** l'UC identifie une instruction de stockage et comprend qu'il faut écrire le contenu de l'ACC à l'adresse 8.
- **Exécution :** le processeur transmet la valeur 19 à la mémoire, qui l'écrit à l'adresse 8.

La mémoire contient désormais 19 à l'adresse 8.

### Bilan de l'exécution

Le programme a donc réalisé les opérations suivantes :

1. Charger la valeur 12 dans l'ACC.
2. Ajouter 7 à cette valeur.
3. Enregistrer le résultat 19 en mémoire.

On peut résumer l'évolution des principaux éléments :

| Étape | CO | Instruction | ACC | Mémoire[8] |
|---|---:|---|---:|---:|
| Initialisation | 0 | — | — | 0 |
| Après `LOAD 5` | 1 | `LOAD 5` | 12 | 0 |
| Après `ADD 6` | 2 | `ADD 6` | 19 | 0 |
| Après `STORE 8` | 3 | `STORE 8` | 19 | 19 |

Cet exemple illustre le rôle complémentaire des différents constituants du processeur :

- Le **CO** indique où récupérer la prochaine instruction.
- Le **RI** conserve l'instruction en cours de traitement.
- L'**UC** interprète l'instruction et coordonne les opérations.
- L'**UAL** effectue les calculs.
- L'**ACC** conserve les données et résultats intermédiaires.
- La **mémoire** fournit les instructions et les données, puis conserve les résultats qui doivent y être enregistrés.

## 2.5. Les instructions de saut

Jusqu'ici, notre programme a été exécuté dans l'ordre des adresses : 0, puis 1, puis 2. Mais il est possible de modifier cet ordre.

Une instruction de saut permet de modifier le contenu du CO afin de poursuivre l'exécution à une autre adresse.

Par exemple, l'instruction `JUMP 8` demande au processeur de poursuivre le programme à l'adresse 8. Au lieu de récupérer l'instruction suivante dans l'ordre habituel, le processeur ira donc chercher celle située à cette nouvelle adresse.

Les instructions de saut permettent notamment de construire des **boucles** et des **conditions**, indispensables à la programmation.

**À retenir :** le CO contient normalement l'adresse de l'instruction suivante. Une instruction de saut peut toutefois modifier cette adresse et ainsi changer l'ordre d'exécution du programme.

---

**Remarque sur le modèle étudié :** dans nos exemples, chaque instruction occupe une seule case mémoire et le CO augmente donc de 1 après chaque recherche (sauf en cas de saut). Sur les véritables processeurs, les instructions sont encodées en binaire et peuvent occuper plusieurs octets. Le déplacement du compteur ordinal dépend alors de la taille de l'instruction, et les mécanismes internes sont plus complexes.