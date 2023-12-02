```Verilog
module SEQ_GENERATE_EXCLUDE(CLK,RESET,SEQ_EXCLUDE);

  input CLK,RESET;
	output SEQ_EXCLUDE;
	reg SEQ_EXCLUDE;
	reg [2:0]current_st,next_st;
	parameter S0=3'b000,S1=3'b001,S2=3'b010,S3=3'b011,S4=3'b100,S5=3'b101,S6=3'b110,S7=3'b111;
	
	always@(posedge CLK or negedge RESET)begin
	   if(!RESET)current_st<=S0;
		else current_st<=next_st;
	end
	
	always@(current_st)begin
	   case(current_st)
		   S0: next_st<=S1;
			S1: next_st<=S2;
			S2: next_st<=S3;
			S3: next_st<=S4;
			S4: next_st<=S5;
			S5: next_st<=S6;
			S6: next_st<=S7;
			S7: next_st<=S0;
			default: next_st<=S0;
		endcase
	end
	
	always@(current_st)begin
	   case(current_st)
		   S0: SEQ_EXCLUDE<=1'b1;
			S1: SEQ_EXCLUDE<=1'b1;
			S2: SEQ_EXCLUDE<=1'b0;
			S3: SEQ_EXCLUDE<=1'b0;
			S4: SEQ_EXCLUDE<=1'b0;
			S5: SEQ_EXCLUDE<=1'b1;
			S6: SEQ_EXCLUDE<=1'b1;
			S7: SEQ_EXCLUDE<=1'b0;
			default: SEQ_EXCLUDE<=1'b0;
		endcase
	end
	
endmodule
```
