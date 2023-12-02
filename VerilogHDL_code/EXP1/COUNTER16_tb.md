```Verilog
`timescale 10ns/1ns
module COUNTER16_tb();
   reg CLK,RST;
	wire [3:0]DOUT;
	
	initial CLK=0;
	always #2 CLK=~CLK;
	
	initial begin
	#0 RST=1'b0;
	#3 RST=1'b1;
	#15 RST=1'b0;
	#9 RST=1'b1;
	#78 RST=1'b0;
	#5 RST=1'b1;
	end
	
	COUNTER16 U1(CLK,RST,DOUT);
endmodule
```
