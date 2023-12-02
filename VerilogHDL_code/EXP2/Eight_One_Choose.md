```
module Eight_One_Choose(d0,d1,d2,d3,d4,d5,d6,d7,cose,medium_data);
   input [3:0] d0,d1,d2,d3,d4,d5,d6,d7;
	input [2:0] cose;
	output [3:0] medium_data;
	reg [3:0] medium_data;
	
	always@(cose)begin
	   case(cose)
		   3'b000: medium_data<=d0;
			3'b001: medium_data<=d1;
			3'b010: medium_data<=d2;
			3'b011: medium_data<=d3;
			3'b100: medium_data<=d4;
			3'b101: medium_data<=d5;
			3'b110: medium_data<=d6;
			3'b111: medium_data<=d7;
		endcase
	end
endmodule
```
