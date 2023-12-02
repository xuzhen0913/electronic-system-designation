```verilog
module Q_save_colum(row_chose,clk6d,colum_chose,saved_colum);
//边缘触发寄存器，保留状态使输出稳定
   input [2:0]row_chose;
	input [1:0]colum_chose;
	input clk6d;
	output [1:0]saved_colum;
	reg [1:0]saved_colum;
	
	always@(posedge clk6d)begin
	   if(row_chose!=3'b100)saved_colum<=colum_chose;
	end
endmodule
```
