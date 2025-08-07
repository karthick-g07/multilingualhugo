---
title: "apprendre la durée"
layout: "duration"
---

# Abs
Renvoie la valeur absolue de la valeur time.Duration donnée.

```
{{ $d := time.ParseDuration "-3h" }}
{{ $d.Abs }} → 3h0m0s
```
sortie : 3h0m0s
___

# Heures
Renvoie la valeur time.Duration en nombre à virgule flottante d'heures.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Hours }} → 3.5420833333333333
```
3,5h → 12 600 secondes  
2,5m → 150 secondes  
1,5s → 1,5 secondes  
→ Total = 12 600 + 150 + 1,5 = 12 751,5 secondes  
12 751,5 secondes ÷ 3600 secondes/heure = 3,542083333... heures
___

# Microsecondes
Renvoie la valeur time.Duration en nombre entier de microsecondes.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Microseconds }} → 12751500000
```
12 751,5 * 1 000 000 = 12 751 500 000
___

# Millisecondes
Renvoie la valeur time.Duration en nombre entier de millisecondes.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Milliseconds }} → 12751500
```
12 751,5 * 1 000 = 12 751 500
___

# Minutes
Renvoie la valeur time.Duration en nombre à virgule flottante de minutes.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Minutes }} → 212.525
```
12 751,5 / 60 = 212,525
___

# Nanosecondes
Renvoie la valeur time.Duration en nombre entier de nanosecondes.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Nanoseconds }} → 12751500000000
```
12 751,5 * 1 000 000 000 = 12 751 500 000 000
___

# Arrondir (Round)
Renvoie le résultat de l'arrondi de DURATION1 au multiple le plus proche de DURATION2.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}

{{ $d.Round (time.ParseDuration "2h") }} → 4h0m0s
{{ $d.Round (time.ParseDuration "3m") }} → 3h33m0s
{{ $d.Round (time.ParseDuration "4s") }} → 3h32m32s
```
___

# Secondes
Renvoie la valeur time.Duration en nombre à virgule flottante de secondes.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Seconds }} → 12751.5
```
___

# Tronquer (Truncate)
Renvoie le résultat de l'arrondi de DURATION1 vers zéro à un multiple de DURATION2.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}

{{ $d.Truncate (time.ParseDuration "2h") }} → 2h0m0s
{{ $d.Truncate (time.ParseDuration "3m") }} → 3h30m0s
{{ $d.Truncate (time.ParseDuration "4s") }} → 3h32m28s
```