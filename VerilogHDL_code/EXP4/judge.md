```verilog
module judge(row_chose,colum_chose,data);
//通过列选信号和行选信号判断按下的按键，输出是二进制编码的数字
   input [2:0]row_chose;
	input [1:0]colum_chose;
	output [3:0]data;
	reg [3:0]data;
	
	always@(row_chose or colum_chose)
	   if(row_chose!=3'b100)begin
		   if(row_chose==3'b000)
			   case(colum_chose)
				   2'b00: begin data<=4'b0000;end
					2'b01: begin data<=4'b0001;end
					2'b10: begin data<=4'b0010;end
					2'b11: begin data<=4'b0011;end
				endcase
			else if(row_chose==3'b001)
			   case(colum_chose)
				   2'b00: begin data<=4'b0100;end
					2'b01: begin data<=4'b0101;end
					2'b10: begin data<=4'b0110;end
					2'b11: begin data<=4'b0111;end
				endcase
			else if(row_chose==3'b010)
			   case(colum_chose)
				   2'b00: begin data<=4'b1000;end
					2'b01: begin data<=4'b1001;end
					2'b10: begin data<=4'b1010;end
					2'b11: begin data<=4'b1011;end
				endcase
			else if(row_chose==3'b011)
			   case(colum_chose)
				   2'b00: begin data<=4'b1100;end
					2'b01: begin data<=4'b1101;end
					2'b10: begin data<=4'b1110;end
					2'b11: begin data<=4'b1111;end
				endcase
		end
endmodule
```
