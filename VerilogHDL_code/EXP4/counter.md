```verilog
module counter(clk,colum_chose);
//计数器
   input clk;
	output [1:0]colum_chose;
	reg [1:0]colum_chose=2'b00;
	
	always@(posedge clk)begin
	if(colum_chose==2'b11)colum_chose<=2'b00;
	else colum_chose<= colum_chose+2'b01;
	end
endmodule

```
