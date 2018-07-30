# Project 2 Combinational Chips

Project link on nand2tetris official website: https://www.nand2tetris.org/project02.

## Objective
Build a set of chips, leading up to an Arithmetic Logic Unit (ALU) of the Hack Computer.

## Thoughts:
1. [HalfAdder](files/HalfAdder.hdl)
    * Implement the algorithmic operation with logic operations observed from the truth table.
    
2. [FullAdder](files/FullAdder.hdl)
    * Two HalfAdder chips and then a Or chip for carries from two HalfAdder. *sum* is not affected by # of addtions.

3. [Add16](files/Add16.hdl)
    * Use FullAdder chip for each bit pair.

4. [Inc16](files/Inc16.hdl)
    * Use Add16 chip just implemented (!) as adding 1 is just a special case.

5. [ALU](files/ALU.hdl)
    1. Control bits: if 0, select x; if 1, select 0 -> Mux16.
    2. ng == MSB.
    3. zr: want to see if all bit equals 0 -> multi-way with Or.
