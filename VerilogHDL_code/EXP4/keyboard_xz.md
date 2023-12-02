```verilog
module keyboard_xz(SW_R3,SW_R2,SW_R1,SW_R0,CLK,a,b,c,d,e,f,g,COM,SW_CO3,SW_CO2,SW_CO1,SW_CO0);
//顶层实体
   input SW_R3,SW_R2,SW_R1,SW_R0,CLK;
	output a,b,c,d,e,f,g,COM,SW_CO3,SW_CO2,SW_CO1,SW_CO0;
	wire [1:0]colum_chose,saved_colum;
	//wire CLKD6;
	wire [3:0]data;
	wire [2:0]row_CHS;
	
	//DF6 U0(CLK,CLKD6);
	counter U1(CLK,colum_chose);
	colum U2(colum_chose,SW_CO3,SW_CO2,SW_CO1,SW_CO0);
	row_CHS U3(SW_R3,SW_R2,SW_R1,SW_R0,row_CHS);
	Q_save_colum U4(row_CHS,CLK,colum_chose,saved_colum);
	judge U5(row_CHS,saved_colum,data);
	FOUR_SEVEN_DECODE U6(data,a,b,c,d,e,f,g);
	
	assign COM=1'b1;
endmodule
```
