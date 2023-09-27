# Boolean calcul

## Operator

### Or (addition)

Noted `a + b`

| a | b | R |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

### And (multiplication)

Noted `a.b` or `ab`

| a | b | R |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

### complement (not)
                                                            
Invert of a boolean specify with a dash above the variable: ā

| a | ā |
|---|---|
| 0 | 1 |
| 1 | 0 |

## Properties

### Neutral element

Element that does not influence the result.

- or (addition):        `0` because `a + 0 = a`
- and (multiplication): `1` because `a * 1 = a`

### Absorbing element

Element that make an operation equal to itself.

- or (addition):        `1` because `a + 1 = 1`
- and (multiplication): `0` because `a * 0 = 0`

### Absorbing with the complement

- or (addition):        `a + ā = 1`
- and (multiplication): `a.ā = 0`

### Indenpotence

- or: `a + a = a`
- and: `a.a = a`

### Commutative law

a + b = b + a
a.b = b.a

### Associative law

(a + b) + c = a + (b + c)
(ab)c = a(bc)

### Distributive law

a(b + c) = ab + ac
ab + ac = a(b + c)
