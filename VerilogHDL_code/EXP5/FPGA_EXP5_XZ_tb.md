```verilog
`timescale 10ns/1ns
module FPGA_EXP5_XZ_tb();
   reg CLK,RST;
	wire [7:0]q;
	
	initial CLK<=0;
	always #1 CLK=~CLK;
	
	initial begin
	RST<=0;
	#2 RST<=1;
	end
	
	FPGA_EXP5_XZ U0(RST,CLK,q);
endmodule

```
