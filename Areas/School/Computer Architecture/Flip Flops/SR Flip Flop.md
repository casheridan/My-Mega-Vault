### Truth Table for SR FF
| CLK | S   | R   | Q   | Q'  |
| --- | --- | --- | --- | --- |
| 0   | x   | x   | Q   | Q'  |
| 1   | 0   | 0   | Q   | Q'  |
| 1   | 0   | 1   | 0   | 1   |
| 1   | 1   | 0   | 1   | 0   |
| 1   | 1   | 1   | x   | x    |

##### <u>Terms:</u>
S = Set
R = Reset
S + R = 1: Jammed, set to 0
CLK: Clock

Rising Edge: When the electrical signal goes from LOW -> HIGH
Falling Edge: When electrical signal goes from HIGH -> LOW

Rising Sensitive: CLK value is 1 when Rising Edge occurs
Falling Sensitive: CLK value is 1 when Falling Edge occurs
Level Sensitive: CLK value is 1 during the duration of the HIGH

Timing Diagram Level Sensitive example:
![[SR Flip Flop.excalidraw]]