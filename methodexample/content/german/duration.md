---
title: "Lerne über Dauer"
layout: "duration"
---

# Abs
Gibt den absoluten Wert des angegebenen time.Duration-Werts zurück.

```
{{ $d := time.ParseDuration "-3h" }}
{{ $d.Abs }} → 3h0m0s
```
Ausgabe: 3h0m0s
___

# Stunden
Gibt den time.Duration-Wert als Fließkommazahl in Stunden zurück.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Hours }} → 3.5420833333333333
```
3,5h → 12.600 Sekunden  
2,5m → 150 Sekunden  
1,5s → 1,5 Sekunden  
→ Gesamt = 12.600 + 150 + 1,5 = 12.751,5 Sekunden  
12.751,5 Sekunden ÷ 3600 Sekunden/Stunde = 3,542083333... Stunden
___

# Mikrosekunden
Gibt den time.Duration-Wert als ganze Zahl in Mikrosekunden zurück.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Microseconds }} → 12751500000
```
12.751,5 * 1.000.000 = 12.751.500.000
___

# Millisekunden
Gibt den time.Duration-Wert als ganze Zahl in Millisekunden zurück.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Milliseconds }} → 12751500
```
12.751,5 * 1.000 = 12.751.500
___

# Minuten
Gibt den time.Duration-Wert als Fließkommazahl in Minuten zurück.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Minutes }} → 212.525
```
12.751,5 / 60 = 212,525
___

# Nanosekunden
Gibt den time.Duration-Wert als ganze Zahl in Nanosekunden zurück.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Nanoseconds }} → 12751500000000
```
12.751,5 * 1.000.000.000 = 12.751.500.000.000
___

# Runden (Round)
Gibt das Ergebnis des Rundens von DURATION1 auf das nächste Vielfache von DURATION2 zurück.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}

{{ $d.Round (time.ParseDuration "2h") }} → 4h0m0s
{{ $d.Round (time.ParseDuration "3m") }} → 3h33m0s
{{ $d.Round (time.ParseDuration "4s") }} → 3h32m32s
```
___

# Sekunden
Gibt den time.Duration-Wert als Fließkommazahl in Sekunden zurück.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Seconds }} → 12751.5
```
___

# Abschneiden (Truncate)
Gibt das Ergebnis des Abschneidens von DURATION1 auf ein Vielfaches von DURATION2 in Richtung Null zurück.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}

{{ $d.Truncate (time.ParseDuration "2h") }} → 2h0m0s
{{ $d.Truncate (time.ParseDuration "3m") }} → 3h30m0s
{{ $d.Truncate (time.ParseDuration "4s") }} → 3h32m28s
```