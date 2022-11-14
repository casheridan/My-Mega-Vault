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

<u>Asynchronous Counter</u>
We don't use universal clock, only first flip flop is driven by the main clock, and the clock input for the rest of flip flop io driven by the output of the previous Flip Flop.

<u>Synchronous Counter</u>
This has one global clock which derives each Flip Flop so the output changes in parallel.