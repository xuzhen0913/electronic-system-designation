```verilog
module FOUR_SEVEN_DECODE(data,a,b,c,d,e,f,g);
//47译码器，把二进制编码译制为数码管的控制信号
   input [3:0]data;
	output a,b,c,d,e,f,g;
	reg [6:0]final_data;
	
	always@(data)begin
	   case(data)
		   4'b0000: final_data<=7'b0000001;
			4'b0001: final_data<=7'b1001111;
			4'b0010: final_data<=7'b0010010;
			4'b0011: final_data<=7'b0000110;
			4'b0100: final_data<=7'b1001100;
			4'b0101: final_data<=7'b0100100;
			4'b0110: final_data<=7'b0100000;
			4'b0111: final_data<=7'b0001111;
			4'b1000: final_data<=7'b0000000;
			4'b1001: final_data<=7'b0000100;
			4'b1010: final_data<=7'b0001000;
			4'b1011: final_data<=7'b1100000;
			4'b1100: final_data<=7'b0110001;
			4'b1101: final_data<=7'b1000010;
			4'b1110: final_data<=7'b0110000;
			4'b1111: final_data<=7'b0111000;
		endcase
	end
	assign a=final_data[6];
	assign b=final_data[5];
	assign c=final_data[4];
	assign d=final_data[3];
	assign e=final_data[2];
	assign f=final_data[1];
	assign g=final_data[0];
endmodule
```
