```verilog
`timescale 10ns/1ns
module seq_tb();
    reg seltb,RESETtb,CLKtb;
	wire detector_out_tb;
	
	initial begin
	CLKtb<=1'b0;
	end
	always #1 CLKtb = ~CLKtb;
	
	initial begin
	RESETtb<=1'b0;
	#2 RESETtb<=1'b1;
	#10 RESETtb<=1'b0;
	#10 RESETtb<=1'b1;
	end
	
	initial begin
	seltb<=1'b0;
	#2 seltb<=1'b1;
	#48 seltb<=1'b0;
	end
	
    seq U0(seltb,RESETtb,CLKtb,detector_out_tb);
endmodule
```
