```Verilog
module LED(EN,ORIGINAL_DATA,CHIPS,CLK,a,b,c,d,e,f,g,LED_S0,LED_S1,LED_S2,LED_S3,LED_S4,LED_S5,LED_S6,LED_S7);

        input EN,CLK;
	input [2:0] CHIPS;
	input [3:0] ORIGINAL_DATA;
	output a,b,c,d,e,f,g,LED_S0,LED_S1,LED_S2,LED_S3,LED_S4,LED_S5,LED_S6,LED_S7;
	wire clk6d;
	wire [3:0] d0,d1,d2,d3,d4,d5,d6,d7;
	wire [2:0] cose;
	wire [3:0] medium_data;
	
	SIXFD(CLK,clk6d);
	count U1(clk6d,cose);
	DATA_TRANSMIT U2(EN,ORIGINAL_DATA,CHIPS,d0,d1,d2,d3,d4,d5,d6,d7);
	Eight_One_Choose U3(d0,d1,d2,d3,d4,d5,d6,d7,cose,medium_data);
	Three_Eight_Decode U4(cose,LED_S0,LED_S1,LED_S2,LED_S3,LED_S4,LED_S5,LED_S6,LED_S7);
	Four_Seven_Decode_LED U5(medium_data,a,b,c,d,e,f,g);
	
endmodule
```
