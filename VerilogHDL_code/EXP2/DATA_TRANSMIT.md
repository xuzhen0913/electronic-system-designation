```
module DATA_TRANSMIT(EN,ORIGINAL_DATA,CHIPS,data0,data1,data2,data3,data4,data5,data6,data7);
   input EN;
	input [3:0]ORIGINAL_DATA;
	input [2:0]CHIPS;
	output [3:0]data0,data1,data2,data3,data4,data5,data6,data7;
	reg [7:0]CS;
	
	always@(CHIPS)begin
	   case(CHIPS)
		   3'b000: CS<=8'b11111110;
			3'b001: CS<=8'b11111101;
			3'b010: CS<=8'b11111011;
			3'b011: CS<=8'b11110111;
			3'b100: CS<=8'b11101111;
			3'b101: CS<=8'b11011111;
			3'b110: CS<=8'b10111111;
			3'b111: CS<=8'b01111111;
		endcase
	end
	
	four_bit_locker U0(ORIGINAL_DATA,EN,CS[0],data0);
	four_bit_locker U1(ORIGINAL_DATA,EN,CS[1],data1);
	four_bit_locker U2(ORIGINAL_DATA,EN,CS[2],data2);
	four_bit_locker U3(ORIGINAL_DATA,EN,CS[3],data3);
	four_bit_locker U4(ORIGINAL_DATA,EN,CS[4],data4);
	four_bit_locker U5(ORIGINAL_DATA,EN,CS[5],data5);
	four_bit_locker U6(ORIGINAL_DATA,EN,CS[6],data6);
	four_bit_locker U7(ORIGINAL_DATA,EN,CS[7],data7);
	
endmodule
```
