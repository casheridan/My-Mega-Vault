## Introduction 
---
The SR Latch, or Set-Reset Latch is a small logic circuit that takes two inputs: S (Set) and R (Reset) and produces two outputs: Q and Q'

When Set is 1 then 


## Circuit Diagram
---
``` circuitjs
$ 64 0.000005 1.0312258501325766 50 5 50 5e-11
151 240 192 272 192 0 2 0 5
151 240 288 272 288 0 2 0 5
w 240 208 240 224 0
w 240 272 240 256 0
w 272 288 272 256 0
w 272 192 272 224 0
w 272 224 240 256 0
w 240 224 272 256 0
M 272 288 304 288 2 2.5
M 272 192 304 192 2 2.5
L 240 176 208 176 2 0 false 5 0
L 240 304 208 304 2 0 false 5 0

```

## Timing Diagram
---
