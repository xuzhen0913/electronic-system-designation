```verilog
module colum(colum_chose,SW_CO3,SW_CO2,SW_CO1,SW_CO0);
//生成列选信号
   input [1:0]colum_chose;
	output SW_CO3,SW_CO2,SW_CO1,SW_CO0;
	reg SW_CO3,SW_CO2,SW_CO1,SW_CO0;
	
	always@(colum_chose)begin
	   case(colum_chose)
		   2'b00: begin SW_CO3<=1'b1;SW_CO2<=1'b1;SW_CO1<=1'b1;SW_CO0<=1'b0;end
			2'b01: begin SW_CO3<=1'b1;SW_CO2<=1'b1;SW_CO1<=1'b0;SW_CO0<=1'b1;end
			2'b10: begin SW_CO3<=1'b1;SW_CO2<=1'b0;SW_CO1<=1'b1;SW_CO0<=1'b1;end
			2'b11: begin SW_CO3<=1'b0;SW_CO2<=1'b1;SW_CO1<=1'b1;SW_CO0<=1'b1;end
		endcase
	end
endmodule
```
