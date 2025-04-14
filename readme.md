# I. Design Title

Design and Implementation of a Simple CPU Simulator

# II. Design Requirements

- The address bus and data bus of the memory are both 16 bits wide.
- Input requirements: Input via a text box on the interface; or file input from the file `test.data` for assembly execution.
- Output requirements: The simulator records the values of the main CPU registers, bus values in each cycle in a `.txt` file. After program execution, the content of the data memory is recorded in a `.txt` file. The interface should also display the information.
- Basic functionality: Complete the serial execution process description of the basic instructions of the textbook model machine. Decompose instructions into micro-instructions. Visualize the instruction execution process. The addressing mode is only register addressing (`000`).
- Extended functionality 1: Integrate addition, subtraction, and multiplication into the existing content.

# III. Design Process

This project consists of 12 modules, as shown in Figure 1:

![image-20250414140715640](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646824.png)

**Figure 1**

As shown in the figure, the 12 modules are:

[1] **Assembly Instruction Text Box**

Assembly instructions are input here either by typing or importing a file. After the instruction input is complete, click "Execute." The model machine will convert the assembly instructions into binary code and store them in the machine code text box on the right. The conversion is done through string recognition in the code, as shown in Figure 2.

![image-20250414140731421](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646825.png)

**Figure 2**

[2] **Machine Code Text Box**

This text box stores machine code, which is input in groups of four bits with spaces in between.

[3] **Register Group Interface**

This interface visually demonstrates the specific operations on registers during instruction execution in the model machine by showing changes in register values. When the values in the model machine's visualization interface change, the defined synchronization method is called to update the register group values, ensuring data consistency, as shown in Figure 3.

![image-20250414140743843](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646826.png)

**Figure 3**

[5] **Model Machine Visualization Interface**

This interface is the core of the model machine project. It visually highlights the flow of data within the machine, controlled by a sequence of micro-commands. The diagram is drawn using Visio, with text boxes placed at important registers. These text boxes highlight changes in values, as shown in Figure 4.

![image-20250414140802153](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646827.png)

**Figure 4**

[6] **Instruction Storage Unit**

Controlled by the `ListView` control, this unit stores the machine code converted from assembly instructions. `IAD` represents the instruction address, and `IValue` represents the instruction, as shown in Figure 5.

![image-20250414140813205](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646828.png)

**Figure 5**

[7] **Micro-Command Sequence Record**

This section stores the micro-command sequence, which determines the data flow in the model machine's visualization interface. The micro-command sequence is identified through string recognition. The assembly instructions are recognized and then decomposed into a micro-command sequence. When the model machine's visualization interface executes, the micro-command sequence here is updated synchronously, as shown in Figure 6.

![image-20250414140822454](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646829.png)

**Figure 6**

[8] **Control Storage Unit**

This section stores the micro-instructions composed of the micro-command sequence. When the model machine's visualization interface runs, the currently executing micro-instruction is highlighted here, as shown in Figure 7.

![image-20250414140831076](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646830.png)

**Figure 7**

[9] **Binary Conversion Interface**

This interface is used for number system conversion. It can convert decimal numbers to binary, including original code, one's complement, and two's complement. The number of bits can be selected as either 8 or 16. The sign bit can also be chosen. This interface can be called during the execution of assembly instructions to assist with calculations, as shown in Figure 8.

![image-20250414140838884](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646831.png)

**Figure 8**

[10] **Multiplication Visualization Interface**

This interface simulates the shift operations in multiplication, visually demonstrating the specific logical operations of multiplication within the model machine, as shown in Figure 9.

![image-20250414140849466](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646832.png)

**Figure 9**

[11] **Process Display Interface**

This interface displays the process of arithmetic operations, including addition, subtraction, multiplication, etc., as shown in Figure 10.

![image-20250414140857056](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646833.png)

**Figure 10**

[12] **Arithmetic Functions**

This function group consists of multiple arithmetic operations, including addition, subtraction, multiplication, etc. Each operation is visually demonstrated, and the results are displayed in the result interface, as shown in Figure 11.

![image-20250414140906242](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646834.png)

**Figure 11.1**

![image-20250414140915022](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646835.png)

**Figure 11.2 Addition**

![image-20250414140925787](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646836.png)

**Figure 11.3 Multiplication**

![image-20250414140935167](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646837.png)

**Figure 11.4 Carry-Lookahead Addition**

![image-20250414140941527](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646838.png)

**Figure 11.5 Two's Complement Addition**

[13] **Speed Control Function**

This function controls the execution interval of the model machine. Users input a value, and the model machine's execution interval is determined by this value, catering to different users' needs, as shown in Figure 12.

![image-20250414140950633](https://raw.githubusercontent.com/stingo1218/pic/main/pic/20250414182646839.png)

**Figure 12**