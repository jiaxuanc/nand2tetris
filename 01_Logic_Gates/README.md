# Project 1 Logic Gates

Project link on nand2tetris official website: https://www.nand2tetris.org/project01.

## Objective
Build a set of logic gates in .hdl files and pass the tests in the hardware simulator.

## Thoughts
0. Nand
  * built-in

1. Not
  * Only one input, so feed the same value to the input pins of Nand gate.

2. And
  * The exact opposite to Nand.

3. Or
  * Or: if not all 0 -> 1; Nand: if not all 1 -> 1.

4. Xor
  * If a and b differs -> 1; (a && ~b) || (~a && b).

5. Mux
  * If sel=0, then a, so (a && ~sel); If sel=1, then b, so (b && sel).

6. DMux
  * Similar idea to Mux, but no need for internal pins.

7. Not16
  * Use Not gate for each bit; No for loop can be used, so have to repeat.

8. And16
  * Use And gate for each bit pair; No for loop can be used, so have to repeat.

9. Or16
  * Use Or gate for each bit pair; No for loop can be used, so have to repeat.

10. Mux16
  * Use Mux gate for each bit pair; No for loop can be used, so have to repeat.

11. Or8Way
  * Use Or gate for adjacent bit pair.

12. Mux4Way16
  * (!) Hardware bits are numbered from right to left, starting with 0. So sel=01, sel[0]=1, sel[1]=0. 
  * Use Mux16 each time to select one of two multi-bit buses.

13. Mux8Way16
  * Use Mux4Wat16 each time to select one of four multi-bit buses.

14. DMux4Way
  * Use DMux to separate 2 multi-bit buses into 2 subgroups with outputs indicating which subgroup is selected. Then use DMux with input pin being previous output flag (!) in each subgroup to find the one selected.

15. DMux8Way
  * Same idea as DMux4Way


