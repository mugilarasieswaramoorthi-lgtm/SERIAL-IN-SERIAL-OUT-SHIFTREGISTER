# SERIAL-IN-SERIAL-OUT-SHIFTREGISTER

**AIM:**

To implement  SISO Shift Register using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**SISO shift Register**

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

![image](https://github.com/naavaneetha/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/154305477/e81c4072-37f9-46c6-8145-566764b74c3a)

Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next.
Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

**Procedure**
1.Connect clock to the shift register to control shifting.

2.Apply serial input (1-bit at a time) at the input terminal.

3.Enable the shift register (if enable pin exists).

4.On each positive/negative clock edge, the input bit is shifted into the first flip-flop.

5.The existing bits shift one position right at every clock pulse.

6.The bit stored in the last flip-flop appears at the serial output (S0).

7.Continue applying clock pulses to shift out all stored bits serially.


**PROGRAM**
module shift_register_3bit (
    input  wire clk,     // clock input
    input  wire rst,     // synchronous reset
    input  wire serial_in, // serial data input
    output reg  [2:0] q   // 3-bit register output
);

always @(posedge clk) begin
    if (rst)
        q <= 3'b000;          // reset all bits
    else
        q <= {q[1:0], serial_in}; // shift left
end

endmodule

Developed by:MUGILARASI E
RegisterNumber:25017644


**RTL LOGIC FOR SISO Shift Register**
<img width="1920" height="1080" alt="Screenshot (59)" src="https://github.com/user-attachments/assets/c852c797-c3be-4deb-845a-8232e3426781" />


**TIMING DIGRAMS FOR SISO Shift Register**
<img width="1920" height="1080" alt="Screenshot (58)" src="https://github.com/user-attachments/assets/f153cc2c-6c0e-43ac-b9b3-36d273db1691" />


**RESULTS**
Thus the SISO Shift Register using verilog and validating their functionality using their functional tables is implemented and verified.
