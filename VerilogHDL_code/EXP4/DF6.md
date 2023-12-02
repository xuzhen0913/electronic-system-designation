```verilog
module DF6(clk,clk6d);
//分频器
   input clk;
	output clk6d;
	reg clk6d;
	reg [19:0] cnt;
	always@(posedge clk)begin
	if(cnt==20'b11111111111111111111)begin cnt<=20'b00000000000000000000;clk6d=~clk6d;end
	else cnt<=cnt+20'b00000000000000000001;
	end
endmodule
```
