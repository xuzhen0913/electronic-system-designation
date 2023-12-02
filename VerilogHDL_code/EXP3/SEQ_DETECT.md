```verilog
module SEQ_DETECT(CLK,RESET,datainput,detector_out);//检测器
    input CLK,datainput,RESET;
	output detector_out;
	reg detector_out;
	reg [3:0] current_st,next_st;
	parameter S0=4'b0000,S1=4'b0001,S2=4'b0010,S3=4'b0011,S4=4'b0100,S5=4'b0101,S6=4'b0110,S7=4'b0111,S8=4'b1000,S9=4'b1001;
	
	always@(posedge CLK)begin
	    if(!RESET)current_st<=S0;
		else current_st<=next_st;
	end
	
	always@(current_st,datainput)begin
	   case(current_st)
		    S0: begin
			    if(datainput==1'b1)next_st<=S1;
				 else next_st<=S0;end
			S1: begin
			    if(datainput==1'b1)next_st<=S2;
				 else next_st<=S0;end
			S2: begin
			    if(datainput==1'b1)next_st<=S3;
				 else next_st<=S0;end
			S3: begin
			    if(datainput==1'b0)next_st<=S4;
				 else next_st<=S3;end
			S4: begin
			    if(datainput==1'b1)next_st<=S5;
				 else next_st<=S0;end
			S5: begin
			    if(datainput==1'b0)next_st<=S6;
				 else next_st<=S2;end
			S6: begin
			    if(datainput==1'b0)next_st<=S7;
				 else next_st<=S1;end
			S7: begin
			    if(datainput==1'b1)next_st<=S8;
				 else next_st<=S0;end
			S8: begin
			    if(datainput==1'b1)next_st<=S9;
				 else next_st<=S0;end
			S9: begin
			    if(datainput==1'b0)next_st<=S0;
				 else next_st<=S1;end
			default: next_st<=S0;
		endcase
	end
	
	always@(current_st)begin
	    if(current_st==S9)detector_out<=1'b1;
		else detector_out<=1'b0;
	end
	
endmodule
```
