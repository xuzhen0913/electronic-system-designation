```verilog
`timescale 10ns/1ns
module keyboard_xz_tb();
   reg SW_R3,SW_R2,SW_R1,SW_R0,CLK;
	wire a,b,c,d,e,f,g,COM,SW_CO3,SW_CO2,SW_CO1,SW_CO0;
	
	initial CLK=0;
	always #1 CLK=~CLK;
	
	initial begin
	#0 SW_R3<=1'b1;#0 SW_R2<=1'b1;#0 SW_R1<=1'b1;#0 SW_R0<=1'b1;
	end
	always begin
	#4 SW_R3<=1'b1;#0 SW_R2<=1'b1;#0 SW_R1<=1'b1;#0 SW_R0<=1'b0;
	#2 SW_R3<=1'b1;#0 SW_R2<=1'b1;#0 SW_R1<=1'b0;#0 SW_R0<=1'b1;
	#2 SW_R3<=1'b1;#0 SW_R2<=1'b0;#0 SW_R1<=1'b1;#0 SW_R0<=1'b1;
	#2 SW_R3<=1'b0;#0 SW_R2<=1'b1;#0 SW_R1<=1'b1;#0 SW_R0<=1'b1;
	#2 SW_R3<=1'b1;#0 SW_R2<=1'b1;#0 SW_R1<=1'b1;#0 SW_R0<=1'b1;
	end
	
	keyboard_xz U0(SW_R3,SW_R2,SW_R1,SW_R0,CLK,a,b,c,d,e,f,g,COM,SW_CO3,SW_CO2,SW_CO1,SW_CO0);
endmodule
```
