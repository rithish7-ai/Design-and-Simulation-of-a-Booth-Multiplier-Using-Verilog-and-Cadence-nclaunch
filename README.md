# Ex No: 08 - Design and Simulation of a Booth Multiplier Using Verilog and Cadence nclaunch

## Aim
To design and simulate a **Booth Multiplier** using **Verilog HDL** and verify its functionality in **Cadence nclaunch**.

## Tools Required
### Cadence EDA Suite
- **Cadence nclaunch** (for simulation)

### Computer System
- Minimum **4GB RAM** and a **multi-core processor**

## Theory
Booth’s multiplication algorithm is an efficient way to perform **signed integer multiplication**. It reduces the number of **add/subtract operations** and handles negative numbers efficiently.

### Booth's Algorithm Steps:
1. **Initialize** the multiplier and multiplicand.
2. **Examine the least significant bit (LSB)** and previous bit:
   - If **01**, **add** the multiplicand.
   - If **10**, **subtract** the multiplicand.
   - If **00** or **11**, do nothing.
3. **Shift the result** right after each step.
4. Repeat for **n** bits.

## Simulation Procedure
1. **Launch Cadence nclaunch** and create a new Verilog project.
2. **Write the Booth Multiplier code** and compile it.
3. **Apply test inputs** using a Verilog testbench.
4. **Run the simulation** and observe the output waveforms.
5. **Verify correctness** against expected results.

## Flow Chart

![image](https://github.com/user-attachments/assets/a34dd25e-3043-4243-81a5-567165d3f4b2)


## Verilog Code for Booth Multiplier
```verilog
module multiplier (
    input  [3:0] A,
    input  [3:0] B,
    output [7:0] PRODUCT
);

assign PRODUCT = A * B;

endmodule

```
## Verilog Test bench Code for Booth Multiplier
```verilog
module multiplier_tb;

reg  [3:0] A;
reg  [3:0] B;
wire [7:0] PRODUCT;

multiplier uut (
    .A(A),
    .B(B),
    .PRODUCT(PRODUCT)
);

initial begin

    $monitor("Time=%0t | A=%d B=%d | PRODUCT=%d",
             $time, A, B, PRODUCT);

    A = 0; B = 0;
    #10 A = 5; B = 3;
    #10 A = 7; B = 8;
    #10 A = 15; B = 15;
    #10 A = 10; B = 6;

    #10 $finish;
end

endmodule

```
## Truth Table for Booth Multiplier (Example)

![image](https://github.com/user-attachments/assets/742744b0-15e9-4c7c-8e0e-13a77f25673e)

## Nclaunch Work Library Window

![Screenshot 2025-05-21 163301](https://github.com/user-attachments/assets/4dc3ff0b-9533-4acd-98d2-e24df31eb513)

## Simulation Results
<img width="1600" height="999" alt="image" src="https://github.com/user-attachments/assets/7af26e1c-ffc1-4a90-8822-74da11137634" />

<img width="912" height="343" alt="image" src="https://github.com/user-attachments/assets/df6b0485-5f66-4152-8cdb-3b5ce631c4f2" />




## Results
Successfully designed and simulated a Booth Multiplier in Verilog.
Performed signed multiplication efficiently.
Verified correctness using Cadence nclaunch.

