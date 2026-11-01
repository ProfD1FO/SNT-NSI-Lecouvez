---
geometry: margin=2.4cm
---

# Correction - Exercices 1 : Les bases de nombres

## Exercice 1 - Décomposer en décimal

### Q1

- $31 = 3 \times 10^1 + 1 \times 10^0$
- $613 = 6 \times 10^2 + 1 \times 10^1 + 3 \times 10^0$
- $3 = 3 \times 10^0$
- $1726 = 1 \times 10^3 + 7 \times 10^2 + 2 \times 10^1 + 6 \times 10^0$
- $19293 = 1 \times 10^4 + 9 \times 10^3 + 2 \times 10^2 + 9 \times 10^1 + 3 \times 10^0$

### Q2

- $1 \times 10^2 + 0 \times 10^1 + 8 \times 10^0 = 108$
- $8 \times 10^3 + 9 \times 10^2 + 1 \times 10^1 + 0 \times 10^0 = 8910$
- $4 \times 10^1 + 8 \times 10^0 = 48$
- $1 \times 10^4 + 1 \times 10^3 + 9 \times 10^2 + 5 \times 10^1 + 7 \times 10^0 = 11957$

## Exercice 2 - Décomposer en base 2

### Q1

- $111_2 = 1 \times 2^2 + 1 \times 2^1 + 1 \times 2^0$
- $10001_2 = 1 \times 2^4 + 1 \times 2^0$
- $10101_2 = 1 \times 2^4 + 1 \times 2^2 + 1 \times 2^0$
- $1_2 = 1 \times 2^0$
- $100_2 = 1 \times 2^2$

### Q2

- $111_2 = 7$
- $10001_2 = 17$
- $10101_2 = 21$
- $1_2 = 1$
- $100_2 = 4$

## Exercice 3 - Nombres possibles

- $91_7$ : invalide
- $2013_2$ : invalide
- $10_2$ : valide
- $FFFF_{16}$ : valide
- $G12_{16}$ : invalide
- $12_8$ : valide

## Exercice 4 - Les autres bases

- $36_7 = 3 \times 7^1 + 6 \times 7^0 = 27$
- $1001_2 = 1 \times 2^3 + 1 \times 2^0 = 9$
- $A3_{16} = 10 \times 16^1 + 3 \times 16^0 = 163$
- $121_9 = 1 \times 9^2 + 2 \times 9^1 + 1 \times 9^0 = 100$

# Correction - Exercices 2 : Passer en binaire

## Exercice 1 - Décomposition

### Q1

$2^0 = 1$

$2^1 = 2$

$2^2 = 4$

$2^3 = 8$

$2^4 = 16$

$2^5 = 32$

$2^6 = 64$

$2^7 = 128$

$2^8 = 256$

### Q2

- $11 = 8 + 2 + 1 = 2^3 + 2^1 + 2^0$
- $35 = 32 + 2 + 1 = 2^5 + 2^1 + 2^0$
- $81 = 64 + 16 + 1 = 2^6 + 2^4 + 2^0$
- $201 = 128 + 64 + 8 + 1 = 2^7 + 2^6 + 2^3 + 2^0$
- $404 = 256 + 128 + 16 + 4 = 2^8 + 2^7 + 2^4 + 2^2$

### Q3

- $11 = 1011_2$
- $35 = 100011_2$
- $81 = 1010001_2$
- $201 = 11001001_2$
- $404 = 110010100_2$

## Exercice 2 - Divisions par 2 successives

### Q1

- $66 = 1000010_2$
- $139 = 10001011_2$
- $417 = 110100001_2$
- $6131 = 1011111110011_2$
- $10000 = 10011100010000_2$

### Q2

- $1000010_2 = 66$
- $10001011_2 = 139$
- $110100001_2 = 417$
- $1011111110011_2 = 6131$
- $10011100010000_2 = 10000$

## Exercice 3 - Programmation de la méthode

```python
def divisions_par_2(nombre):
    restes = ""

    while nombre != 0:
        restes = str(nombre % 2) + restes
        nombre = nombre // 2

    return restes
```

# Correction - Exercices 3 : Entiers relatifs en complément à deux
## Exercice 1 - Décimal vers complément à deux
1. $-5$

$5 = 00000101$

Inversion : $11111010$

Ajout de $1$ : $11111011$

Donc $-5 = 11111011$

2. $-12$

$12 = 00001100$

Inversion : $11110011$

Ajout de $1$ : $11110100$

Donc $-12 = 11110100$

3. $-27$

$27 = 00011011$

Inversion : $11100100$

Ajout de $1$ : $11100101$

Donc $-27 = 11100101$

4. $-42$

$42 = 00101010$

Inversion : $11010101$

Ajout de $1$ : $11010110$

Donc $-42 = 11010110$

5. $-73$

$73 = 01001001$

Inversion : $10110110$

Ajout de $1$ : $10110111$

Donc $-73 = 10110111$

Exercice 2 - Complément à deux vers décimal

$11111011 = -5$

$11110000 = -16$

$11010111 = -41$

$10111101 = -67$

$10000001 = -127$

Exercice 3 - Vérifier avec une addition

1.

$00000101 + 11111011 = 00000000$

Donc $5 + (-5) = 0$

2.

$00001100 + 11110100 = 00000000$

Donc $12 + (-12) = 0$

3.

$00100001 + 11011111 = 00000000$

Donc $33 + (-33) = 0$

Exercice 4 - Maîtrise
1.

$18 = 00010010$

Inversion : $11101101$

Ajout de $1$ : $11101110$

Donc $-18 = 11101110$

2.

$11100110 = -26$

3.

$64 = 01000000$

Inversion : $10111111$

Ajout de $1$ : $11000000$

Donc $-64 = 11000000$

4.

Sur 8 bits, l'intervalle est :

$[-128 ; 127]$

5.

Le nombre de bits doit être fixé car il détermine le nombre de valeurs représentables et donc l'intervalle des nombres possibles.
