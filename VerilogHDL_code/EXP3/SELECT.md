```verilog
module SELECT(sel,SEQ_EX,SEQ_IN,DATA_DET);//选择器
    input sel,SEQ_EX,SEQ_IN;
	output DATA_DET;
	reg DATA_DET;
	
	always@(sel or SEQ_EX or SEQ_IN)begin
	   case(sel)
		    1'b1: DATA_DET<=SEQ_IN;
			1'b0: DATA_DET<=SEQ_EX;
	   endcase
	end
endmodule


```
