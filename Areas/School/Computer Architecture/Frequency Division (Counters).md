## Introduction
---
A counter is a device that stores the number of times a particular event or process has occured. Often in relationship with a clock. For example: UP counter increases count for every rising edge of the clock.

Counters are used for frequency division. The main properties of a counter are timing, sequencing, and counting.

Counters work in two modes:
- UP
- DOWN

There are two categories of counters:
1. Asynchronous Counter
2. Synchronous Counter

### Asynchronous Counter
We don't use universal clock, only first flip flop is driven by the main clock, and the clock input for the rest of flip flop io driven by the output of the previous Flip Flop.

<u>Circuit Diagram</u>
``` circuitjs
$ 64 0.000005 4.818269829109882 50 5 50 5e-11
156 80 224 128 224 0 0
156 192 224 208 224 0 0
156 416 224 448 224 0 0
156 304 224 368 224 0 0
w 176 224 176 256 0
w 176 256 192 256 0
w 288 224 288 256 0
w 288 256 304 256 0
w 400 224 400 256 0
w 400 256 416 256 0
L 304 192 304 160 2 1 false 5 0
w 80 224 80 192 0
w 192 224 192 192 0
w 192 288 192 224 0
w 304 288 304 224 0
w 416 288 416 224 0
w 304 224 304 192 0
w 416 224 416 192 0
w 80 192 192 192 0
w 416 192 304 192 0
w 192 192 304 192 0
R 80 256 48 256 1 2 100 2.5 2.5 0 0.5
w 80 224 80 288 0

```

### Synchronous Counter
This has one global clock which derives each Flip Flop so the output changes in parallel.

<u>Excitation Table</u>

| Qn  | Qn+1 | J   | K   |
| --- | ---- | --- | --- |
| 0   | 0    | 0   | x   |
| 0   | 1    | 1   | x   |
| 1   | 0    | x   | 1   |
| 1   | 1    | x   | 0   |

| J   | K   | Q   | Q'  |
| --- | --- | --- | --- |
| 0   | 0   | Q   | Q'  |
| 0   | 1   | 0   | 1   |
| 1   | 0   | 1   | 0   |
| 1   | 1   | Qn' | Qn  |

<u>Next State Diagram</u>
| Present State               | Next State | Outputs |
| --------------------------- | ---------- | ------- |
| Q<sub>2</sub> Q<sub>1</sub> |            |         |

<u>K-map</u>


<u>Circuit Diagram (4 bit counter)</u>
``` circuitjs
$ 64 0.000005 10.20027730826997 50 5 50 5e-11
L -48 208 -48 176 2 1 false 5 0
R -16 336 -64 336 1 2 100 2.5 2.5 0 0.5
156 416 208 464 208 10 0
156 272 208 320 208 10 0
156 128 208 176 208 10 0
156 -16 208 32 208 10 0
w -48 304 96 304 0
w 96 304 240 304 0
w 240 304 384 304 0
w 384 304 528 304 0
w 512 240 528 240 0
w 368 240 384 240 0
w 224 240 240 240 0
w 80 240 96 240 0
w 96 240 96 304 0
w 240 240 240 304 0
w 384 240 384 304 0
w 528 240 528 304 0
w -48 208 -32 208 0
w -32 208 -32 272 0
w -32 272 -16 272 0
w -32 208 -16 208 0
w -48 208 -48 304 0
w 80 208 112 208 0
w 112 208 112 272 0
w 112 272 128 272 0
w 112 208 128 208 0
w 368 208 368 112 0
150 240 128 256 128 0 2 0 5
w 224 144 240 144 0
w 240 112 128 112 0
w 128 112 128 208 0
w 256 128 272 128 0
w 272 128 272 208 0
w 272 208 256 208 0
w 256 208 256 272 0
w 256 272 272 272 0
w 128 112 128 80 0
150 384 96 400 96 0 3 0 5
w 128 80 384 80 0
w 400 96 416 96 0
w 416 96 416 208 0
w 416 208 400 208 0
w 400 208 400 272 0
w 400 272 416 272 0
w 368 112 384 112 0
w 384 96 320 96 0
w 320 96 320 176 0
w 320 176 224 176 0
w 224 176 224 208 0
w 224 176 224 144 0
M 512 208 544 208 2 2.5
w -16 336 -16 240 0
w -16 336 128 336 0
w 128 336 272 336 0
w 272 336 416 336 0
w 416 240 416 336 0
w 272 240 272 336 0
w 128 240 128 336 0

```

<u>Tinkercad Example</u>
![[Screenshot 2022-11-15 014408.png]]

``` circuitjs
$ 64 0.000005 3.1763992386181834 50 5 50 5e-11
156 160 224 224 224 4 0
156 304 224 432 224 4 5
M 400 224 416 224 2 2.5
R 128 352 80 352 1 2 100 2.5 2.5 0 0.5
w 128 352 272 352 0
w 272 352 272 256 0
w 272 256 304 256 0
w 160 256 128 256 0
w 128 256 128 352 0
w 160 224 160 288 0
w 160 224 160 192 0
w 160 192 256 192 0
w 304 224 304 288 0
L 304 224 304 160 2 1 false 5 0
w 256 224 256 192 0
M 256 224 272 224 2 2.5
```


