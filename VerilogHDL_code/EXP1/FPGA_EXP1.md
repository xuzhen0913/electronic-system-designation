```
module FPGA_EXP1(a,b,c,y0,y1,y2,y3,y4,y5,y6,y7);
   input a,b,c;
	output y0,y1,y2,y3,y4,y5,y6,y7;
	reg y0,y1,y2,y3,y4,y5,y6,y7;
	
	always@(a or b or c)
	begin
	   y0 <= 1'b1; y1 <= 1'b1; y2 <= 1'b1; y3 <= 1'b1;
		y4 <= 1'b1; y5 <= 1'b1; y6 <= 1'b1; y7 <= 1'b1;
		case({a,b,c})
		   3'b000: y0 <= 1'b0;
			3'b001: y1 <= 1'b0;
			3'b010: y2 <= 1'b0;
			3'b011: y3 <= 1'b0;
			3'b100: y4 <= 1'b0;
			3'b101: y5 <= 1'b0;
			3'b110: y6 <= 1'b0;
			3'b111: y7 <= 1'b0;
		endcase
	end
endmodule
```
