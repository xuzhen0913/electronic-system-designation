```verilog
module FPGA_EXP5_XZ(RST,CLK,q);
   input RST,CLK;
	output [7:0]q;
	reg [9:0]count;
	
	mystorage U0(count,CLK,q);
	
	always@(posedge CLK)begin
	   if(!RST)count<=10'b0000000000;
		else if(count==10'b1111111111)count<=10'b0000000000;
		else count<=count+10'b0000000001;
	end
endmodule

```
