```
module SIXFD(clk,clk6d);
   input clk;
	output clk6d;
	reg clk6d;
	reg [4:0] cnt;
	always@(posedge clk)begin
	if(cnt==5'b11111)begin cnt<=5'b00000;clk6d=~clk6d;end
	else cnt<=cnt+1;
	end
endmodule
```
