```Verilog
`timescale 10ns/1ns
module FPGA_EXP1_tb();

        reg a,b,c;
	wire y0,y1,y2,y3,y4,y5,y6,y7;
	
	initial begin
	   #0 a=1'b0;#0 b=1'b0;#0 c=1'b0;
           #2 c=1'b1;
           #2 b=1'b1;#0 c=1'b0;
           #2 c=1'b1;
           #2 a=1'b1;#0 b=1'b0;#0 c=1'b0;
           #2 c=1'b1;
           #2 b=1'b1;#0 c=1'b0;
           #2 c=1'b1;
           #2 b=1'bx;
           #2 b=1'b1;#0 c=1'bz;
           #2 ;
        end
		
       FPGA_EXP1 U1(a,b,c,y0,y1,y2,y3,y4,y5,y6,y7);
	
endmodule
```
