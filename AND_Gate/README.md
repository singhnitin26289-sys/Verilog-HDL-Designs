# AND Gate using Verilog

## Overview
This project implements a basic 2-input AND gate using Verilog HDL. It is part of my journey to learn Digital Design and ASIC Verification.

## Logic Description
An AND gate produces a HIGH output (1) only when both inputs are HIGH (1). Otherwise, the output remains LOW (0).

## Truth Table

| Input A | Input B | Output Y |
|:-------:|:-------:|:--------:|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

## Verilog Code

```verilog
module and_gate (
    input A,
    input B,
    output Y
);

assign Y = A & B;

endmodule
```

## Testbench
A testbench is used to verify all possible input combinations.

```verilog
module and_gate_tb;

reg A, B;
wire Y;

and_gate uut (
    .A(A),
    .B(B),
    .Y(Y)
);

initial begin
    $monitor("A=%b B=%b Y=%b", A, B, Y);

    A=0; B=0; #10;
    A=0; B=1; #10;
    A=1; B=0; #10;
    A=1; B=1; #10;

    $finish;
end

endmodule
```

## Simulation Tools
- Verilog HDL
- Icarus Verilog
- GTKWave
- Visual Studio Code
- Ubuntu (WSL)

## Expected Output

```text
A=0 B=0 Y=0
A=0 B=1 Y=0
A=1 B=0 Y=0
A=1 B=1 Y=1
```

## Learning Outcomes
- Understanding basic logic gates.
- Learning Verilog module structure.
- Understanding continuous assignments.
- Writing and running a testbench.
- Verifying digital logic through simulation.

## Author
Nitin Singh

Electronics Engineering Student  
Interested in VLSI Design and ASIC Verification.