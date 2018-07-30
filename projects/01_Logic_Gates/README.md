# Project 1 Logic Gates

Project link on nand2tetris official website: https://www.nand2tetris.org/project01.

## Objective
Build a set of logic gates in .hdl files and pass the tests in the hardware simulator.

## Thoughts
0. Nand
    * built-in gate.

1. [Not](files/Not.hdl)
    * Only one input, so feed the same value to the input pins of Nand gate.

2. [And](files/And.hdl)
    * The exact opposite to Nand.

3. [Or](files/Or.hdl)
    * Or: if not all 0 -> 1; Nand: if not all 1 -> 1.

4. [Xor](files/Xor.hdl)
    * If a and b differs -> 1; (a && ~b) || (~a && b).

5. [Mux](files/Mux.hdl)
    * If sel=0, then a, so (a && ~sel); If sel=1, then b, so (b && sel).

6. [DMux](files/DMux.hdl)
    * Similar idea to Mux, but no need for internal pins.

7. [Not16](files/Not16.hdl)
    * Use Not gate for each bit; No looping constructs in the HDL language, so have to repeat.

8. [And16](files/And16.hdl)
    * Use And gate for each bit pair; No looping constructs in the HDL language, so have to repeat.

9. [Or16](files/Or16.hdl)
    * Use Or gate for each bit pair; No looping constructs in the HDL language, so have to repeat.

10. [Mux16](files/Mux16.hdl)
    * Use Mux gate for each bit pair; No looping constructs in the HDL language, so have to repeat.

11. [Or8Way](files/Or8Way.hdl)
    * Use Or gate for adjacent bit pair.

12. [Mux4Way16](files/Mux4Way16.hdl)
    * (!) Hardware bits are numbered from right to left, starting with 0. So sel=01, sel[0]=1, sel[1]=0. 
    * Use Mux16 each time to select one of two multi-bit buses.

13. [Mux8Way16](files/Mux8Way16.hdl)
    * Use Mux4Wat16 each time to select one of four multi-bit buses.

14. [DMux4Way](files/DMux4Way.hdl)
    * Use DMux to separate 2 multi-bit buses into 2 subgroups with outputs indicating which subgroup is selected. Then use DMux with input pin being previous output flag (!) in each subgroup to find the one selected.

15. [DMux8Way](files/DMux8Way.hdl)
    * Same idea as DMux4Way.


