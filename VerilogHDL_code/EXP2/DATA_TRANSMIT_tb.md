    `timescale 10ns/1ns  
    module DATA_TRANSMIT_tb();  
    reg EN_tb;
	reg [2:0] CHIPS_tb,cose_tb;
	reg [3:0] ORIGINAL_DATA_tb;
	wire [3:0] medium_data_tb,data0_tb,data1_tb,data2_tb,data3_tb,data4_tb,data5_tb,data6_tb,data7_tb;
	
	DATA_TRANSMIT U0(EN_tb,ORIGINAL_DATA_tb,CHIPS_tb,data0_tb,data1_tb,data2_tb,data3_tb,data4_tb,data5_tb,data6_tb,data7_tb);
	
	initial begin
	#0 EN_tb=1'b1;#0 CHIPS_tb=3'b000;#0 ORIGINAL_DATA_tb=4'b0000;
	#1 EN_tb=1'b0;#0 cose_tb=3'b000;#0 CHIPS_tb=3'b001;#0 ORIGINAL_DATA_tb=4'b0001;#1 EN_tb=1'b1;
	#1 EN_tb=1'b0;#0 cose_tb=3'b001;#0 CHIPS_tb=3'b010;#0 ORIGINAL_DATA_tb=4'b0010;#1 EN_tb=1'b1;
	#1 EN_tb=1'b0;#0 cose_tb=3'b010;#0 CHIPS_tb=3'b011;#0 ORIGINAL_DATA_tb=4'b0011;#1 EN_tb=1'b1;
	#1 EN_tb=1'b0;#0 cose_tb=3'b011;#0 CHIPS_tb=3'b100;#0 ORIGINAL_DATA_tb=4'b0100;#1 EN_tb=1'b1;
	#1 EN_tb=1'b0;#0 cose_tb=3'b100;#0 CHIPS_tb=3'b101;#0 ORIGINAL_DATA_tb=4'b0101;#1 EN_tb=1'b1;
	#1 EN_tb=1'b0;#0 cose_tb=3'b101;#0 CHIPS_tb=3'b110;#0 ORIGINAL_DATA_tb=4'b0110;#1 EN_tb=1'b1;
	#1 EN_tb=1'b0;#0 cose_tb=3'b110;#0 CHIPS_tb=3'b111;#0 ORIGINAL_DATA_tb=4'b0111;#1 EN_tb=1'b1;
	#1 EN_tb=1'b0;#0 cose_tb=3'b111;#0 CHIPS_tb=3'b000;#0 ORIGINAL_DATA_tb=4'b1000;#1 EN_tb=1'b1;
	#1 EN_tb=1'b0;#0 cose_tb=3'b000;#0 CHIPS_tb=3'b001;#0 ORIGINAL_DATA_tb=4'b1001;#1 EN_tb=1'b1;
	#1 EN_tb=1'b0;#0 cose_tb=3'b001;#0 CHIPS_tb=3'b010;#0 ORIGINAL_DATA_tb=4'b1010;#1 EN_tb=1'b1;
	#1 EN_tb=1'b0;#0 cose_tb=3'b010;#0 CHIPS_tb=3'b011;#0 ORIGINAL_DATA_tb=4'b1011;#1 EN_tb=1'b1;
	#1 EN_tb=1'b0;#0 cose_tb=3'b011;#0 CHIPS_tb=3'b100;#0 ORIGINAL_DATA_tb=4'b1100;#1 EN_tb=1'b1;
	#1 EN_tb=1'b0;#0 cose_tb=3'b100;#0 CHIPS_tb=3'b101;#0 ORIGINAL_DATA_tb=4'b1101;#1 EN_tb=1'b1;
	#1 EN_tb=1'b0;#0 cose_tb=3'b101;#0 CHIPS_tb=3'b110;#0 ORIGINAL_DATA_tb=4'b1110;#1 EN_tb=1'b1;
	#1 EN_tb=1'b0;#0 cose_tb=3'b110;#0 CHIPS_tb=3'b111;#0 ORIGINAL_DATA_tb=4'b1111;#1 EN_tb=1'b1;
	
	#1 EN_tb=1'b0;#0 cose_tb=3'b111;#0 CHIPS_tb=3'b111;#0 cose_tb=3'b111;#0 ORIGINAL_DATA_tb=4'b0000;#1 EN_tb=1'b1;
	end
	
	Eight_One_Choose U1(data0_tb,data1_tb,data2_tb,data3_tb,data4_tb,data5_tb,data6_tb,data7_tb,cose_tb,medium_data_tb);
	
	endmodule
