---
title: "learn about duration"
layout: "duration"
---
# Abs
Returns the absolute value of the given time.Duration value.

```
{{ $d := time.ParseDuration "-3h" }}
{{ $d.Abs }} → 3h0m0s

```
output:3h0m0s
___
# Hours
Returns the time.Duration value as a floating point number of hours.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Hours }} → 3.5420833333333333

```
3.5h → 12,600 seconds

2.5m → 150 seconds

1.5s → 1.5 seconds

→ Total = 12,600 + 150 + 1.5 = 12,751.5 seconds

12,751.5 seconds ÷ 3600 seconds/hour = 3.542083333... hours
___
# Microseconds
Returns the time.Duration value as an integer microsecond count.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}

{{ $d.Microseconds }} → 12751500000
```
3.5h → 12,600 seconds

2.5m → 150 seconds

1.5s → 1.5 seconds

→ Total = 12,600 + 150 + 1.5 = 12,751.5 seconds

12,751.5*1000*1000=12751500000
___
# Milliseconds
Returns the time.Duration value as an integer millisecond count.
```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Milliseconds }} → 12751500
```
3.5h → 12,600 seconds

2.5m → 150 seconds

1.5s → 1.5 seconds

→ Total = 12,600 + 150 + 1.5 = 12,751.5 seconds

12,751.5*1000=12751500
___
# Minutes
Returns the time.Duration value as a floating point number of minutes.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Minutes }} → 212.525
```
3.5h → 12,600 seconds

2.5m → 150 seconds

1.5s → 1.5 seconds

→ Total = 12,600 + 150 + 1.5 = 12,751.5 seconds

12,751.5/60=212.525
___

# Nanoseconds

Returns the time.Duration value as an integer nanosecond count.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Nanoseconds }} → 12751500000000

```
3.5h → 12,600 seconds

2.5m → 150 seconds

1.5s → 1.5 seconds

→ Total = 12,600 + 150 + 1.5 = 12,751.5 seconds

12,751.5\*1000\*1000\*1000=12751500000000
___
# Round
Returns the result of rounding DURATION1 to the nearest multiple of DURATION2.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}

{{ $d.Round (time.ParseDuration "2h") }} → 4h0m0s
{{ $d.Round (time.ParseDuration "3m") }} → 3h33m0s
{{ $d.Round (time.ParseDuration "4s") }} → 3h32m32s

```
# Seconds
Returns the time.Duration value as a floating point number of seconds.

```
Seconds
Returns the time.Duration value as a floating point number of seconds.
```
___
# Truncate
Returns the result of rounding DURATION1 toward zero to a multiple of DURATION2.

```
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}

{{ $d.Truncate (time.ParseDuration "2h") }} → 2h0m0s
{{ $d.Truncate (time.ParseDuration "3m") }} → 3h30m0s
{{ $d.Truncate (time.ParseDuration "4s") }} → 3h32m28s

```