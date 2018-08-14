# Project 3 Sequential Chips

Project link on nand2tetris official website: https://www.nand2tetris.org/project03.

## Objective
> Build all the chips described in Chapter 3, leading up to a Random Access Memory (RAM) unit. The only building blocks that you can use are primitive DFF gates, chips that you will build on top of them, and chips described in previous chapters.

## Thoughts:
0. DFF
    * Primitive

1. [Bit](files/a/Bit.hdl)
    * Implement for two chips in the diagram, not considering uninitialized variables.
    * > The reason that the chip still works is that HDL is a hardware description language (also known as a "declarative" language). It describes the wiring connections that are needed to make the chip, not how it operates once power is applied. It makes no difference what order the parts are put into a circuit board. As long as all the parts get placed and connected together correctly, the circuit board will function. The Hardware Simulator "applies the power" and tests how the chip functions. An important aspect of this is that there is no such thing as an "uninitialized variable" in HDL. If a wire is connected to an output somewhere in the HDL, it can be connected to any input. This is particularly important to understand for Chapter 3. (http://nand2tetris.org/software/HDL%20Survival%20Guide.html)

2. [Register](files/a/Register.hdl)
    * Just use Bit for each bit in the array.

3. [RAM8](files/a/RAM8.hdl)
    * Need to have 8 registers updated correctly before outputting the selected register value -> DMux8Way to pass *load* to the selected register (others get 0, so won't change value)

4. [RAM64](files/a/RAM64.hdl)
    * Same idea as RAM8.

5. [RAM512](files/b/RAM512.hdl)
    * Same idea as RAM8.

6. [RAM4K](files/b/RAM4K.hdl)
    * Same idea as RAM8.

7. [RAM16K](files/b/RAM16K.hdl)
    *  Same idea as RAM8.

8. [PC](files/a/PC.hdl)
    * 4 conditions -> 3 Mux16; priority (most to least): reset, load, inc.
    * Then put the processed output into Register
    * (!) Note that PC should output from the Register 
    > Outputting from other chips does not guarantee immediate storage and input after an output is made: the input may be made at the same time of storage, which would mess up the clock cycle. The output and storage of output must occur at the same time. (By Aditya Gomatam, extracted from https://www.coursera.org/learn/build-a-computer/discussions/weeks/3/threads/Di7gv-qREeeelw5rF-0c1g).
    * <img src="PC_diagram.jpeg">
    (Drawn by Bjorn Inge Westerheim, see https://www.coursera.org/learn/build-a-computer/discussions/all/threads/UVIv7X38EeaEYRLxIcdkdQ/replies/LDEa8n6DEea3IA7ABe4oxQ).

