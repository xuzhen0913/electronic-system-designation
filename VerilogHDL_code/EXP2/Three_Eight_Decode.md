```verilog
module Three_Eight_Decode(cose,LED_S0,LED_S1,LED_S2,LED_S3,LED_S4,LED_S5,LED_S6,LED_S7);
   input [2:0]cose;
	output LED_S0,LED_S1,LED_S2,LED_S3,LED_S4,LED_S5,LED_S6,LED_S7;
	reg [7:0]LED_S;
	
	always@(cose)begin
	   case(cose)
		   3'b000: LED_S<=8'b10000000;
			3'b001: LED_S<=8'b01000000;
			3'b010: LED_S<=8'b00100000;
			3'b011: LED_S<=8'b00010000;
			3'b100: LED_S<=8'b00001000;
			3'b101: LED_S<=8'b00000100;
			3'b110: LED_S<=8'b00000010;
			3'b111: LED_S<=8'b00000001;
		endcase
	end
	
	assign LED_S0=LED_S[0];
	assign LED_S1=LED_S[1];
	assign LED_S2=LED_S[2];
	assign LED_S3=LED_S[3];
	assign LED_S4=LED_S[4];
	assign LED_S5=LED_S[5];
	assign LED_S6=LED_S[6];
	assign LED_S7=LED_S[7];
	
endmodule
```
