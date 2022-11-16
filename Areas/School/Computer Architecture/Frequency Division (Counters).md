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

[[Designing a Multi-Bit Synchronous Counter]]
