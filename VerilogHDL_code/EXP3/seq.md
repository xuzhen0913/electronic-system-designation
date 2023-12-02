```
module seq(sel,RESET,CLK,detector_out);//顶层实体
        input RESET,CLK,sel;
	output detector_out;
	wire SEQ_EX,SEQ_IN,DATA_DET,CLK6D;
	
	SIXFD U0(CLK,CLK6D);
	SEQ_GENERATE_EXCLUDE U1(CLK6D,RESET,SEQ_EX);
	SEQ_GENERATE_INCLUDE U2(CLK6D,RESET,SEQ_IN);
	SELECT U3(sel,SEQ_EX,SEQ_IN,DATA_DET);
	SEQ_DETECT U4(CLK6D,RESET,DATA_DET,detector_out);
	
endmodule

```
