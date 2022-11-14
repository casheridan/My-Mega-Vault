## Introduction 
---
The SR Latch, or Set-Reset Latch is a small logic circuit that takes two inputs: S (Set) and R (Reset); it also produces two outputs: Q and Q'.


## Circuit Diagram
---
``` circuitjs
$ 64 0.000005 1.0312258501325766 50 5 50 5e-11
151 240 256 272 256 0 2 5 5
151 240 352 272 352 0 2 5 5
w 240 272 240 288 0
w 240 336 240 320 0
w 272 352 272 320 0
w 272 256 272 288 0
w 272 288 240 320 0
w 240 288 272 320 0
M 272 352 304 352 2 2.5
M 272 256 304 256 2 2.5
L 240 240 208 240 2 0 false 5 0
L 240 368 208 368 2 0 false 5 0

```

## Timing Diagram
---
